
## CTF-Tool
- `CTF` 도구 설치 노트

### RsaCtfTool
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