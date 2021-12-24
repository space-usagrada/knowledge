---
tags:
  - M1 Mac
  - environment
---

# M1 Mac 用

基本的には[このサイト](https://isapplesiliconready.com)を見ればどのアプリが Native 対応しているのかわかる。

homebrew, LaTeX, Docker も M1 対応したので今までの知見がそのまま使える。

LaTeX の install 方法(homebrew)

```bash
brew install mactex-no-gui --cask
sudo tlmgr update --self --all
sudo tlmgr paper a4
```

Node.JS は gcc を brew で入れていると nodebrew, nodenv でのコンパイルが(3月頃は)通らなかった。
gcc と M1 の相性は良くなさそう。（FFIなども失敗する）
