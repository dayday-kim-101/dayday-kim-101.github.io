---
layout: post
title:  "드디어 성공한 AWS에 웹 서버 띄우기"
categories: web
tags: web server, aws
author: dayday
---

* content
{:toc}

# 요약
1. AWS EC2 인스턴스 생성
2. Security Group에 http 포트(80번) 추가 
3. EC2 SSH 접속 with pem
4. EC2 에서 Apache 설치하고 실행
5. 로컬에서 scp로 html 파일들 EC2에 옮기기
6. EC2에 옮겼던 파일들을 /var/www/html/ 에 옮기기
7. 크롬에서 공인 IP로 접속되는지 확인하기
   <br>










# 1. AWS EC2 인스턴스 생성

```shell
1. console.aws.amazon.com/ 접속
2. EC2 들어가기
3. Launch instance 클릭
4. AMI 선택
5. t2.micro 선택
6. Auto-assign Public IP 만 Enable
7. 나머지 다 Next
```
<br>
<br>

# 2. Security Group에 http 포트(80번) 추가

```shell
1. 해당 instance ID 클릭
2. Security 탭에서 해당 Security Groups 클릭
3. Edit inbound rules 클릭
4. Add rule 클릭
5. Type에 HTTP 선택하고, Souce는 0.0.0.0/0 선택하고 저장
```

<br>
<br>

# 3. EC2 SSH 접속 with pem

```shell
$ ssh -i "web_dayday.pem" ec2-user@ec2-15-164-216-92.ap-northeast-2.compute.amazonaws.com
```

<br>
<br>

# 4. EC2 에서 Apache 설치하고 실행

```shell
1. $ sudo yum install httpd
2. $ sudo service httpd start
```

<br>
<br>

# 5. 로컬에서 scp로 html 파일들 EC2에 옮기기

```shell
$ scp -i aws_keypairs/web_dayday.pem -r workspace/web_apps/test_bootstrap/* ec2-user@ec2-15-164-216-92.ap-northeast-2.compute.amazonaws.com:/home/ec2-user
```

<br>
<br>

# 6. EC2에 옮겼던 파일들을 /var/www/html/ 에 옮기기

```shell
$ sudo cp -r test_bs/* /var/www/html/
```

<br>
<br>

# 7. 크롬에서 공인 IP로 접속되는지 확인하기

![](https://github.com/dayday-kim-101/dayday-kim-101.github.io/blob/master/images/2023-02-04-launch-aws-webserver/launch_test_web_page.png?raw=true)

<br>
<br>
