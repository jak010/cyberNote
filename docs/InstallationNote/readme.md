
## docker for pentest (with Kali)
- `https://www.kali.org/blog/official-kali-linux-docker-images/`


## RsaCtfTool
  - `URL`: https://github.com/Ganapati/RsaCtfTool.git
  - `Enviorment`
    - `OS`: macOs Big Sur (11.2.1) (M1)
  - `Installation`
    ```sh
    $ brew install gmp

    $ find / -name "gmp.h" 2>/dev/null
    >> /opt/homebrew/../gmp.h

    $ export "CFLAGS=-I/opt/homebrew/include -L/opt/homebrew/lib" 

    $ pip3 install -r requirement.txt
    ```
    - 위 과정을 진행했음에도 불구하고 `OS X`에서는 실행이 되질 않는다
  - `Installation Way`: using Dockerfile
    ```sh
    $ sudo docker build -t alpine:rsactftool .
    ```
    - repository에 Dockerfile 있으니 그걸 이용하자


## pip2 Installation
  - OS: kali 2021.01
  - pip2 installation guide
    ```sh
    sudo apt update
    curl https://bootstrap.pypa.io/pip/2.7/get-pip.py --output get-pip.py
    sudo python2 get-pip.py

    sudo pip install --upgrade setuptools
    ```