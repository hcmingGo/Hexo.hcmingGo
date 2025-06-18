---
title: 牛客网刷题总结
date: '2025-06-12 17:03:39'
updated: '2025-06-18 10:51:01'
permalink: /post/niukecom-s-questionwriting-summary-cmo2o.html
comments: true
toc: true
---



# 牛客网刷题总结

0613：

HJ [字符串加解密_牛客题霸_牛客网](https://www.nowcoder.com/practice/2aa32b378a024755a3f251e75cbf233a?tpId=37&tags=&title=&difficulty=0&judgeStatus=0&rp=0&sourceUrl=https%3A%2F%2Fwww.nowcoder.com%2Fexam%2Foj%3FquestionJobId%3D2%26subTabName%3Donline_coding_page) 中等题

‍

HJ31 [单词倒排_牛客题霸_牛客网](https://www.nowcoder.com/practice/81544a4989df4109b33c2d65037c5836?tpId=37&tags=&title=&difficulty=0&judgeStatus=0&rp=0&sourceUrl=https%3A%2F%2Fwww.nowcoder.com%2Fexam%2Foj%3FquestionJobId%3D2%26subTabName%3Donline_coding_page)

1. isalpha() 判断元素是否为字母，否则则替换为空字符
2. replace()函数的使用
3. 列表的元素不换行输出的方法

```python
a = input()
for i in a:
    if not i.isalpha():
        a = a.replace(i,' ')
b = a.split()
print(*b[::-1])
```

‍

HJ32 [密码截取_牛客题霸_牛客网](https://www.nowcoder.com/practice/3cd4621963e8454594f00199f4536bb1?tpId=37&tags=&title=&difficulty=0&judgeStatus=0&rp=0&sourceUrl=https%3A%2F%2Fwww.nowcoder.com%2Fexam%2Foj%3FquestionJobId%3D2%26subTabName%3Donline_coding_page) 中等题

回文子串类题型：

```python

# 从右到左，对每个字符进行遍历处理，并且每个字符要处理两次，因为回文子串有两种情况：
# ABA型：只需要从当前字符向两边扩散，比较左右字符是否相等，找出以当前字符为中心的最长回文子串长度
# ABBA型：只需要从当前字符和下一个字符向两边扩散，比较左右字符是否相等，找出以当前字符和下一个字符为中心的最长回文子串长度
# 最后比对两种类型的长度，取自较长的长度
out = 0

for i in range(0, len(s)):  # 双指针
    k = i - 1
    j = i + 1
    len_ABA = 1
    while k >= 0 and j < len(s):
        if s[k] == s[j]:
            k -= 1
            j += 1
            len_ABA += 2
        else:
            break
    
    k = i
    j = i + 1
    len_ABBA = 0
    while k >= 0 and j < len(s):
        if s[k] == s[j]:
            k -= 1
            j += 1
            len_ABBA += 2
        else:
            break
     
    now_len = max(len_ABA, len_ABBA)
    if out <now_len:
        out = now_len
print(out)
```
