# Shell App

## 설치해보자

```bash
sudo apt install screenfetch -y
sudo apt install toilet -y
sudo apt install figlet -y
sudo apt install jp2a -y

sudo apt install screenfetch toilet figlet jp2a -y
```



### 정보 추정하기 - screenfetch

```bash
screenfetch
```



### toilet 글씨를 큰 문자로 표시

```bash
toilet [하고싶은 말]
```

- -F border : 테두리 처리
- --metal : 메탈릭 표시
- --gay

```bsah
ls -al | toilet -f term --gay
```



### figlet

- ASCII 로 배너문자 만들기
- 폰트 확인

```bash
showfigfonts KFC
```

- 특정 폰트로 출력

```bash
figlet -f [폰트명] [텍스트내용]
```

- 파이프랑 써보기

```bash
figlet KFC | toilet -f term --gay
```



### 이미지를 ASCII 로 : jp2a

- 이미지 주소 복사
- 이미지 다운로드

```bash
wget [image URL]
```

- jpg 변환

```bash
sudo apt install imagemagick
```

```bash
convert [png file name][jpg file name].jpg
```

- 써보기

```bash
jp2a[image file name] --background=light
```

