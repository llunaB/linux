# Multi Thread, Multi Processing

## 멀티쓰레드

- Context Switching 빠름 (전역변수 공유)
- Thread 통신이 빠름
- 공유 리소스 이슈 발생



## 멀티프로세스

- Context Switching 느림
- 통신 느림(IPC)
- 메모리가 독립적으로 보호됨



## 쓰레드를 사용하는 방법

### Data Decomposition

- 데이터 단위로 분해하여 Thread Programming
- 각 Thread 마다 같은 작업을 수행

### Task Decomposition

- 작업 단위로 분해하여 Thread Programming
- 각 Thread 마다 다른 작업을 수행
- pipeline ----- (컨베이어 벨트 공장처럼..)



# System Call

> 리눅스 App 에서 리눅스 커널에 요청을 위해 만들어둔 함수

- printf, scanf 

- fopen, fscanf, fprintf 

  모두 커널이 필요하다.

  장치를 제어하려면 시스템 콜을 써서 장치에 매핑된 파일을 수정.



## 파일

리눅스에서 파일의 의미

- 저장장치에 저장된 파일들
- 저장장치에 저장된 디렉토리들
- 장치들(마우스, 키보드, 메모리 - 파일로 취급)
- Socket, Pipe



# Thread 발생가능한 문제

## Race Condition

- Thread, Process 의 타이밍에 따라 결과값이 달라질 수 있는 상태
- 경쟁 상태
- 예) **여러 개의 쓰레드가 전역변수를 같이 쓰는 경우**



## Critical Section

- Thread, Process가 동시에 접근해선 안되는 곳
- HW 장치를 사용하는 곳, Shared Resource(전역변수 등)



# Thread / Process Synchronization

- Critical Section을 동시에 수행하지 않도록 않게 하기 위해 Thread 간 협의를 맞추는 것
- 둘이서 하나의 HW 자원을 쓰거나 하나의 변수를 사용할 때 한 명씩 돌아가면서 쓰기 위해 협의를 봐야 함
- 동기화 알고리즘은 Pthreads가 지원
  - 뮤텍스
  - 세마포어
  - Sprin Lock
  - Barrier