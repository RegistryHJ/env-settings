# Flutter

> Flutter 설치
> <br> https://docs.flutter.dev/get-started/install/macos/mobile-ios?tab=download

### Flutter SDK 설치 번들을 설치 페이지에서 다운로드

### Zip파일 압축 해제 (MacOS Arm64 3.19.3 버전 기준):

```zsh
unzip flutter_macos_arm64_3.19.3-stable.zip -d ~/.flutter
```

### `~/.zshrc` 열기:

```zsh
sudo nano ~/.zshrc
```

### `PATH`에 Flutter SDK 경로 추가

`Ubuntu`:

```nano
export PATH="/home/"[UserName]"/.flutter/flutter/bin:$PATH"
```

`MacOS`:

```nano
export PATH="/Users/"[UserName]"/.flutter/flutter/bin:$PATH"
```

### `~/.zshrc` 적용:

```zsh
source ~/.zshrc
```

### Flutter Doctor 실행:

```zsh
flutter doctor -v
```
