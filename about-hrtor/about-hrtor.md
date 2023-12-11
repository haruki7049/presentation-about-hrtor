---
title: About hrtor, a scalable line editor's goal
author: haruki7049
paginate: true
slide: true
marp: true
theme: default
class: invert
---

# About hrtor, a scalable line editor's goal

- Date: 2023/12/11
- Author: haruki7049
- hrtor's URL: https://github.com/haruki7049/hrtor

---
<!--
header: About hrtor, a scalable line editor's goal
footer: "This presentation's URL: https://github.com/haruki7049/presentation-about-hrtor"
-->

# Table of this presentation

1. What is hrtor?
2. Goal of hrtor in the future
3. Goal of hrtor:v0.2.0
4. Goal of hrtor:v0.2.1
5. How do we develop hrtor?

---

# What is hrtor?

一言で言うと拡張可能なラインエディター。Lua-langで拡張可能だという機能を備える。現在バージョン0.1.0であり、5種類のデフォルトコマンドが搭載されている。なおかつそのコマンドのエイリアスが設定出来る。
```lua
commands = {
  exit = "q",
  print = "p",
}
```

---

# Goal of hrtor in the future

直近の目標：

- hrtorコマンドのシェル補完。
- hrtorのAPIの実装。

将来の目標：

- スクリーンモードの実装。
    - lessコマンド風のビューアー。
    - vi風のTUIコマンド。
- コンフィグファイルを設定すればNeoVimやEmacsの環境を再現出来る。
- JavaScriptとか他の言語でも設定出来るようにFFIの実装？

---

# Goal of hrtor:v0.2.0

- コマンドを作成可能にする機能の基礎。

例を以下に記載。
```lua
hrtor.commands = {
  print = function()
    hrtor.api.display_buffer();
  end,
  exit = function()
    hrtor.api.quit();
  end,
  ~~~
}
```

---

# Goal of hrtor:v0.2.1

- コマンドを設定すればGNU edのコマンドが一語一句まで再現出来る。

---

# How do we develop hrtor?

この点には議論の余地がある。

使う機能：

- Issue
- PullRequest
- milestone
- GitHub Projects
- GitHub Discussions
- CI/CD

---

すべき事：

- CONTRIBUTING.mdの精査
- APIの構想を練る
- 他には？
