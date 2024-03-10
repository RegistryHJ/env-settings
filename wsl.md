# WSL (Windows Subsystem for Linux)

> WSL
> <br> https://learn.microsoft.com/ko-kr/windows/wsl/install

## WSL 설치 명령

### PowerShell에서 WSL 설치 명령으로 설치:

```posh
wsl —install
```

<br>

## WSL 설치 경로 변경

### WSL 종료:

```posh
wsl —shutdown
```

### Ubuntu tar 파일로 내보내기:

```posh
wsl --export Ubuntu "[내보낼 경로]"\Ubuntu.tar
```

### Ubuntu 등록 해제:

```posh
wsl --unregister Ubuntu
```

### Ubuntu 원하는 경로로 가져오기:

```posh
wsl --import Ubuntu "[원하는 경로]"\Ubuntu "[내보내기 한 파일 경로]"\Ubuntu.tar
```

<br>

## WSL 고급 설정 구성

> WSL 고급 설정 구성
> <br> https://learn.microsoft.com/ko-kr/windows/wsl/wsl-config#wslconfig

### 전역 설정 구성 `%UserProfile%\\.wslconfig`:

```
[wsl2]
processors=2
memory=8GB
swap=16GB
swapFile="[원하는 경로]\\swap.vhdx"
```

### 배포 당 설정 구성 `/etc/wsl.conf`:

```bash
sudo nano /etc/wsl.conf
```

```nano
[boot]
systemd = true

[user]
default = "[UserName]"
```
