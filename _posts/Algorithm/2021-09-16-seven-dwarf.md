---
layout: post
title: 백준 2309번 일곱 난쟁이 (python 파이썬)
subtitle: 백준 2309번 일곱 난쟁이
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2309번 일곱 난쟁이 문제를 Python으로 해결한 문제이다.  

* [백준 2309번 일곱 난쟁이 문제 링크](https://www.acmicpc.net/problem/2309){:target="_blank"}


### 문제 
왕비를 피해 일곱 난쟁이들과 함께 평화롭게 생활하고 있던 백설공주에게 위기가 찾아왔다. 일과를 마치고 돌아온 난쟁이가 일곱 명이 아닌 아홉 명이었던 것이다.

아홉 명의 난쟁이는 모두 자신이 "백설 공주와 일곱 난쟁이"의 주인공이라고 주장했다. 뛰어난 수학적 직관력을 가지고 있던 백설공주는, 다행스럽게도 일곱 난쟁이의 키의 합이 100이 됨을 기억해 냈다.

아홉 난쟁이의 키가 주어졌을 때, 백설공주를 도와 일곱 난쟁이를 찾는 프로그램을 작성하시오.


### 입력
아홉 개의 줄에 걸쳐 난쟁이들의 키가 주어진다. 주어지는 키는 100을 넘지 않는 자연수이며, 아홉 난쟁이의 키는 모두 다르며, 가능한 정답이 여러 가지인 경우에는 아무거나 출력한다.


### 출력
**<u>일곱 난쟁이의 키를 오름차순으로 출력한다. 일곱 난쟁이를 찾을 수 없는 경우는 없다.</u>**


### 문제풀이
1. 난쟁이의 키 9개를 입력받아서 전부 더한다.
2. 이중 for문을 돌려서, total - 난쟁이 2명의 합 이 100인경우 9개의 배열에서 제거해준다.
3. 제거한 배열을 오름차순 정렬하여 순서대로 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

dwarf = [int(read()) for _ in range(9)]

total = sum(dwarf)
one = 0
two = 0

for i in range(9):
    for j in range(i+1, 9):
        if total - (dwarf[i] + dwarf[j]) == 100:
            one, two = dwarf[i], dwarf[j]
            break

dwarf.remove(one)
dwarf.remove(two)
dwarf.sort()

for i in dwarf:
    print(i)
```