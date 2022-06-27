# 시스템 정보확인

## 네트워크 정보 확인

- ip 주소 확인

```bash
ipconfig
```



## 디렉토리 용량 확인

- 파일 용량까지 바이트 단위로

```bash
ls -al
```

- 인간 옵션

```bash
ls -alh
```



> File System 및 SSD에서 최소 저장 사이즈는 4KB
>
> 따라서 6 Byte를 저장하더라도, 빈 공간으로 꽉 채워 4KB 단위로 저장한다.



- 디스크 용량 확인 

```bash
du ./bts.txt
```

```bash
du -h ./bts.txt
```





## CPU 정보

```bash
cat /proc/cpuinfo
```



## Memory 정보

```Bash
cat /proc/meminfo
```



## 사용중인 메모리 정보 확인

```bash
free -h
```

- total = used + free + cache
- available : 하나의 앱이 현재 사용할 수 있는 메모리 추정 계산치
- Swap: RAM 부족한 경우, 하드디스크를 일시적으로 메모리처럼 사용하는 공간



## 디스크 정보 확인

- SCSI 장치들의 디바이스 파일 확인

```bash
cat /proc/scsi/scsi
```

### SCSI 란?

- 과거 컴퓨터에서 장치를 병렬 방식으로 연결하는 인터페이스 표준 중 하나
- SSD/ HDD 구분없이 사용하는 인터페이스 이름

- SCCI 장치 명령어

```bash
$ sudo apt install lsscsi -y
$ lsscsi
```



### 디스크 장치파일 명명 규칙

- 먼저 발견하는 것부터 이름을 지음
  - sd* (SCSI DISK)
  - sr* (SCSI CD-ROM)
  - sg* (SCSI GENERIC)
- 확인해보기

```bash
ls /dev/s*
```



### 디스크 세부 정보 확인

- SCSI 장치들의 디스크 파티션 정보 확인

```bash
sudo fdisk -l
```

- fdisk : 파티션 관리 유틸리티

- sda용량 읽기

```bash
sudo fdisk -l /dev/sda
```



## USB 확인

- USB에 연결된 장치 목록 확인

```bash
lsusb
lsusb -t # 계층구조
```



## OS 정보 확인

- 리눅스 배포판 정보 확인

```bash
cat /etc/os-release
cat /etc/centos-release
```



### LSB (Linux Standard Base)

- Linux 배포판들끼리 표준화(ISO 표준)
  - POSIX 포직스
  - File System
  - System Call
  - Package Format



## 리눅스 커널 버전 확인

```bash
cat /proc/version
```

or

```bash
uname -r
```



## 현재 사용자 계정 확인

```bash
who
```

- 레벨 확인

```bash
who -r
```

