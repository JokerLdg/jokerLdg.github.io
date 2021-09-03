---
layout: post
title: 백준 18870번 좌표 압축 (python 파이썬)
subtitle: 백준 18870번 좌표 압축
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 18870번 좌표 압축 문제를 Python으로 해결한 문제이다.  

* [백준 18870번 좌표 압축 문제 링크](https://www.acmicpc.net/problem/18870){:target="_blank"}


### 문제 
수직선 위에 N개의 좌표 X1, X2, ..., XN이 있다. 이 좌표에 좌표 압축을 적용하려고 한다.

Xi를 좌표 압축한 결과 X'i의 값은 Xi > Xj를 만족하는 서로 다른 좌표의 개수와 같아야 한다.

X1, X2, ..., XN에 좌표 압축을 적용한 결과 X'1, X'2, ..., X'N를 출력해보자.


### 입력
첫째 줄에 N이 주어진다.

둘째 줄에는 공백 한 칸으로 구분된 X1, X2, ..., XN이 주어진다.


### 출력
**<u>첫째 줄에 X'1, X'2, ..., X'N을 공백 한 칸으로 구분해서 출력한다.</u>**


### 문제풀이
1. N을 입력받는다.
2. set을 통해 중복을 없애주고 정렬한다.
3. dict를 이용하여 요소를 만들어준다.
4. 반복을 통해 dict에서 뽑아준다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())

coordinate = list(map(int, read().split()))
coordinate2 = sorted(list(set(coordinate)))

dic = {coordinate2[i] : i for i in range(len(coordinate2))}

for i in coordinate:
	print(dic[i], end=' ')
```