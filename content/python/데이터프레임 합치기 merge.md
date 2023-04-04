---
title: "데이터프레임 합치기 merge"
---

key(이름이 같은 열)를 기준으로 두 개의 데이터프레임을 합친다.

이름이 다를 경우 left_on='열 이름', right_on='열 이름'을 지정한다.

합치는 방법
- how='inner' : 교집합(기본값)
- how='left' : left - right
- how='right' : right - left
- how='outer' : 합집합

```python
df_2 = pd.merge(left_df, right_df, on='key', how='inner')
df_3 = left_df.merge(right_df, 
					 left_on='key_left', right_on='key_right', how='left') 
```