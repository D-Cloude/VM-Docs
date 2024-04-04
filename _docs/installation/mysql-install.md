---
title: mysql 설치
tags: 
description: mysql을 설치 해보자
---
# mysql 설치
VM에서 Mysql을 설치하는 방법을 알려드리겟습니다.

## Linux

### Debian, Ubuntu

#### mysql 패키지를 설치해 줌니다.

```bash
sudo apt update
sudo apt install mysql-server
```
#### mysql 포트를 설정해줌니다.
```bash
sudo ufw allow mysql
```
#### MySQL 실행
```bash
sudo systemctl start mysql
```

## Docker

> Root권한으로 실행해서 하시기바람니다.

### 도커 이미지를 다운해줌니다.
```bash
docker pull mysql
```

### Mysql 도커를 생성해 줌니다.
```bash
docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=<password> -d -p 3306:3306 mysql:latest
```
[설정사항]
- --name <container_name> : <container_name> 이름의 컨테이너를 실행한다.
- -e : 컨테이너 내에서 사용할 환경변수를 설정
- -e MYSQL_ROOT_PASSWORD=<password> : MySQL의 root 권한의 비밀번호를 <password>로 설정한다.
- -d : detach 모드로 컨테이너가 실행된다. 컨테이너가 백그라운드로 실행된다고 보면 된다.
- -p <호스트 포트> <컨테이너 포트> : 호스트와 컨테이너의 포트를 연결한다
- mysql:latest : 컨테이너에 사용할 이미지

### 외부에서 접속을 하기 원하면 방과벽을 열어줌니다.
```bash
sudo ufw allow mysql
```
## Windows