---
title: "pandas loc iloc 차이"
---

- loc : 인덱스 이름 사용, 범위의 끝 포함
- iloc : 위치 인덱스 사용, 범위의 끝 미포함

```python
import pandas as pd

dic_data = {'col1':[1,2,3], 'col2':[4,5,6], 'col3':[7,8,9]}
df = pd.DataFrame(dic_data)
df.index = ['a','b','c']
print( df.loc['a':'c'] )
print( df.iloc[0:2] )
#   col1  col2  col3
#a     1     4     7
#b     2     5     8
#c     3     6     9
#   col1  col2  col3
#a     1     4     7
#b     2     5     8
```

