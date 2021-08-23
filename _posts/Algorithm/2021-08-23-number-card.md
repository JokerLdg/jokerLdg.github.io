---
layout: post
title: 백준 10815번 숫자 카드 (python 파이썬)
subtitle: 백준 10815번 숫자 카드
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 10815번 숫자 카드 문제를 Python으로 해결한 문제이다.  

* [백준 10815번 숫자 카드 문제 링크](https://www.acmicpc.net/problem/1026){:target="_blank"}


### 문제 
숫자 카드는 정수 하나가 적혀져 있는 카드이다. 상근이는 숫자 카드 N개를 가지고 있다. 정수 M개가 주어졌을 때, 이 수가 적혀있는 숫자 카드를 상근이가 가지고 있는지 아닌지를 구하는 프로그램을 작성하시오.


### 입력
첫째 줄에 상근이가 가지고 있는 숫자 카드의 개수 N(1 ≤ N ≤ 500,000)이 주어진다. 둘째 줄에는 숫자 카드에 적혀있는 정수가 주어진다. 숫자 카드에 적혀있는 수는 -10,000,000보다 크거나 같고, 10,000,000보다 작거나 같다. 두 숫자 카드에 같은 수가 적혀있는 경우는 없다.

셋째 줄에는 M(1 ≤ M ≤ 500,000)이 주어진다. 넷째 줄에는 상근이가 가지고 있는 숫자 카드인지 아닌지를 구해야 할 M개의 정수가 주어지며, 이 수는 공백으로 구분되어져 있다. 이 수도 -10,000,000보다 크거나 같고, 10,000,000보다 작거나 같다


### 출력
**<u>첫째 줄에 입력으로 주어진 M개의 수에 대해서, 각 수가 적힌 숫자 카드를 상근이가 가지고 있으면 1을, 아니면 0을 공백으로 구분해 출력한다.</u>**


### 문제풀이
1. N카드와 M카드를 입력받는다.
2. M_card가 N_card에 포함되면 1, 아니면 0을 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())
N_card = set(map(int, read().split()))
M = int(read())
M_card = list(map(int, read().split()))

for i in M_card:
    if i in N_card:
        print(1, end=' ')
    else:
        print(0, end=' ')
```
