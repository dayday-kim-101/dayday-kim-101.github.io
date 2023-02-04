---
layout: post
title:  "Mac에서 IntelliJ React-native 설정하기"
categories: IDE
tags: intelliJ, react-native
author: dayday
---

* content
{:toc}

# 요약
1. Install nvm
2. Install node.js
3. Install yarn
4. Install React-Native CLI
5. Open IntelliJ Project
6. Set Run on IntelliJ
   <br>










# 1. Install nvm

```shell
1. $ export NVM_DIR="$HOME/.nvm" && (
  git clone https://github.com/nvm-sh/nvm.git "$NVM_DIR"
  cd "$NVM_DIR"
  git checkout `git describe --abbrev=0 --tags --match "v[0-9]*" $(git rev-list --tags --max-count=1)`
) && \. "$NVM_DIR/nvm.sh"

2. $ vi ~/.bash_profile

아래를 추가하고 저장(:wq)

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm

3. $ source ~/.bash_profile
```
<br>
<br>

# 2. Security Group에 http 포트(80번) 추가

```shell
1. $ nvm install --lts
버전 지정해서 설치해도 됨
ex) $ nvm install 12

node.js 설치 여부 확인
ex) $ nvm ls

원하는 버전 사용하기
ex) $ nvm use 12
```

<br>
<br>

# 3. Install yarn

```shell
1. $ npm install -g yarn
```

<br>
<br>

# 4. Install React-Native CLI

```shell
1. $ npx create-react-app dayday-app

2. $ cd dayday-app
```

<br>
<br>

# 5. Open IntelliJ Project

Preference -> Languages & Frameworks -> Node.js and Npm 에서

- Package Manager를 yarn으로

<br>
<br>

# 6. Set Run on IntelliJ

Run -> Edit Configuration -> 왼쪽 상단 + -> npm 추가하기

- package.json을 현재 디렉토리인지 확인 정도

- Scripts를 start로 설정

<br>
<br>

# 7. Check Run

Run하면 됨.

<br>
<br>
