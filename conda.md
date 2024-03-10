# Conda

> Anaconda
> <br> https://www.anaconda.com/download#downloads

> MiniConda
> <br> https://docs.anaconda.com/free/miniconda/miniconda-install/

### 명령어로 설치하기 (Anaconda3-2024.02-1 aarch64 버전 기준):

```zsh
bash ./Anaconda3-2024.02-1-Linux-aarch64.sh
```

### 스크립트 진행:

```zsh
In order to continue the installation process, please review the license
agreement.
Please, press ENTER to continue
>>> ENTER

END USER LICENSE AGREEMENT >>> q
(q를 입력하면 라이센스창이 종료되고 다음 질문이 실행됨.)

Do you accept the license terms? [yes|no]
>>> yes

Anaconda3 will now be installed into this location:
/home/"[UserName]"/anaconda3

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below

[/home/"[UserName]"/anaconda3] >>> /home/"[UserName]"/.anaconda3

You can undo this by running `conda init --reverse $SHELL`? [yes|no]
[no] >>> yes
```

### `~/.zshrc` 적용:

```zsh
source ~/.zshrc
```

### Conda Base Environment Auto Activate 해제:

```zsh
conda config --set auto_activate_base false
```

### Shell에서 나가기:

```zsh
exit
```

### Conda 가상환경 만들기:

```zsh
conda create -n “[EnvName]” python=“[Version]”
```

### Conda 가상환경 리스트 보기:

```zsh
conda env list
```

### Conda 가상환경 활성화:

```zsh
conda activate “[EnvName]”
```

### Conda 가상환경에 패키지 설치:

```zsh
conda install “[PakageName]”
```

### Conda 가상환경 비활성화:

```zsh
conda deactivate
```

### Conda 가상환경 제거:

```zsh
conda remove -n “[EnvName]” --all
```
