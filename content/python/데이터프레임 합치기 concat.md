---
title: "데이터프레임 합치기 concat"
---

## 두 개 데이터프레임 만들기

```python
num1 = np.arange(1, 13)
num2 = np.arange(13,25)
num1 = num1.reshape(3, 4)
num2 = num2.reshape(3, 4)
df1 = pd.DataFrame(num1, columns=['col1','col2','col3','col4'])
df2 = pd.DataFrame(num2, columns=['col1','col2','col3','col4'])
```

![[python/images/Pasted image 20230404220939.png]]
![[python/images/Pasted image 20230404220953.png]]
## 행 방향(아래로) 합치기

```python
df = pd.concat([df1, df2])
```

![[python/images/Pasted image 20230404221045.png]]
index가 변경되지 않고 원래의 인덱스를 그래도 갖고 있다. 합칠 때 이를 초기화하려면 ignore_index = true를 입력한다.

```python
df = pd.concat([df1, df2], ignore_index=True)
```

![[python/images/Pasted image 20230404221613.png]]
## 열 방향(옆으로) 합치기

```python
df_col = pd.concat([df1, df2], axis=1)
```

![[python/images/Pasted image 20230404221356.png]]

## 합치는 데이터프레임의 행, 열 개수가 같지 않을 경우

```python
num3 = np.arange(25, 37)
num3 = num3.reshape(4, 3)
df3 = pd.DataFrame(num3, columns=['col2', 'col4', 'col5'])
```

![[python/images/Pasted image 20230404222106.png]]

```python
df_na = pd.concat([df2, df3])
```

![[python/images/Pasted image 20230404222215.png]]
df2에는 col5가 없고, df3에는 col1, col3가 없다. 없는 값은 nan으로 채워진다.

## join="inner/outer" 기준으로 교집합/합집합

### 컬럼명 기준으로 inner join

```python
df_inner = pd.concat([df1, df3], join='inner')
```

![[python/images/Pasted image 20230404224006.png]]

### 컬럼명 기준으로 outer join

```python
df_outer = pd.concat([df1, df3], join='outer')
```

![[python/images/Pasted image 20230404224244.png]]

### 인덱스 기준으로 inner join

```python
df_inner = pd.concat([df1, df3], axis=1, join='inner')
```

![[python/images/Pasted image 20230404223738.png]]

### 인덱스 기준으로 outer join

```python
df_outer = pd.concat([df1, df3], axis=1, join='outer')
```

![[python/images/Pasted image 20230404223823.png]]

