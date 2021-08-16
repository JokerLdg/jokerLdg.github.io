---
layout: post
title: 백준 1181번 단어 정렬 (python 파이썬)
subtitle: 백준 1181번 단어 정렬
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1181번 단어 정렬 문제를 Python으로 해결한 문제이다.  

* [백준 1181번 단어 정렬 문제 링크](https://www.acmicpc.net/problem/1181){:target="_blank"}


### 문제 
알파벳 소문자로 이루어진 N개의 단어가 들어오면 아래와 같은 조건에 따라 정렬하는 프로그램을 작성하시오.

1. 길이가 짧은 것부터
2. 길이가 같으면 사전 순으로


### 입력
첫째 줄에 단어의 개수 N이 주어진다. (1 ≤ N ≤ 20,000) 둘째 줄부터 N개의 줄에 걸쳐 알파벳 소문자로 이루어진 단어가 한 줄에 하나씩 주어진다. 주어지는 문자열의 길이는 50을 넘지 않는다.


### 출력
**<u>조건에 따라 정렬하여 단어들을 출력한다. 단, 같은 단어가 여러 번 입력된 경우에는 한 번씩만 출력한다.</u>**


### 문제풀이
1. 배열에 (단어 길이, 단어) 형태로 집어 넣는다.
2. 배열에 중복을 제거한다.
3. 배열을 람다식으로 정렬한다.
    * word[0], word[1]은 단어의 길이먼저 정렬후, 단어별로 정렬한다.
4. 정렬된 배열의 2번째 값을 출력한다. 


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())
words = []

for i in range(N):
    word = read()
    word_length = len(word)
    words.append((word_length, word))

words = list(set(words))
words.sort(key = lambda word: (word[0], word[1]))

for word in words:
    print(word[1])
```