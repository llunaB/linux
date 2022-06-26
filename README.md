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

