## bash を zsh にして、Starshipでおしゃれなプロンプトのターミナルに

### bash to zsh 

bash で env の設定 （rbenv） をすると、もともとは
```
# ~/.bashrc

export PATH="$PATH:$HOME/.rbenv/bin"
eval "$(rbenv init -)"
```
こう。  
anyenv なので、
```
# ~/.bashrc

if [ -d ${HOME}/.anyenv ] ; then
    export PATH="$HOME/.anyenv/bin:$PATH"
    eval "$(anyenv init -)"
fi
```
こうなる。  
しかし、 ``~/.zshrc`` にそのままコピペするとエラー。なので、zshにするときには、
```
# ~/.zshrc

if [ -d ${HOME}/.anyenv ] ; then
    export PATH="$HOME/.anyenv/bin:$PATH"
    eval "$(anyenv init -zsh)"
fi
```
これでOK。


### Starship

Starship とは、  
Starship  
[https://starship.rs/](https://starship.rs/)  

starship/starship: ☄🌌️ The cross-shell prompt for astronauts.  
[https://github.com/starship/starship](https://github.com/starship/starship)  


Installation
```
$ brew cask install starship
$ vim ~/.zshrc

# ~/.zshrc

eval "$(starship init zsh)"
```


デフォルトでコマンド行後ろに入る空行を無効に
```
$ touch ~/.config/starship.toml
$ echo "add_newline = false" >> ~/.config/starship.toml
```

