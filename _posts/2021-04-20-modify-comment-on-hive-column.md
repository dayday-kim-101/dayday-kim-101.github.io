---
layout: post
title:  "hive 테이블 comment 수정하기"
categories: Hive
---

# 요약
1. beeline 접속
2. 명령어 실행
   <br>

# 1. beeline 접속

> hive 연결 계정 혹은 hive 계정에 접속해서 다음 코드 실행
> <br>
> ```shell
> $ beeline
> ```

-  커멘드 앞에 이름이 막 jdbc, hive 어쩌구로 되어있어야됨
-  그냥 beeline이라고 되어있으면 제대로 연결 안된거임
   <br>



<br>

# 2. 명령어 실행

```shell
jdbc:hive2://...> ALTER TABLE temp.dayday_test_del_column CHANGE mem_no mem_no STRING COMMENT 'asdasd';
```

주의사항은 파티션키가 적용된 컬럼은 코멘트 수정이 안됨!
