## Lecture 1

### Coding Part:

```
import argparse
```

> argparse 是 Python 内置的一个用于命令项选项与参数解析的模块

reference：https://docs.python.org/zh-cn/3/library/argparse.html

```python
import argparse

parser = argparse.ArgumentParser(description='Process some integers.')

parser.add_argument('integers', metavar='N', type=int, nargs='+', help='an integer for the accumulator')

parser.add_argument('--sum', dest='accumulate', action='store_const', const=sum, default=max, help='sum the integers (default: find the max)')

args = parser.parse_args()
print(args.accumulate(args.integers))
```

```
$ python argparse_usage.py
usage: argparse_usage.py [-h] [--sum] N [N ...]
argparse_usage.py: error: too few arguments
$ python argparse_usage.py 1 2 3 4
4
$ python argparse_usage.py 1 2 3 4 --sum
10
```



### gym 环境：

参考：https://zhuanlan.zhihu.com/p/26985029

了解几个比较重要的函数

- reset() 重置环境
- render() 展示（可视化）
- step() 模拟物理引擎

可以用 time库 time.sleep(0.2) 加在每一轮的后面来看输出的observation和reward，更好地理解这些函数。



### CEM：

参考：https://gist.github.com/kashif/5dfa12d80402c559e060d567ea352c06