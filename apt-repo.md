# APT Repository

### `/etc/apt/sources.list` 열기:

```bash
sudo nano /etc/apt/sources.list
```

### 주소 부분을 아래와 같이 변경

### Ubuntu 미러 서버:

```nano
https://ftp.kaist.ac.kr/ubuntu (Korea, 10Gbps)
https://mirror.nishi.network/ubuntu (Japan, 10Gbps)
```

### Ubuntu Ports 미러 서버:

```nano
https://ftp.kaist.ac.kr/ubuntu-ports (Korea, 10Gbps)
https://mirror.nishi.network/ubuntu-ports (Japan, 10Gbps)
```

> 그 외 서버 (Launchpad)
> <br> https://launchpad.net/ubuntu/+archivemirrors

### Repository 업데이트:

```bash
sudo apt update
```

### Repository 업그레이드:

```bash
sudo apt upgrade
```
