# MariaDB

## APT Repository를 사용하여 설치 (Ubuntu 22.04 LTS, MariaDB 11.3 기준)

> MariaDB
> <br> https://mariadb.org/download/?t=repo-config

### 의존성 패키지 설치:

```zsh
sudo apt install apt-transport-https curl
```

### MariaDB Keyring을 디렉토리에 다운로드:

```zsh
sudo mkdir -p /etc/apt/keyrings
sudo curl -o /etc/apt/keyrings/mariadb-keyring.pgp 'https://mariadb.org/mariadb_release_signing_key.pgp'
```

### Repository Source 파일 만들기:

```zsh
sudo nano /etc/apt/sources.list.d/mariadb-sources
```

### Repository Source 파일에 내용 추가:

```zsh
# MariaDB 11.3 repository list - created 2024-03-02 11:09 UTC
# https://mariadb.org/download/
X-Repolib-Name: MariaDB
Types: deb
# deb.mariadb.org is a dynamic mirror if your preferred mirror goes offline. See https://mariadb.org/mirrorbits/ for details.
# URIs: https://deb.mariadb.org/11.3/ubuntu
URIs: https://ftp.yz.yamagata-u.ac.jp/pub/dbms/mariadb/repo/11.3/ubuntu
Suites: jammy
Components: main main/debug
Signed-By: /etc/apt/keyrings/mariadb-keyring.pgp
```

### Repository 업데이트:

```zsh
sudo apt update
```

### MariaDB Server 설치:

```zsh
sudo apt install mariadb-server
```

### MariaDB 서비스 시작:

```zsh
sudo systemctl start mariadb
```

### MariaDB 서비스를 StartUp 서비스로 설정:

```zsh
sudo systemctl enable mariadb
```

<br>

## Homebrew를 사용하여 설치하기 (MacOS, MariaDB 11.3 기준)

### Formula로 설치:

```zsh
brew install mariadb
```

### MariaDB 서비스 시작:

```zsh
brew services start mariadb
```

### `~/.zshrc` 열기:

```zsh
sudo nano ~/.zshrc
```

### MariaDB에서 `PATH`, `LDFLAGS`, `CPPFLAGS`, `PKG_CONFIG_PATH` 추가:

```nano
export PATH="/opt/homebrew/opt/mariadb/bin:$PATH"
export LDFLAGS="-L/opt/homebrew/opt/mariadb/lib"
export CPPFLAGS="-I/opt/homebrew/opt/mariadb/include"
export PKG_CONFIG_PATH="/opt/homebrew/opt/mariadb/lib/pkgconfig"
```

### `~/.zshrc` 적용:

```zsh
source ~/.zshrc
```

### MariaDB 서비스를 Damon으로 등록:

```zsh
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mariadb.plist
```

<br>

## Docker를 사용하여 설치 (권장)

> MariaDB - Docker Hub
> <br> https://hub.docker.com/_/mariadb

### MariaDB Docker Image Pull하기:

```zsh
docker pull mariadb:latest
```

### MariaDB Docker Container 만들기:

```zsh
docker run --detach --name "[ContainerName]" --publish 3306:3306 --env MARIADB_ROOT_PASSWORD="[DBRootPassword]" mariadb:latest
```

### Container bash에 액세스하기:

```zsh
docker exec -it "[ContainerName]" bash
```

<br>

## MariaDB Setting 하기

### MariaDB 보안 설정 스크립트 실행:

```zsh
sudo mariadb-secure-installation
```

or `Docker`

```zsh
mariadb-secure-installation
```

### 스크립트 진행:

```zsh
Enter current password for root (enter for none): "[DBRootPassword]"
Switch to unix_socket authentication [Y/n] y
Change the root password? [Y/n] n
Remove anonymous users? [Y/n] y
Disallow root login remotely? [Y/n] y
Remove test database and access to it? [Y/n] y
Reload privilege tables now? [Y/n] y
```

### 프롬프트 변경을 위해 파일 열기

`Ubuntu`:

```zsh
sudo nano /etc/mysql/my.cnf
```

or `Docker`

```zsh
nano /etc/mysql/my.cnf
```

`MacOS`:

```zsh
sudo nano /opt/homebrew/etc/my.cnf
```

### 파일 하단에 프롬프트 옵션 추가:

```nano
...
[mysql]
prompt='\u @ \h [\d] -> '
```

### MariaDB 실행 (root):

```zsh
sudo mariadb
```

or `Docker`

```zsh
mariadb
```

### MariaDB에 User 추가:

```sql
CREATE USER `[DBUserName]`@`%` IDENTIFIED BY '[DBUserPassword]';
```

### MariaDB에 Database 추가:

```sql
CREATE DATABASE `[DBName]` DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
```

### MariaDB Database에 User 권한 부여:

```sql
GRANT ALL PRIVILEGES ON `[DBName]`.* TO `[DBUserName]`@`%`;
```

### MariaDB 캐시 초기화:

```sql
FLUSH PRIVILEGES;
```

### MariaDB Shell에서 나가기:

```sql
exit
```

### MariaDB 실행 (User):

```zsh
sudo mariadb -u [DBUserName] -p
```

or `Docker`

```zsh
mariadb -u [DBUserName] -p
```

### MariaDB Database에 접속:

```sql
USE `[DBName]`;
```

### MariaDB Shell에서 나가기:

```sql
exit
```
