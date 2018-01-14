# 数据文件的读取与存储

## 读取CSV文件为DataFrame

- usercols 指定读取的列
- dytpe 指定数据类型
- skiprows
  - 参数int：从开始时跳过的行数
  - 参数callable：跳过传入行标后返回为True的行

```python
data = pd.read_csv('data.csv',usecols=[0,1,2],
dtype={'col1': 'category'},
skiprows=lambda x: x % 2 != 0)
```

## 将DataFrame保存为csv

```py
to_csv(path_or_buf=None, sep=",", na_rep='', float_format=None, columns=None, header=True,
index=True, # 若T，csv第一列将是DF的index，默认列名为空。
index_label=None, mode='w', encoding=None, compression=None, quoting=None, quotechar='"', line_terminator='\n', chunksize=None, tupleize_cols=None, date_format=None, doublequote=True, escapechar=None, decimal='.')
```

## DataFrame的序列化

```python
df=pd.DataFrame(a)#a是一个二维的NumPy数组
df.to_pickle("filename")
df=pd.read_pickle('filename')
```

## Pickle模块的基本使用
```py
#使用pickle模块将数据对象保存到文件

import pickle

data1 = {'a': [1, 2.0, 3, 4+6j],
         'b': ('string', u'Unicode string'),
         'c': None}
selfref_list = [1, 2, 3]
selfref_list.append(selfref_list)
output = open('data.pkl', 'wb')

# Pickle dictionary using protocol 0.
pickle.dump(data1, output)

# Pickle the list using the highest protocol available.
pickle.dump(selfref_list, output, -1)
output.close()

#使用pickle模块从文件中重构python对象

import pprint, pickle

pkl_file = open('data.pkl', 'rb')

data1 = pickle.load(pkl_file)
pprint.pprint(data1)

data2 = pickle.load(pkl_file)
pprint.pprint(data2)

pkl_file.close()
```