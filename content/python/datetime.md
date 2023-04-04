---
title: "datetime"
---

## 기본 사용법

```python
from datetime import datetime
now = datetime.now()
print(now)              # 2023-04-03 18:53:46.772618
print(now.year)         # 2023
print(now.month)        # 4
print(now.day)          # 3  
print(now.weekday())    # 0-월요일
print(now.hour)         # 18
print(now.minute)       # 56
print(now.second)       # 46
print(now.microsecond)  # 772618(마이크로초: 백만분의 1초)
```

주의할 점은 요일을 구하면 숫자를 반환한다는 것이다. 월요일이 0이고 일요일이 6이다.

## 시간과 문자열을 상호 변환하기

- time → string : <mark style="background: #FFB8EBA6;">datetime변수.strftime('포맷')</mark> string from time. 
- string → time : <mark style="background: #FFB86CA6;">datetime.strptime('시간문자열', '포맷)</mark> string parse time. 

```python
from datetime import datetime
now = datetime.now()
print( now.strftime('%Y/%m/%d') )   # 2023/04/03

str = '2023-4-3'
print( datetime.strptime(str, "%Y-%m-%d") )   # 2023-04-03 00:00:00
```

[날짜/시간 관련 포맷 코드 설명서 보기](https://docs.python.org/ko/3.10/library/datetime.html#strftime-and-strptime-behavior)

## 날짜와 시간 연산

### 날짜 - 날짜

```python
dt1 = datetime(2022,1,1)
dt2 = datetime(2023,1,1)
print( dt2 - dt1 )    # 365 days, 0:00:00
```

### 날짜 + 기간

- 날짜, 초 단위 연산 : datetime.timedelta()
- 월 단위 연산 : dateutil.relativedelta.relativedelta()

```python
import datetime
dt1 = datetime.datetime(2022,12,31)
dt2 = dt1 + datetime.timedelta(days = 1)
print( dt2 )
# 2023-01-01 00:00:00

from dateutil.relativedelta import relativedelta
dt3 = dt1 + relativedelta(months = 1)
print( dt3 )
# 2023-01-31 00:00:00
```

주의!! timedelta 메소드는 datetime.datetime이 아니라 datetime에 있다.

