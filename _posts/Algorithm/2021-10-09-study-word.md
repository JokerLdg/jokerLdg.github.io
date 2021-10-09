---
layout: post
title: 백준 1157번 단어 공부 (python 파이썬)
subtitle: 백준 1157번 단어 공부
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1157번 단어 공부 문제를 Python으로 해결한 문제이다.  

* [백준 1157번 단어 공부 문제 링크](https://www.acmicpc.net/problem/1157){:target="_blank"}


### 문제 
알파벳 대소문자로 된 단어가 주어지면, 이 단어에서 가장 많이 사용된 알파벳이 무엇인지 알아내는 프로그램을 작성하시오. 단, 대문자와 소문자를 구분하지 않는다.


### 입력
첫째 줄에 알파벳 대소문자로 이루어진 단어가 주어진다. 주어지는 단어의 길이는 1,000,000을 넘지 않는다.


### 출력
**<u>첫째 줄에 이 단어에서 가장 많이 사용된 알파벳을 대문자로 출력한다. 단, 가장 많이 사용된 알파벳이 여러 개 존재하는 경우에는 ?를 출력한다.</u>**


### 문제풀이
1. 단어를 중복을 제거하고 저장한다.
2. 단어별로 개수를 센다.
3. 단어 개수의 최대값이 2개 이상이면 ? 출력하고, 아니면 최대값의 문자를 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

s = read().upper()
set_s = list(set(s))

count_list = []

for word in set_s:
    count = s.count(word)
    count_list.append(count)

if count_list.count(max(count_list)) >= 2:
    print('?')
else:
    print(set_s[count_list.index(max(count_list))])
```