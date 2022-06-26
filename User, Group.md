# User 계정 다루기

## 리눅스 계정의 종류

1. superuser
2. user
3. system 계정 : 시스템 운영을 위한 계정, 로그인 불가능



- 리눅스 로그인한 계정 확인

```bash
cat /etc/passwd | grep bash
```



## 사용자 만들기

- 사용자 추가

```bash
sudo adduser lluna
```

- 사용자 삭제

```bash
sudo deluser --remove-home llunaB
```



## 사용자 전환

- 로그아웃 하지 않고 전환
  - exit 하면 원래 사용자로 돌아온다.

```bash
su [사용자명]
```

- /home/[username]



## sudoer 그룹

- root 아니어도 su 명령어를 사용할 수 있음

```bash
sudo su
```



- 그룹 수정

```bash
sudo vi /etc/sudoers
```

##### User previlege specifinaction

root ALL=(ALL:ALL) ALL

lluna ALL=(ALL:ALL) ALL  => 추가!!





## 비밀번호

- root의 비밀번호는 아무도 모른다. 보안을 위해 지정하지 않는다!!
- 비밀번호 변경

```bash
passwd
```



# 리눅스 그룹

## 규칙

- User를 생성하면 그룹이 함께 생성된다.
- 한 그룹에 여러 개의 계정을 포함할 수 있다.
- 한 계정은 여러 그룹에 속할 수 있다.



- 그룹 확인

```bash
groups [username]
# 사용자명 : 그룹명1 그룹명2
```

- 그룹 생성

```bash
sudo addgroup [groupname]
```

- 그룹에 사용자 추가

```bash
sudo gpasswd -a [username] [groupname]
```

- 그룹에서 사용자 제거

```bash
sudo gpasswd -d [username] [groupname]
```

- 특정 그룹의 사용자 모두 찾기

```bash
cat /etc/group | grep [groupname]
```



## sudo 그룹

- sudo 그룹에 있으면 sudoer가 될 수 있다.

- sudoer가 되는 방법 2가지

  - 1. /etc/sudoer 파일에 계정 추가
    2. sudo 그룹에 속하면 된다.

    ```bash
    sudo gpasswd -a lluna2 sudo
    ```

    

## 그룹 확인하기

- 그룹확인

```bash
cat /etc/group
```

