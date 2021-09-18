---
layout: post
title: 백준 1302번 베스트셀러 (python 파이썬)
subtitle: 백준 1302번 베스트셀러
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1302번 베스트셀러 문제를 Python으로 해결한 문제이다.  

* [백준 1302번 베스트셀러 문제 링크](https://www.acmicpc.net/problem/1302){:target="_blank"}


### 문제 
김형택은 탑문고의 직원이다. 김형택은 계산대에서 계산을 하는 직원이다. 김형택은 그날 근무가 끝난 후에, 오늘 판매한 책의 제목을 보면서 가장 많이 팔린 책의 제목을 칠판에 써놓는 일도 같이 하고 있다.

오늘 하루 동안 팔린 책의 제목이 입력으로 들어왔을 때, 가장 많이 팔린 책의 제목을 출력하는 프로그램을 작성하시오.


### 입력
첫째 줄에 오늘 하루 동안 팔린 책의 개수 N이 주어진다. 이 값은 1,000보다 작거나 같은 자연수이다. 둘째부터 N개의 줄에 책의 제목이 입력으로 들어온다. 책의 제목의 길이는 50보다 작거나 같고, 알파벳 소문자로만 이루어져 있다.


### 출력
**<u>첫째 줄에 가장 많이 팔린 책의 제목을 출력한다. 만약 가장 많이 팔린 책이 여러 개일 경우에는 사전 순으로 가장 앞서는 제목을 출력한다.</u>**


### 문제풀이
1. 책을 입력받아서 Counter를 이용하여 배열의 같은 종류의 숫자를 세어준다.
2. Counter의 items를 이용하여 따로 배열에 책이름, 팔린 책의 개수를 넣어준다.
3. lambda를 이용하여 팔린 책의 개수를 기준으로 내림차순, 팔린 책의 이름을 오름차순으로 정렬한다.
4. 배열의 첫번째의 첫번째 값을 출력한다.


### 코드
```python
import sys
from collections import Counter

read = lambda: sys.stdin.readline().rstrip()

N = int(read())
books = [read() for _ in range(N)]
seller = []

for name, count in Counter(books).items():
    seller.append([name, count])

seller.sort(key=lambda x:(-x[1], x[0]))

print(seller[0][0])
```