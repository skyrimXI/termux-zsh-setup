# termux-zsh-setup




## Installation 
- Install [termux Emulator](https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk)
- Update and Upgrade packages
```shell
apt-get update && apt-get upgrade
```
## ZSH Installation
- Run
```shell
apt install ZSH
```
- Creating `.zshrc` File
- Configure `zsh` in `.zshrc` File
```shell
nano .zshrc
```
- Paste this configuration for saving commands history
```shell
# History in cache directory:
HISTSIZE=10000
SAVEHIST=10000
HISTFILE=~/.zsh_history
```
- This is used for `TAB` complete
```shell
# Basic auto/tab complete:
autoload -U compinit
zstyle ':completion:*' menu select
zmodload zsh/complist
compinit
_comp_options+=(globdots)
```
- For Promt configuration use `PROMPT`
```shell
PROMPT=%F{yellow}[USER_NAME]%f%F{blue}[%2~]%f'
```
- `USER_NAME`
    - Used for Custom Name
- `%F{CUSTOME_COLOUR}%f`
  - For Custom Colour
- `%2`
  - For how many directory past gonna show on `PROMPT`
- `~`
  - For showing `~` instead of `HOME`

### For `Syntex-highlighting`
### In your ~/.zshrc

Simply clone this repository and source the script:

```zsh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
```

  Then, enable syntax highlighting in the current interactive shell:

```zsh
source ./zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```
### For `syntex-auto-suggestion`
1. Clone this repository somewhere on your machine. This guide will assume `~/.zsh/zsh-autosuggestions`.

    ```shell
    git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
    ```

2. Add the following to your `.zshrc`:

    ```shell
    source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
    ```
### Usefull `alias` for `Termux`
```shell
alias update='apt-get update && apt-get upgrade -y'
alias l='ls -al'
alias c='clear'
alias install='apt-get install'
alias remove='apt-get --purge remove'
alias installed='apt list --installed'
```
### Demo `.zsrc` 

### Just Copy and Paste it to your `.zshrc` file

```shell 

# History in cache directory:
HISTSIZE=10000
SAVEHIST=10000
HISTFILE=~/.zsh_history

# Basic auto/tab complete:
autoload -U compinit
zstyle ':completion:*' menu select
zmodload zsh/complist
compinit
_comp_options+=(globdots)

PROMPT='%F{yellow}[USER_NAME]%f%F{blue}[%2~]%f'
RPROMPT='%F{green}%t◽%W%f'

source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
source ./zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
source /data/data/com.termux/files/home/zsh-syntax-highlighting/zsh-s>

alias update='apt-get update && apt-get upgrade -y'
alias l='ls -al'
alias c='clear'
alias install='apt-get install'
alias remove='apt-get --purge remove'
alias installed='apt list --installed'
```

hffhfh

djfgfb
