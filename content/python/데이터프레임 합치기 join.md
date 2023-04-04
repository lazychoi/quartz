---
title: "데이터프레임 합치기 join"
---

행 인덱스를 기준으로 데이터프레임을 합친다. 즉, 열 방향(우측)으로 합친다.

left join이 기본값이다.

주의!! 두 데이터프레임에 <mark style="background: #FFB8EBA6;">이름이 같은 컬럼명이 있으면 안 된다</mark>. 

```python
df = left_df.join(right_df)
```
