---
layout: post
title:  "맥북에서 부팅 시 쥬피터 자동 실행"
categories: tip
---

# 요약
1. 애플 스크립트 만들기
2. 스크립트 로드하기
<br>

# 1. 애플 스크립트 만들기

```shell
$ cd ~/library/LaunchAgents/

$ touch com.jupyter.server.plist

$ vi com.jupyter.server.plist 
```
<br>

아래를 복사하여 붙여넣기
```xml
<?xml version="1.0" encoding="UTF-8"?>
<plist>
  <dict>
    <key>KeepAlive</key>
    <true />
    <key>RunAtLoad</key>
    <true />
    <key>Label</key>
    <string>com.jupter.server</string>
    <key>ProgramArguments</key>
    <array>
      <string>/Library/Frameworks/Python.framework/Versions/3.7/bin/jupyter-notebook</string>
    </array>
  </dict>
</plist>
```
string 태그는 jupyter-notebook 명령어가 실행되는 위치입니다.
-  anaconda 사용자
```shell
/Users/dayday/anaconda3/bin/jupyter-notebook
```
-  파이썬 설치하신 사용자 혹은 이미 설치되어 있는 사용자
```shell
$ export 하면, 아래와 같은 결과가 나오는데, Python 부분 찾아서 들어가보시면, jupyter-notebook 명령어 보입니다.
...
declare -x PATH="...  /Library/Frameworks/Python.framework/Versions/3.7/bin  ..."
...
```
<br>
<br>

# 2. 스크립트 로드하기

```shell
$ launchctl load ~/Library/LaunchAgents/com.jupyter.server.plist 
```

굳이 재부팅해서, 확인하실 필요없이 여기까지 하면 잘 됩니다!