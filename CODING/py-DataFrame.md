# Data Frame 数据结构

## 自我描述属性

```py
df.columns #每个columns对应的keys
df.shape#形状（a，b）; index长度为a; columns数为b
df.index#返回index列表
df.values#返回value二维array
df.head();df.tail()
```

## 选取与修改特定位置的值

```py
df['col0']  #按照列名获取指定的列，返回的是一个Series，其中key是索引，value是该列对应的字段值
df[2:5] #获取第3行~5行，返回一个新的dataframe
df.drop(['a'],axis=1,inplace=False)  #删除指定的列
# inplace=True => 改变原数据
```

只读，不改变原数据。

```py
df.loc[0,'col1']='new value' #正确做法
df[0,'col2']=99 #可能会新增一个列名为(0,col2)的列
```

可以新增不存在的列或行；未赋值部分为NaN。

### 空值填充
```py
DataFrame.fillna(value=None, method=None, axis=None, inplace=False, limit=None, downcast=None, **kwargs)
```

## 数据集的合并或连接或堆叠

列与列，按若干个键，合并： merge

```py
merge(left, right, how='inner',
on=[None,None],left_on=None,right_on=None,
left_index=False, right_index=False, # 使用行索引作为连接键
sort=True,suffixes=('_x', '_y'), copy=True, indicator=False)
```

相同长度，列与列，直接连接： join

```py
join(self, other, on=None, how='left',
lsuffix='', rsuffix='', # 给两边同名的列加上后缀
sort=False)
```
