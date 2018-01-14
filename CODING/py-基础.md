# Python基础

## 运行环境

- spyder
  - 类似于Rstudio
  - #%%作cell的划分
- jupyter notebook
- pycharm
- visual studio code
  - 使用jupyter插件

## 包的安装

在使用pip install的时候增加参数

```-i https://pypi.tuna.tsinghua.edu.cn/simple```

## 字符串

- 字符串被单引号括起来
- 内容含有\时注意转义

## 错误与异常

```python
  try:
    f = open('myfile.txt')
    s = f.readline()
    i = int(s.strip())
  except OSError as err:
    print("OS error: {0}".format(err))
  except ValueError:
    print("Could not convert data to an integer.")
  except:
    print("Unexpected error:", sys.exc_info()[0])
  else:
    pass # 无异常时执行
```
