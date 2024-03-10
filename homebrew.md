# Homebrew

> Homebrew
> <br> https://brew.sh/ko/

### Homebrew 설치 명령:

```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Homebrew 업데이트:

```zsh
brew update
```

### Homebrew 업그레이드:

```zsh
brew upgrade
```

### Homebrew로 설치할 Formula/Cask 검색:

```zsh
brew search "[FormulaName/CaskName]"
```

### Homebrew로 Formula 설치:

```zsh
brew install "[FormulaName]"
```

### Homebrew로 Cask 설치:

```zsh
brew install —cask "[CaskName]"
```

### Homebrew로 설치된 모든 목록 보기:

```zsh
brew list
```

### Homebrew로 설치된 Formula 목록 보기:

```zsh
brew list —formula
```

### Homebrew로 설치된 Cask 목록 보기:

```zsh
brew list —cask
```

### Homebrew로 설치된 Formula/Cask 삭제:

```zsh
brew remove "[FormulaName/CaskName]"
```

### Homebrew로 설치된 Formula/Cask의 이전 버전 다운로드 및 캐시 파일 삭제:

```zsh
brew cleanup "[FormulaName/CaskName]"
```

### Homebrew로 설치된 필요없는 종속성 제거:

```zsh
brew autoremove
```
