# Install ZSH Shell

Prerequisities:

```
apt install -y curl git fonts-font-awesome htop zsh
```

Optional:

```
git config --global http.sslVerify false
```

Install ZSH:

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Change default shell for current or a specific user:

```
chsh -s /bin/zsh # Current user
chsh -s /bin/zsh <username>
```

Install p10k:

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
echo 'source ~/.oh-my-zsh/custom/themes/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
p10k configure
```

Additional aliases:

```
alias distro='cat /etc/*-release'.
alias ll='ls -lha --color=always'
alias myip='curl http://ipecho.net/plain; echo'
alias reload='source ~/.zshrc'
```

Edit `.p10k.zsh` and comment `context` section:

https://www.reddit.com/r/zsh/comments/e416xp/prompt_elements_with_powerlevel10k/?rdt=49370

```
typeset -g POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(
  ...
  context                 # user@hostname
  ...
)
```
