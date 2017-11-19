layout: post
title: Python随机生成32位字符串用于API秘钥
date: 2017-11-19
categories: blog
tags: pythom

description: 使用python随机生成32位字符串
---
# Python随机生成32位字符串用于API秘钥

在配置企业微信支付API的过程中，32位字符作为API秘钥，本想使用连续的英文和数字作为API秘钥，考虑到涉及到钱，其安全性还是需要高一些。 最近刚好在学习Python，就尝试着写一下随机生成32位字符串的函数：

```
from random import Random
def random_str(randomlength=32):
    str = ''
    chars = 'AaBbCcDdEeFfGgHhIiJjKkLlMmNnOoPpQqRrSsTtUuVvWwXxYyZz0123456789'
    length = len(chars) - 1
    random = Random()
    for i in range(randomlength):
        str+=chars[random.randint(0, length)]
    return str
print (random_str(32))
```
32位字符串的类型，可根据chars赋值的字符串来进行调整，本例子中目前包含大小写字符和数字。

