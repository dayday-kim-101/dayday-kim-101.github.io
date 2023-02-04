---
layout: post
title:  "윈도우 10 64bit에서 아나콘다로 파이썬 32비트 설치"
categories: python
tags: python, 32bit, x86
author: dayday
---

* content
{:toc}

# 요약
1. 아나콘다 설치
2. 명령 프롬프트(cmd)에서 conda 사용하기
3. conda 명령어로 가상환경 설정
   <br>










# 1. 아나콘다 설치

걍 아래 링크에서 다운 받고, 귀찮으니까 Next 하면서 설치 <br>

[Anaconda Individual Edition](https://www.anaconda.com/products/distribution)

<br>
<br>

# 2. 명령 프롬프트(cmd)에서 conda 사용하기

환경변수 세팅해줘야됨 <br>

제어판 -> 시스템 -> 고급 시스템 설정 -> 환경 변수 -> 사용자 변수의 Path에다가, 다음 2개 추가 <br>

- C:\Users\DK-Room\anaconda3\Scripts

- C:\Users\DK-Room\anaconda3\Library\bin

특히, 두 번째 것 안하면, CondaHTTPError: HTTP 000 CONNECTION FAILED 요딴 에러 남

<br>
<br>

# 3. conda 명령어로 가상환경 설정

> set CONDA_FORCE_32BIT=1

> conda create -n py32

> activate py32

> conda config --env --set subdir win-32

> conda install python=3.8 anaconda

<br>
<br>
