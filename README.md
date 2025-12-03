5 15 20 26 35 66 69 88 =190
441
## 分类
#### 文件处理：
- 20T3 Q5
- 24T3 Q8
- 21T3 Q6
#### 字符串/数组处理：
- 模拟考试 Q3✅
- 24T3pre Q1✅ Q2✅ Q3
- 24T3 Q1✅ Q3✅
- 23T3 Q1 Q3
- 22T2 Q1
- 22T1 Q1
#### 图形打印：
- 22T2 Q3
- 22T1 Q3
## 数据结构
```py
# 双指针
for i in range(n - 1):
    for j in range(i + 1, j):
        pass
while i < len(a) and j < len(b):
    check() i += 1
    j += 1

# 翻转字符串
s[::-1]

# 排序字符串 返回数组
s = sorted(s)

# 栈
stk stk.append(x)  # 初始化
stk.pop()  # 栈顶元素
hh = len(stk) - 1  # 栈顶下标
```
## 语法
```py
s.count(i)  # i在s中出现的次数
s.replace('old', 'new')  # 把s的old替换为new
s.split()  # 默认按空白符分割，忽略连续空白。
s = sorted(s, reverse=True)  # 从大到小
s.index(k)  # k在s第一次出现的位置（首字母为准）

s = ''.join(l)  # 数组转字符串
l = list(s)  # 字符串转数组

a = set(nums)  # 去重
a.add(1)  # 添加
a.remove(1)  # 删除 不存在报错
```
## 库
```py
from itertools import zip_longest, cycle
list(zip([1, 2], ['a', 'b', 'c']))  # 一一配对，允许长度不同

from collections import defaultdict, Counter

# A,B...循环 next(letters)：返回str
from itertools import cycle
import string
letters = cycle(string.ascii_uppercase)
for i in range(total):  # 动态提取字母
    myLetters += next(letters)

# 竖着打印数组
from itertools import zip_longest
cols = [' * ', '***']
for l in zip_longest(*cols):
    print(' '.join(l).rstrip())
```
## 模版：字符串、数组处理
重复某数字，个数是该数的下一个数，最后一个用第一个数
```py
s = s.replace('0', '')
s = s + s[0]
res = ''
for i in range(1, len(s)):
    res += s[i - 1] * int(s[i])
return res
```
二维数组，对内部数组排序，内部数组大小、顺序不能乱，其中数字升序排列
```py
lengths = []  # 存每个二维数组的长度
l = []  # 存二维数组的展开
for i in range(len(myList)):
    lengths.append(len(myList[i]))
    l.extend(myList[i])
l = sorted(l)
res = []
for i in lengths:
    res.append(l[:i])
    l = l[i:]
return res
```
去除序列重复数字
```py
s = str(number)
res = s[0]
for i in range(1, len(s)):
    if s[i] != s[i - 1]
    res += s[i]
return res

# 保留满足某性质：
for i in range(len(s)):
    if check():
        res += s[i]
```
按顺序匹配目标串中是否含有模版串，中间可有其他字符
```py
def matches(target, words):
    i = 0
    for j in range(len(words)):
        if i < len(target) and words[j] == target[i]:
            i += 1
    return i == len(target)
```
负数处理
```py
is_negative = False
if a < 0:
    is_negative = True
    a = a[1:]  # 数字：a = a * -1
return -a if is_negative else a
```
一串数，从大到小输出其中的单个奇数
```py
res = ''
for i in range(s):
    if int(s[i]) % 2 != 0:
        res += s[i]
if not res:
    return 0
res = int(''.join(sorted(res, reverse=True)))
```
输出第三大的数：lc414
```py
nums = set(nums)
if len(nums) > 3:
    nums.remove(max(nums))
    nums.remove(max(nums))
    return max(nums)
```
字符串加法：lc415
- py内置最高int转字符串的最大位数：4300
```py
sys.set_int_max_str_digits(10000)
return str(int(num1) + int(num2))
```
中心扩展算法，找出最长的水仙花子串长度：lc5
```py
def expand(s: str, l: int, r: int):
    while l >= 0 and l < len(s) and s[l] == s[r]:
        l -= 1
        r += 1
    return (r - 1) - (l + 1) + 1

for i in range(len(s)):
    odd = expand(s, i, i)
    even = expand(s, i, i + 1)
```
进制转换：lc67
```py
a = int(s, 2)  # 二进制数字串转十进制
a = bin(b)[2:]  # 十进制数字转二进制
```
输入n，输出n个数，每一个是前一个数加上该数的下标
```py
res = []
cnt = 1
for i in range(n):
    cnt += i
return tuple(res), tuple(res[::-1])
```
## 模版：文件处理
基础
```py
with open(filename) as f:
    lines = []
    for line in f:
        lines.append(line.strip())  # 读取所有行，存到数组里
```
## 库
```py
import math
math.floor()  # 向下取整
math.ceil()  # 向上取整
math.sqrt()  # 开平方
```