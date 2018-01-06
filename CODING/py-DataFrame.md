# Data Frame 数据结构

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
