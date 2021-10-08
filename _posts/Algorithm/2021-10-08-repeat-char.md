---
layout: post
title: 백준 10809번 알파벳 찾기 (python 파이썬)
subtitle: 백준 10809번 알파벳 찾기
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 10809번 알파벳 찾기 문제를 Python으로 해결한 문제이다.  

* [백준 10809번 알파벳 찾기 문제 링크](https://www.acmicpc.net/problem/2675){:target="_blank"}


### 문제 
문자열 S를 입력받은 후에, 각 문자를 R번 반복해 새 문자열 P를 만든 후 출력하는 프로그램을 작성하시오. 즉, 첫 번째 문자를 R번 반복하고, 두 번째 문자를 R번 반복하는 식으로 P를 만들면 된다. S에는 QR Code "alphanumeric" 문자만 들어있다.

QR Code "alphanumeric" 문자는 
```0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ\$%*+-./:이다.```


### 입력
첫째 줄에 테스트 케이스의 개수 T(1 ≤ T ≤ 1,000)가 주어진다. 각 테스트 케이스는 반복 횟수 R(1 ≤ R ≤ 8), 문자열 S가 공백으로 구분되어 주어진다. S의 길이는 적어도 1이며, 20글자를 넘지 않는다. 


### 출력
**<u>각 테스트 케이스에 대해 P를 출력한다.</u>**


### 문제풀이
단어를 R만큼 answer에 더하여 answer를 마지막에 출력하면 된다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

T = int(read())

for i in range(T):
    R, S = map(str, read().split())
    answer = ""
    for word in S:
        answer += (word * int(R))
    print(answer)
```