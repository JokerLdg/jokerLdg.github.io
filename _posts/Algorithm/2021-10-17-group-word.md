---
layout: post
title: 백준 1316번 그룹 단어 체커 (python 파이썬)
subtitle: 백준 1316번 그룹 단어 체커
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1316번 그룹 단어 체커 문제를 Python으로 해결한 문제이다.  

* [백준 1316번 그룹 단어 체커 문제 링크](https://www.acmicpc.net/problem/1316){:target="_blank"}


### 문제 
그룹 단어란 단어에 존재하는 모든 문자에 대해서, 각 문자가 연속해서 나타나는 경우만을 말한다. 예를 들면, ccazzzzbb는 c, a, z, b가 모두 연속해서 나타나고, kin도 k, i, n이 연속해서 나타나기 때문에 그룹 단어이지만, aabbbccb는 b가 떨어져서 나타나기 때문에 그룹 단어가 아니다.

단어 N개를 입력으로 받아 그룹 단어의 개수를 출력하는 프로그램을 작성하시오.


### 입력
첫째 줄에 단어의 개수 N이 들어온다. N은 100보다 작거나 같은 자연수이다. 둘째 줄부터 N개의 줄에 단어가 들어온다. 단어는 알파벳 소문자로만 되어있고 중복되지 않으며, 길이는 최대 100이다.


### 출력
**<u>첫째 줄에 그룹 단어의 개수를 출력한다.</u>**


### 문제풀이
특정 문자 다음에 다른 문자가 나올 경우 문자열에서 그 글자 다음부터 끝까지 검사하여 똑같은 문자가 있는지 확인하고, answer를 1 증가시킨다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())
answer = 0

for i in range(N):
    word = read()
    for j in range(len(word)):
        if j != len(word)-1:
            if word[j] == word[j+1]:
                pass
            elif word[j] in word[j+1:]:
                break
        else:
            answer += 1

print(answer)
```