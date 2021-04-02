# .config
Personal settings for different source environments

## First installation

### iTerm2
https://iterm2.com/downloads/stable/latest

### Oh-My-Zsh
https://ohmyz.sh/#install

### brew
```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### xcode tools
```
sudo xcode-select --install
```

### ssh
```zsh
$ ssh-keygen -t ed25519 -C "email@domain.com"
```
```zsh
$ ssh-add -K ~/.ssh/key
```
```zsh
$ pbcopy < ~/.ssh/key.pub
```
Add that ssh key on [GitHub](https://github.com/settings/ssh/new).

### gpg
```zsh
$ brew install gnupg
```
```zsh
$ gpg --full-generate-key
```
```zsh
$ gpg --list-secret-keys --keyid-format LONG
/Users/hubot/.gnupg/secring.gpg
------------------------------------
sec   4096R/<GPG KEY ID> 2016-03-10 [expires: 2017-03-10]
uid                          Hubot 
ssb   4096R/42B317FD4BA89E7A 2016-03-10
```
```zsh
$ gpg --armor --export <GPG KEY ID>
-----BEGIN PGP PUBLIC KEY BLOCK-----
...
-----END PGP PUBLIC KEY BLOCK-----
```
copy the output and paste that gpg key on [GitHub](https://github.com/settings/gpg/new)
```zsh
$ git config --global commit.gpgsign true
```
```zsh
$ git config --global user.signingkey <GPG KEY ID>
```
```zsh
$ echo 'export GPG_TTY=$(tty)' >> ~/.zshrc
```

### nvm

```zsh
brew install nvm
```

export NVM_DIR="$HOME/.nvm"
  [ -s "/usr/local/opt/nvm/nvm.sh" ] && . "/usr/local/opt/nvm/nvm.sh"  # This loads nvm
  [ -s "/usr/local/opt/nvm/etc/bash_completion.d/nvm" ] && . "/usr/local/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion
