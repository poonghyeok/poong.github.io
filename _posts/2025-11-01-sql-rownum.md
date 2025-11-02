---
title: SQL ROW NUM
author: poonghyeok
date: 2025-11-01
category: ["SQL", "MYSQL", "ORACLE"]
layout: post
mermaid: true
---

#### MYSQL에서 ROW_NUMBER() 사용
```sql
select user_id
, country
, row_number() over (partition by country order by user_id)
from user_account;
```

> `mysql`에서 `row_number`는 window 내에서 순서를 의미한다.
그러면 `rank()`나 `dense_rank()` 랑 똑같은 거 아니냐라고 생각할 수 있는데, 같은 값에 대한 처리에서 차이가 있다.

#### ORACLE 19c에서 ROWNUM 사용
```sql
SELECT rownum, payment_id, amount, payment_date 
FROM  payment WHERE rownum < 10 
ORDER BY amount, payment_date;
```

> window가 아닌 전체 결과에 대한 행 시퀀스