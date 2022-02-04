---
layout: post
title:  "로컬에서 jekyll 블로그(github.io 블로그) 돌려보기 on Windows"
categories: blog
---

# 요약
1. 루비 설치
2. gem으로 필요한 패키지 설치
3. bundle install을 통해 gemfile내 패키지들 설치하기
4. 로컬서버 실행


# 1. 루비 설치

루비 설치는 [홈페이지](https://rubyinstaller.org/downloads/archives/) 에서 본인이 원하는 버전을 다운받으면 된다. <br>

본인은 2.5.5-1 버전을 다운로드했다. <br>
(Gemfile에서 jekyll 은 4.0.0 이상이 필요해서 루비가 2.5이상 버전이 필요했고, public_suffix가 4.0.3 가 필요해서 루비가 2.7이하 버전이 필요했다.) <br>

![](https://github.com/dayday-kim-101/dayday-kim-101.github.io/blob/master/images/2022-01-30-blog-local-jekyll-serve/1_1_download_ruby_version.png?raw=true) <br>
<br>
<br>

<br>

# 2. gem으로 필요한 패키지 설치

gem은 루비에서 패키지를 관리하는 툴이다. (파이썬에서 pip 느낌) <br>

필요한 패키지 설치에 앞서, 루비 전용 프롬프트를 설치해서 진행해야한다. <br>

![](https://github.com/dayday-kim-101/dayday-kim-101.github.io/blob/master/images/2022-01-30-blog-local-jekyll-serve/2_1_run_command_prompt_with_ruby.png?raw=true) <br>
<br>

![](https://github.com/dayday-kim-101/dayday-kim-101.github.io/blob/master/images/2022-01-30-blog-local-jekyll-serve/2_2_run_command_on_ruby_prompt.png?raw=true) <br>
<br>

그리고 ***<span style="color:rgb(201, 0, 22)"> git repository 경로에서 패키지 설치를 진행 </span>*** 해야한다.

필요한 패키지 설치 리스트는 다음과 같다. <br>
1. \> gem install jekyll
2. \> gem install bundler
<br>
<br>

<br>

# 3. bundle install을 통해 gemfile내 패키지들 설치하기

git repository 경로(gemfile 있는 경로)에서 bundle install 실행하면, 쭉 설치되고, 에러가 나면 메세지에 따라 해결한다.

![](https://github.com/dayday-kim-101/dayday-kim-101.github.io/blob/master/images/2022-01-30-blog-local-jekyll-serve/3_1_install_gem_packages.png?raw=true) <br>
<br>
<br>

<br>

# 4. 로컬서버 실행

git repository 경로에서 다음 명령어 실행 <br>

> ```shell
> F:\Workspace\github\dayday-kim-101.github.io> bundle exec jekyll serve --port 5000 --trace 
> ```

<br>

포트는 기본 포트보다 5000번을 추천합니다. 4000번이 기본인데 이상하게 어떤 프로세스가 잡고있는지 서버가 뜨질 않았다. <br>

![](https://github.com/dayday-kim-101/dayday-kim-101.github.io/blob/master/images/2022-01-30-blog-local-jekyll-serve/4_1_run_local_jekyll_server.png?raw=true) <br>
<br>

http://127.0.0.1:5000 로 들어가면 다음과 같이 접속된다. <br>
(이렇게하면, push 안하고도 결과를 바로 확인 할 수 있다.) <br>

![](https://github.com/dayday-kim-101/dayday-kim-101.github.io/blob/master/images/2022-01-30-blog-local-jekyll-serve/4_2_result_run_local_jekyll_server.png?raw=true) <br>
<br>

