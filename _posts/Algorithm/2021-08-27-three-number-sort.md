---
layout: post
title: 백준 2752번 세수정렬 (python 파이썬)
subtitle: 백준 2752번 세수정렬
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2752번 세수정렬 문제를 Python으로 해결한 문제이다.  

* [백준 2752번 세수정렬 문제 링크](https://www.acmicpc.net/problem/2752){:target="_blank"}


### 문제 
동규는 세수를 하다가 정렬이 하고싶어졌다.

숫자 세 개를 생각한 뒤에, 이를 오름차순으로 정렬하고 싶어 졌다.

숫자 세 개가 주어졌을 때, 가장 작은 수, 그 다음 수, 가장 큰 수를 출력하는 프로그램을 작성하시오.


### 입력
숫자 세 개가 주어진다. 이 숫자는 1보다 크거나 같고, 1,000,000보다 작거나 같다. 이 숫자는 모두 다르다.


### 출력
**<u>제일 작은 수, 그 다음 수, 제일 큰 수를 차례대로 출력한다.</u>**


### 문제풀이
1. 수를 입력 받아서 list로 만든다.
2. list를 오름차순으로 정렬한다.
3. 파이썬의 * 연산자를 이용하여 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

number = list(map(int, read().split()))
number.sort()

print(*number)
```