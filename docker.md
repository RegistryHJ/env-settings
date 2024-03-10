# Docker

## Docker Desktop

> Install Docker Desktop
> <br> https://www.docker.com/products/docker-desktop/

<br>

## Docker Engine (Ubuntu)

> Install Docker Engine
> <br> https://docs.docker.com/engine/install/ubuntu/

### Docker GPG Key 추가:

```zsh
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

### APT Source에 추가:

```zsh
echo \
 "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
 $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
 sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
```

### Docker 설치:

```zsh
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock 에러 발생 시:

```zsh
sudo usermod -a -G docker "[UserName]"
```
