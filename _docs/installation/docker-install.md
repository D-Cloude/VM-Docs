---
title: Docker 설치하기
tags: 
description: 
---

# 도커 설치하기

이 문서에서는 VM에서 컨테이너를 이용을 해야 할 경우에 설치하는 방법을 알려드림니다.

## Linux
### Debian / Ubuntu
#### 저장소 추가 해서 설치하기

1. 우분투 패키지를 업데이트 합니다.
```bash
sudo apt-get update
```
2. 필요한 패키지 설치
```bash
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```
3. Docker의 공식 GPG키를 추가
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

4. Docker의 공식 apt 저장소를 추가
```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

5. 시스템 패키지 업데이트
```bash
sudo apt-get update
```

7. Docker 설치
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
```


#### 패키지로 설치하기
간단하게 설치할경우 패키지로 쉽게 설치하면 됨니다.

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

> 이 설치방법은 도커가 최신버전으로 설치 안될수 있습니다.

### 도커가 잘 설치되어 있는지 확인

#### 도커 실행상태 확인
```bash
sudo systemctl status docker
```

### Windows

#### WSL2

윈도우에서는 도커를 사용해주기 위해서 WSL2를 활성화 해주어야 합니다.<br/>
Powershell를 관리자 권한을 줘서 들어간다음에 아래에 명렁어를 입력해주세요.<br/>

```powershell
 dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
Virtual Machine 기능 사용하기 위해 아래 명렁어를 입력해주세요.

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

WSL를 최신버전으로 업데이트를 하기위해 아래 파일을 설치하고 설치해세요. <br/>
[링크](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

#### WSL2 Linux
마소 앱스토어 들어가서 원하는 리눅스를 검색해서 설치를 해줌니다.<br>
저는 우분투로 해보겟습니다.<br>
<img data-action="zoom" src='{{ "/assets/img/ubuntu.png" | relative_url }}' alt='absolute'><br>

#### docker-desktop
[https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)<br><br>
위 링크에 들어가서 Windows버전을 설치해주면 됨니다.