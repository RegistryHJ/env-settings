# Zsh

### Zsh 설치 & 기본 Shell 변경 (Ubuntu):

```bash
sudo apt install zsh && chsh -s `which zsh`
```

(MacOS의 경우 Zsh가 기본 Shell임.)

### Oh My Zsh 설치:

```bash
curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh
```

> Oh My Zsh
> <br> https://github.com/ohmyzsh/ohmyzsh

### `~/.zshrc` 열기:

```bash
sudo nano ~/.zshrc
```

### Prompt 설정:

```nano
PROMPT="%(?. %F{#00ff00}✓ %F{#ffffff}[%n @ %m] %F{#00ffff}%~ %F{#00ff00}➤. %F{#ff0000}✗ %F{#ffffff}[%n @ %m] %F{#00ffff}%~ %F{#ff0000}➤) %f"
```

### 적용할 Plugin 입력:

```nano
plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
  zsh-better-npm-completion
)
```

### 적용할 Plugin 설치:

```zsh
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions --depth=1

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting --depth=1

git clone https://github.com/lukechilds/zsh-better-npm-completion ~/.oh-my-zsh/custom/plugins/zsh-better-npm-completion --depth=1
```

### `~/.zshrc` 적용:

```zsh
source ~/.zshrc
```
