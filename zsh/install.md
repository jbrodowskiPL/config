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
p10k configure
```

Additional aliases:

```
alias distro='cat /etc/*-release'.
alias ll='ls -lha --color=always'
alias myip='curl http://ipecho.net/plain; echo'
alias reload='source ~/.zshrc'
```