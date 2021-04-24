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
   cat flag
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