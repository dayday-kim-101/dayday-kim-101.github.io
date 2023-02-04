---
layout: post
title:  "나만의 도메인으로 나만의 웹 사이트 띄우기"
categories: web
tags: web, aws
author: dayday
---

* content
{:toc}

# 요약
1. 도메인 구매
2. 도메인 구매 한 곳에서 레코드 설정
3. AWS Elastic IP 생성
4. AWS Route 53 생성 및 설정
5. EC2에 원하는 웹 사이트 업로드하면, 해당 도메인으로 연결됨
   <br>










# 1. 도메인 구매

[웹 사이트 띄우는 환경]

- AWS EC2



[준비물]

- AWS 계정(Free Tier 추천, 보통 가입하면 Free Tier임)

- AWS의 서비스들 (EC2, Elastic IP, Route 53)

- 도메인 구매 (본인은 가비아에서 도메인 샀음, 연 2만원)

<br>

> www.gabia.com/ 에서 회원가입 -> 원하는 도메인 검색 후 구매

<br>
<br>

# 2. 도메인 구매 한 곳에서 레코드 설정

- My 가비아 -> DNS 관리툴 -> DNS 설정 ->

타입 : A, 호스트 : www, 값 : AWS Elastic IP에서 할당 받은 IP 주소 (3번에서 해봐요~)

![](https://github.com/dayday-kim-101/dayday-kim-101.github.io/blob/master/images/2023-02-04-my-website-on-my-domain/dns_setting.png?raw=true)

<br>
<br>

# 3. AWS Elastic IP 생성

<br>
<br>

# 4. AWS Route 53 생성 및 설정

- NS, SOA 타입은 바로 만들어짐

- NS에서 값을 가비아에서 산, 네임서버 주소로 바꿔줌

- A 타입은 www.asdsadsadsad.com  이라고 하지말고, asdsadsadsad.com  설정하고, Value는 Elastic IP 적어주자

- CNAME은 www.asdsadsadsad.com 라고 해주고, value 에다가  asdsadsadsad.com   라고 적어줌

![](https://github.com/dayday-kim-101/dayday-kim-101.github.io/blob/master/images/2023-02-04-my-website-on-my-domain/set_aws_route_53.png?raw=true)

<br>
<br>

# 5. EC2에 원하는 웹 사이트 업로드하면, 해당 도메인으로 연결됨

<br>
<br>
 
# References

- [도메인을_IP_주소에_연결하는_방법과_nslookup](https://medium.com/@bdv111/%EB%8F%84%EB%A9%94%EC%9D%B8%EC%9D%84-ip-%EC%A3%BC%EC%86%8C%EC%97%90-%EC%97%B0%EA%B2%B0%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EA%B3%BC-nslookup-9e70a32eec57)
- [AWS_외부_도메인_연결_방법](http://makebct.net/aws-%EC%99%B8%EB%B6%80-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%97%B0%EA%B2%B0-%EB%B0%A9%EB%B2%95-1/?cat=989/)

<br>
<br>
