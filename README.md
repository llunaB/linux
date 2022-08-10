# Basics

## 용어

### 리눅스란?

컴퓨터 운영체제의 일종으로 유닉스 운영체제보다 자유롭게 변형하고 배포할 수 있는 오픈소스, 리눅스 커널

### 배포판

리눅스 커널에 컴파일러, 쉘, 응용 프로그램 등을 붙여서 만든 것

- 데비안 계열의 Ubuntu
- 레드햇 계열의 CentOS

### 쉘?

- 사용자(응용 프로그램)와 커널을 연결하는 역할
- 사용자 CLI 인터페이스

### 커널?

- 리눅스의 핵심
- 하드웨어 등 컴퓨터의 모든 자원 초기화 및 제어 기능



## 파일 구조

- 리눅스의 가장 상위 구조는 `root` 이다.

- root(/)

  - bin : 프로그램 설치 경로 
  - etc : 제어판 개념의 설정파일
  - usr : 기본 실행 파일과 라이브러리 파일, 헤더 파일 등, UNIX SYSYEM RESOURCE의 약자
    - bin 실행파일 
    - lib 라이브러리
  - home : 사용자 홈 디렉터리가 생성되는 디렉터리
    - user1 : 윈도우 `C:\\Users\\admin`
    - user2
    - user3
  - tmp : 앱이 막 쓰고 작업하는 영역
  - root : root 계정의 홈 디렉토리이다. 루트 개별 폴더
  - boot : 부팅에 필요한 커널 파일
  - etc : 리눅스 설정에 필요한 각종 파일
  - dev : 장치 파일이 담긴 디렉터리
  - opt : 추가 패키지가 설치되는 디렉터리
  - sys: 리눅스 커널과 관련된 파일이 있는 디렉터리

  

## 명령어 타입

- alias
- built-in 
- 응용어플리케이션 명령어



## user?

- user 와 root의 `bash` 는 다르다.
- su - 하면 또다른 process 가 생성되는 것이고 이것을 `fork` 라고 한다.



## 파일 종류

- 디렉터리
- 심볼링 링크
  - 하드링크
  - 심볼릭 링크



## redirection

```bash
ls -l test2 >> out.log 2>&1   
```



## 사용자

```bash
sudo chown 사용자 대상
```



## 권한

- rwx rwx rwx
- unmask 개념
- SetUID, SetGID, Sticky Bit



# grep, awk

s

# Commands

## history : 이전 기록 확인

```bash
![번호]
```



## cat : 파일 내용 출력

```bash
cat /proc/cpuinfo
```

- 내용을 파일로 저장

```bash
cat /proc/cpuinfo > bts.txt
```



## find : 파일 찾기

- 전 영역에서 특정 파일 찾기

```bash
find / -name "file.txt"
```

- 단어에 config가 포함된 모든 파일 및 디렉토리 찾기

```bash
find ./ -name "*config*"
```

- 파일만 찾기

```bash
find [경로] -name "filename" -type f
```

- 디렉토리만 찾기

```bash
find [경로] -name "filname" -type d
```



## grep : 문자열 검색 - 정규표현식 사용 가능

- meminfo 파일 내 "kB" 문자열 검색

```bash
grep kB ./meminfo
```

- 현재 디렉토리에 있는 모든 파일 대상으로 "ache"가 들어있는 라인 모두 출력
  - -r 옵션 추가시 내부 디렉토리에 있는 파일도 모두 찾음

```bash
grep ache ./*
```

- 다른 명령어 출력결과에 문자열 검색하기( | 로 구분 )

```bash
ls -al | grep .v
```

```bash
cat abc.txt | grep bbq
```



## 예시

- /proc 디렉토리에 info 로 시작하는 파일 찾기 (관리자 권한)

```bash
sudo find /proc -name "info*"
```

- /bin 디렉토리에 z로 시작하는 파일 모두 찾기
  - /bin은 링크이기 때문에 /를 붙여야 함

```bash
find /bin/ -name "z*"
```

