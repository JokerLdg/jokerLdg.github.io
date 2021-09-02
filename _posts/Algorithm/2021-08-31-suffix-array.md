---
layout: post
title: 백준 11656번 접미사 배열 (python 파이썬)
subtitle: 백준 11656번 접미사 배열
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 11656번 접미사 배열 문제를 Python으로 해결한 문제이다.  

* [백준 11656번 접미사 배열 문제 링크](https://www.acmicpc.net/problem/11656){:target="_blank"}


### 문제 
접미사 배열은 문자열 S의 모든 접미사를 사전순으로 정렬해 놓은 배열이다.

baekjoon의 접미사는 baekjoon, aekjoon, ekjoon, kjoon, joon, oon, on, n 으로 총 8가지가 있고, 이를 사전순으로 정렬하면, aekjoon, baekjoon, ekjoon, joon, kjoon, n, on, oon이 된다.

문자열 S가 주어졌을 때, 모든 접미사를 사전순으로 정렬한 다음 출력하는 프로그램을 작성하시오.


### 입력
첫째 줄에 문자열 S가 주어진다. S는 알파벳 소문자로만 이루어져 있고, 길이는 1,000보다 작거나 같다.


### 출력
**<u>첫째 줄부터 S의 접미사를 사전순으로 한 줄에 하나씩 출력한다.</u>**


### 문제풀이
1. N을 입력받는다.
2. S_list에 S를 집어 넣는다.
	* S에 다시 첫번째 값을 제외한 나머지를 잘라서 대입한다.
3. S_list의 값을 정렬하여 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

S = read()
S_list = []

for _ in S:
	S_list.append(S)
	S = S[1:]

for s in sorted(S_list):
	print(s)
```
