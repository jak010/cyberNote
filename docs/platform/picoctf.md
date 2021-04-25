- URL (picoGYM)
     - `https://play.picoctf.org/practice?page=1`

## General

### Obedian Cat
 - Description
	 ```
	  This file has a flag in plain sight (aka "in-the-clear"). 
	 ```
 - Walk-Throught
   ```sh
   $ cat flag
   ```
 - Flag Is: picoCTF{s4n1ty_v3r1f13d_2aa22101}

### Python Wrangling
  - Description
  ```
  Python scripts are invoked kind of like programs in the Terminal...
  Can you run this Python script using this password to get the flag?
  ```
  - Walk-Throught
    - File (file_name: content)
        - `ende.py`
        - `flag.txt.en`
        - `pw.txt`: 67c6cc9667c6cc9667c6cc9667c6cc96 
    - Solve
    ```sh
    $ python3 ende.py -d flag.txt.en
	  Please enter the password:67c6cc9667c6cc9667c6cc9667c6cc96
	  picoCTF{4p0110_1n_7h3_h0us3_67c6cc96}
    ```

### Wave a flag
  - Description
  ```
  Can you invoke help flags for a tool or binary
  This program has extraordinarily helpful information...
  ```
  - Walk-Throught
     - File: `warm`
     - Solve
	  ```
	  $ warm -h
	  Oh, help? I actually don't do much, but I do have this flag here:
	  picoCTF{b1scu1ts_4nd_gr4vy_30e77291}
	  ```

### Nice NetCat
 - Description
 ```text
 There is a nice program that you can talk to by using this command in a shell:
 $ nc mercury.picoctf.net 35652, but it doesn't speak English...
 ```
 - `Walk-Throught`
 ```python
  with open("nice_netcat", "r" ,encoding="utf8") as file:
    strings = "".join([ chr(int(x)) for x in file.readlines()])
    print(strings)
 ```

### Static ain't always noise
 - Description
 ```text
 Can you look at the data in this binary: static? This BASH script might help!
 ```
 - `Walk-Throught`
 ```sh
 $ ./ltdis.sh static
 $ cat static.ltdis.strings.txt
 ```

### Tab, Tab, Attack
 - Description
 ```text
 Using tabcomplete in the Terminal will add years to your life, esp.
 when dealing with long rambling directory structures and filenames: Addadshashanammu.zip
 ```
 - `Walk-Throught`
 ```sh
 $ apt install tree unzip
 $ tree -L 11 -f
 $ cat ./Addadshashanammu/../fang-of-haynekhtnamet
 ```

