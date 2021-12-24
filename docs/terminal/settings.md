---
tags:
  - terminal
  - environment
---

# ターミナルのカスタマイズ

prezto + enhancd を使ってきたが、promptを使うメリットが薄くなってきたので、整理しなおそうとした。

最新の zsh が使えるように、brewで `zsh` をinstallし、ログインshellを更新する。以下のエラーが出たので、[エラーが起こる場合](https://qiita.com/ayihis@github/items/88f627b2566d6341a741)を参考に `chmod` で権限をつけて解消。

```zsh
zsh compinit: insecure directories, run compaudit for list.
Ignore insecure directories and continue [y] or abort compinit [n]?
```

```zsh
brew install zsh
nvim /private/etc/shells
chmod 755 /opt/homebrew/share/zsh/site-functions
chmod 755 /opt/homebrew/bin/zsh
chsh -s /opt/homebrew/bin/zsh
```

ホーム直下に `dotfiles` を作った。

```zsh
mkdir ~/dotfiles
cd ~/dotfiels
```

この後、`.zprezto` の中身から、`.zshrc`,
`.zshenv`, `.zpreztorc`
をコピーして、ホーム直下にシンボリックリンクを貼る

```zsh
ln -sfnv dotfiles/.zshrc ~/.zshrc
ln -sfnv dotfiles/.zshenv ~/.zshenv
```

同じ要領で、 `.vimrc` `.tmux.conf` `.latexkrc` `.gitconifig` もdotfilesで管理するようにした

## 参考文献

- [zsh-tutorial](https://zenn.dev/k4zu/articles/zsh-tutorial)
- [dotfiles の育て方](https://qiita.com/reireias/items/b33b5c824a56dc89e1f7)
