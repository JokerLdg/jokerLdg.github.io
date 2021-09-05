---
layout: post
title: 백준 2822번 점수 계산 (python 파이썬)
subtitle: 백준 2822번 점수 계산
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2822번 점수 계산 문제를 Python으로 해결한 문제이다.  

* [백준 2822번 점수 계산 문제 링크](https://www.acmicpc.net/problem/2822){:target="_blank"}


### 문제 
상근이는 퀴즈쇼의 PD이다. 이 퀴즈쇼의 참가자는 총 8개 문제를 푼다. 참가자는 각 문제를 풀고, 그 문제를 풀었을 때 얻는 점수는 문제를 풀기 시작한 시간부터 경과한 시간과 난이도로 결정한다. 문제를 풀지 못한 경우에는 0점을 받는다. 참가자의 총 점수는 가장 높은 점수 5개의 합이다. 

상근이는 잠시 여자친구와 전화 통화를 하느라 참가자의 점수를 계산하지 않고 있었다. 참가자의 8개 문제 점수가 주어졌을 때, 총 점수를 구하는 프로그램을 작성하시오.


### 입력
8개 줄에 걸쳐서 각 문제에 대한 참가자의 점수가 주어진다. 점수는 0보다 크거나 같고, 150보다 작거나 같다. 모든 문제에 대한 점수는 서로 다르다. 입력으로 주어지는 순서대로 1번 문제, 2번 문제, ... 8번 문제이다.


### 출력
**<u>첫째 줄에 참가자의 총점을 출력한다. 둘째 줄에는 어떤 문제가 최종 점수에 포함되는지를 공백으로 구분하여 출력한다. 출력은 문제 번호가 증가하는 순서이어야 한다.</u>**


### 문제풀이
1. 점수를 8개를 입력받는다.
2. 점수를 내림차순으로 정렬하여 변수에 집어 넣어주고, 5번째까지 slice한다.
3. answer배열에 5개의 최고 점수에 대한 index+1 값을 넣어준다.
4. total에 5개 최고 점수를 다 더해준다.
5. 마지막으로 total, 파이썬의 * 을 이용하여 answer도 같이 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

score = []
score_sort = []
answer = []
total = 0

for i in range(8):
    score.append(int(read()))

score_sort = sorted(score, reverse=True)
score_sort = score_sort[:5]

for i in score_sort:
    answer.append(score.index(i)+1)

answer.sort()
total = sum(score_sort)

print(total)
print(*answer)
```