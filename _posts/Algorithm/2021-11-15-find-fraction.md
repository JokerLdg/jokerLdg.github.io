---
layout: post
title: 백준 1193번 분수찾기 (python 파이썬)
subtitle: 백준 1193번 분수찾기
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1193번 분수찾기 문제를 Python으로 해결한 문제이다.  

* [백준 1193번 분수찾기 문제 링크](https://www.acmicpc.net/problem/1193){:target="_blank"}


### 문제 
무한히 큰 배열에 다음과 같이 분수들이 적혀있다.

|-----|-----|-----|-----|-----|-----|
|1/1|1/2|1/3|1/4|1/5|…|
|2/1|2/2|2/3|2/4|…|…|
|3/1|3/2|3/3|…|…|…|
|4/1|4/2|…|…|…|…|
|5/1|…|…|…|…|…|
|…|…|…|…|…|…|

이와 같이 나열된 분수들을 1/1 → 1/2 → 2/1 → 3/1 → 2/2 → … 과 같은 지그재그 순서로 차례대로 1번, 2번, 3번, 4번, 5번, … 분수라고 하자.

X가 주어졌을 때, X번째 분수를 구하는 프로그램을 작성하시오.


### 입력
첫째 줄에 X(1 ≤ X ≤ 10,000,000)가 주어진다.


### 출력
**<u>첫째 줄에 분수를 출력한다.</u>**


### 문제풀이
* 입력받은 X를 1씩 늘려 가며 빼서 몇 번째 줄에 몇 번째 숫자인지 구한다.
* 짝수 줄인 경우, 분자는 오름차순, 분모는 내림차순이다.
* 홀수 줄인 경우, 분자는 내림차순, 분모는 오름차순이다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

X = int(read())

numerator, denominator = 0, 0
line = 1

while X > line:
    X -= line
    line += 1

if line % 2 == 0:
    numerator = X
    denominator = line - X + 1
else:
    numerator = line - X + 1
    denominator = X

print(numerator, '/', denominator, sep='')
```