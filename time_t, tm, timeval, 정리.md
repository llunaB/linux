# time

## UTC

Coordinated Universal Time

- 국제 표준시간
- 1972년부터 시행
- UTC + offset으로 시간 표시
- 한국 = UTC + 9 = KST



## RTC

Real Time Clock = RTC

- 전원 없어도 계산을 함
- 수은 건전지 사용



## Linux에서 관리하는 시간

### date

- 부팅시 RTC 정보를 받아 리눅스에서 시간 정보를 관리
- 네트워크에 연결될 때(인터넷 될 때) Time 서버에서 시간을 자동 update



### hwclock

- sudo hwclock
- RTC HW 장치가 가지고 있는 시간 정보 값
- 리눅스에서는 date와 RTC가 맞지 않으면 한쪽으로 Sync를 맞춰주는 명령어를 써야함



### 인터넷 타임서버 시간값 - 클라우드 이용시 필수

```bash
sudo apt install rdate
sudo rdate time.bora.net
# date 로 현재시간 확인
```



### hwclock 명령어

- 시스템 시간을 기준으로 RTC 시간을 변경

```bash
sudo hwclock -s
```

- 반대 명령어 : RTC 기준으로 시스템 시간을 ㅂ녀경

```bash
hwclock -w
```



## time 시스템콜

- time_t time(NULL); 
  - 1970년 1월 1일 0시 0초부터 현재 시간까지 지난 초
- time_t type
  - 64 비트 unsigned 정수형 숫자



## Latency

- 자극과 반응 시간
- 신호 전달 후 Response 시간
- 함수 호출 후 리턴까지 걸리는 시간



## clock 함수

- CPU Clock 이 아닌 프로세스 clock
- 현재 프로세스가 시작되고, 얼마나 시간이 흘렀는지 구함
- 리턴 값 = clock_t



# timeval

## gettimeofday 시스템콜

- us 단위로 정밀한 시간을 얻을 수 있다.

### 사용방법

```c
int gettimeofday(struct timeval *tv, struct timezone *tz);
```



# 정리 - Latency 측정방법

## 초 단위 현재시간 측정 

- sleep 시스템콜 사용


## us 단위 시간 측정

- clock 시스템콜 사용



## us 단위 현재 시간 측정

- gettimeofday 시스템콜 사용



