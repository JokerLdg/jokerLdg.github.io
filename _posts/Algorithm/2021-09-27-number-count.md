---
layout: post
title: 백준 2577번 숫자의 개수 (python 파이썬)
subtitle: 백준 2577번 숫자의 개수
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2577번 숫자의 개수 문제를 Python으로 해결한 문제이다.  

* [백준 2577번 숫자의 개수 문제 링크](https://www.acmicpc.net/problem/2577){:target="_blank"}


### 문제 
세 개의 자연수 A, B, C가 주어질 때 A × B × C를 계산한 결과에 0부터 9까지 각각의 숫자가 몇 번씩 쓰였는지를 구하는 프로그램을 작성하시오.

예를 들어 A = 150, B = 266, C = 427 이라면 A × B × C = 150 × 266 × 427 = 17037300 이 되고, 계산한 결과 17037300 에는 0이 3번, 1이 1번, 3이 2번, 7이 2번 쓰였다.


### 입력
첫째 줄에 A, 둘째 줄에 B, 셋째 줄에 C가 주어진다. A, B, C는 모두 100보다 크거나 같고, 1,000보다 작은 자연수이다.


### 출력
**<u>첫째 줄에는 A × B × C의 결과에 0 이 몇 번 쓰였는지 출력한다. 마찬가지로 둘째 줄부터 열 번째 줄까지 A × B × C의 결과에 1부터 9까지의 숫자가 각각 몇 번 쓰였는지 차례로 한 줄에 하나씩 출력한다.</u>**


### 문제풀이
1. 10개의 배열을 저장할 변수를 만든다.
2. 반복문을 돌리는데, 합계가 0이 아닐때 까지 돌린다.
	* 합계를 10으로 나눈 나머지의 값을 1 증가시킨다.
	* 합계를 10으로 나눈다.



### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

total = 1

for i in range(3):
    total *= int(read())

answer = [0] * 10

while total != 0:
    answer[total % 10] += 1
    total //= 10

for number in answer:
    print(number)
```