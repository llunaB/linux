# Shell

- 쉘은 프로그램이다.
- `kernel`을 감싸고 있고, 운영체제 내부에 접근하기 위한 프로그램



## window의 shell

- cmd 명령프롬프트 (cmd.exe)  -> 거의 이것만 씀
- Power Shell
- Windows Shell (윈도우 화면)



## Ubuntu의 shell

- 윈도우는 GNOME 3, CLI 는 Bash
- GNOME3의 그래픽 라이브러리 이름: GTK
- UNITY GUI shell(예전버젼 ~우분투 16.04)



# GNOME 꾸미기

## Tweak 설치

https://linuxconfig.org/how-to-install-tweak-tool-on-ubuntu-22-04-lts-jammy-jellyfish-linux

- Tweak 실행 후 Apprearance -Theme 변경가능

## FireFox 실행

- FireFox 확장 플러그인 설치 
- https://addons.mozilla.org/ko/firefox/addon/gnome-shell-integration

## DashtoDock 설치

- https://extensions.gnome.org/
- Dash to Dock
- OpenWeather
- User Themes



## CLI Shell 의 종류

- 우분투 기본 CLI Shell : Bash

쉘 종류 확인하기

```bash
cat /etc/shells
```



## 명령어 구분 : shell 명령어 vs. shell script 명령어

- ls 명령어 == 쉘 명령어

  - /bin에 프로그램이 존재!

  - ```bash
    find / -name ls 
    ```

  - ```bash
    /bin
    ```

    

- echo 명령어 == bash 쉘 스크립트 명령어



## 환경변수

- 쉘스크립트의 시스템 전역변수

```bash
printenv
```

- 현재 사용중인 쉘 확인 (SHELL=/bin/bash 로 환경변수 저장되어있음!)

```bash
echo $SHELL
```

