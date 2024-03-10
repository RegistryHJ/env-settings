# SDKMan (Java, Tomcat, etc.)

> SDKMan
> <br> https://sdkman.io/install

### Curl로 설치:

```zsh
curl -s "https://get.sdkman.io" | bash
```

### SDKMan을 `PATH`에 추가:

```zsh
source "$HOME/.sdkman/bin/sdkman-init.sh"
```

### SDKMan으로 JAVA 리스트 보기:

```zsh
sdk list java
```

### SDKMan으로 JAVA 설치:

```zsh
sdk install java "[버전]"
```

### SDKMan으로 Tomcat 리스트 보기:

```zsh
sdk list tomcat
```

### SDKMan으로 Tomcat 설치:

```zsh
sdk install tomcat "[버전]"
```

### 프로그램을 설치된 버전 중 원하는 버전으로 변경:

```zsh
sdk use "[버전 변경을 원하는 프로그램]" "[변경할 버전]"
```
