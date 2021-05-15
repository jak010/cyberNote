
## Badit

#### Level 00
 - Server : `ssh bandit0@bandit.labs.overthewire.org -p 2220`
 	- password: bandit0
 - `Walk Throught`
 	- ssh 로 원격 서버 접속을 시도할 수 있는지를 보는 문제
 - Next Level: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

#### Level 01 
  - Server : `ssh bandit1@bandit.labs.overthewire.org -p 2220`
 	- password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1
  - `Walk Throught`
 	```sh
 	cat *
 	```
 	- 대시 (-) 파일 읽는 문제
  - Next Level: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

#### Level 02
  - Server : `ssh bandit2@bandit.labs.overthewire.org -p 2220`
 	- password: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
  - `Walk Throught`
 	- 파일명에 공백이 들어간 파일을 읽을 수 있는 지 보는 문제
 	- tab을 통해 자동완성으로 읽으면 됨
  - Next Level: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

#### Level 03
  - Server : `ssh bandit3@bandit.labs.overthewire.org -p 2220`
 	- password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
  - `Walk Throught`
 	```sh
 	$ cat ~/inhere/.hidedn
 	```
  - Next Level: pIwrPrtPN36QITSp3EQaw936yaFoFgAB


#### Level 04
  - Server : `ssh bandit4@bandit.labs.overthewire.org -p 2220`
 	- password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
 - `Walk Throught`
 	```sh
 	$ cd ~/inhere
 	$ file ./*
 	...
 	./-file07: ASCII text
 	...
 	```
 	- 필요한 파일의 종류를 탐색하고 어떤 식으로 찾아낼 수 있는지 보는 문제
 - Next Level: koReBOKuIDDepwhWk7jZC0RTdopnAYKh

#### Level 05
  - Server : `ssh bandit5@bandit.labs.overthewire.org -p 2220`
 	- password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
 - `Walk Throught`
 	```sh
 	$ cd ~/inhere
 	$ find ./* -size 1033c
 	```
 	- 파일의 크기를 이용하여 find를 이용할 수 있는지 보는 문제
 - Next Level: DXjZPULLxYr17uwoI01bNLQbtFemEgo7

#### Level 06
  - Server : `ssh bandit6@bandit.labs.overthewire.org -p 2220`
 	- password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
 - `Walk Throught`
 	```sh
 	$ find / -group "bandit6" 2>/dev/null
 	$ cat /var/lib/dpkg/info/bandit7.password
 	```
 	- 특정 그룹에 소속된 파일을 검색할 수 있는지 보는 문제
 - Next Level: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

#### Level 07
  - Server : `ssh bandit7@bandit.labs.overthewire.org -p 2220`
 	- password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
 - `Walk Throught`
 	```sh
 	$ cat data.txt | grep "millionth"
 	```
 	- 파일의 텍스트가 많을 떄 특정 값으로 원하는 내용만 추출할 수 있는지 보는 문제
 - Next Level: cvX2JJa4CFALtqS87jk27qwqGhBM9plV



