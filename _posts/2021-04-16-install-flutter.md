---
layout: post
title:  "Flutter 설치하기 on MacOS"
categories: tip
tags:  flutter
author: dayday
---

* content
{:toc}


# 요약
1. 미리 준비 하기
2. 설치하기
   <br>







# 1. 미리 준비 하기

-  Android Studio 설치
-  Xcode 설치
-  Chrome 설치
-  IntelliJ 설치
-  cocoapods 설치
<br>


> Android 설치
> <br>
> [여기서](https://developer.android.com/studio/index.html) 다운로드 후 바로 설치
> <br>
> 설치 하고 한 번 꼭 실행해야 합니다!

<br>

> Xcode 설치
> <br>
> AppStore에서 Xcode 검색 후 설치
> <br>
> 설치 하고 한 번 꼭 실행해야 합니다!
> <br>
> 그리고 다음 명령어 실행
> <br>
> ```shell
> $ sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
> $ sudo xcodebuild -runFirstLaunch
> ```

<br>

> Chrome 설치
> <br>
> AppStore에서 Chrome 검색 후 설치
> <br>
> 설치 하고 한 번 꼭 실행해야 합니다!

<br>

> cocoapods 설치
> <br>
> 다음 명령어 실행
> <br>
> ```shell
> $ sudo gem install cocoapods
> ```

<br>

# 2. 설치하기

사실 [여기서](https://flutter.dev/docs/get-started/install/macos) 하라는대로 하는게 가장 좋아요!

### 2-1. 다운로드

그냥 [여기서](https://flutter.dev/docs/get-started/install/macos) 다운로드



```shell
$ cd ~/development
$ unzip ~/Downloads/flutter_macos_2.0.4-stable.zip
```

<br>

```shell
$ export PATH="$PATH:`pwd`/flutter/bin"
```

<br>

```shell
$ flutter doctor
```