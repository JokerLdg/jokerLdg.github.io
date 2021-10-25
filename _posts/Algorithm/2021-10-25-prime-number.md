---
layout: post
title: 백준 1978번 소수 찾기 (python 파이썬)
subtitle: 백준 1978번 소수 찾기
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1978번 소수 찾기 문제를 Python으로 해결한 문제이다.  

* [백준 1978번 소수 찾기 문제 링크](https://www.acmicpc.net/problem/1978){:target="_blank"}


### 문제 
주어진 수 N개 중에서 소수가 몇 개인지 찾아서 출력하는 프로그램을 작성하시오.


### 입력
첫 줄에 수의 개수 N이 주어진다. N은 100이하이다. 다음으로 N개의 수가 주어지는데 수는 1,000 이하의 자연수이다.


### 출력
**<u>주어진 수들 중 소수의 개수를 출력한다.</u>**


### 문제풀이
소수를 찾으려면 1과 자기 자신으로 나눠지는 수를 찾으면 된다.

* 만든 숫자를 check함수를 이용하여 각 숫자를 소수인지 아닌지 판단한다.
	* 소수 판단방법은 판단할 숫자의 제곱근을 구한다.
	* 2보다 작으면 소수가 아니므로 False
	* 2이상이면 2부터 제곱근만큼 반복문을 실행하는데, 그 값으로 나누어 떨어지면 소수가 아니다.


### 코드
```python
import sys

read = sys.stdin.readline

def check(n):
    if n < 2:
        return False

    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True

N = int(read().rstrip())

numbers = list(map(int, read().split()))

answer = 0

for number in numbers:
    if check(number):
        answer += 1

print(answer)
```