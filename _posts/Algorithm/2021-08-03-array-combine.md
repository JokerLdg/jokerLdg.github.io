---
layout: post
title: 백준 11728번 배열 합치기 (python 파이썬)
subtitle: 백준 11728번 배열 합치기
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 11728번 배열 합치기 문제를 Python으로 해결한 문제이다.  

* [백준 11728번 배열 합치기 문제 링크](https://www.acmicpc.net/problem/11728){:target="_blank"}


### 문제 
정렬되어있는 두 배열 A와 B가 주어진다. 두 배열을 합친 다음 정렬해서 출력하는 프로그램을 작성하시오.


### 입력
첫째 줄에 배열 A의 크기 N, 배열 B의 크기 M이 주어진다. (1 ≤ N, M ≤ 1,000,000)

둘째 줄에는 배열 A의 내용이, 셋째 줄에는 배열 B의 내용이 주어진다. 배열에 들어있는 수는 절댓값이 109보다 작거나 같은 정수이다.


### 출력
**<u>첫째 줄에 두 배열을 합친 후 정렬한 결과를 출력한다.</u>**


### 문제풀이
해당 문제는 배열을 합쳐서 정렬을 하는 방법과, 투 포인터를 이용하여 푸는 방법이 있다.

* **배열 정렬**
1. 각 배열에 입력을 받는다.
2. A배열과 B배열을 합친다.
3. 합친 배열을 정렬하고 파이썬의 * 을 이용하여 출력한다.


* **투 포인터**
1. 각 배열에 입력 받는다.
2. a와 b의 포인터를 생성하여 두 포인터가 각 배열의 끝이 아닐때 까지 진행한다.
3. a포인터의 길이가 A배열의 끝에 다왔다면 B배열의 값을 추가한다.
4. b포인터의 길이가 B배열의 끝에 다왔다면 A배열의 값을 추가한다.
5. 두 배열의 길이가 끝이 아닌경우 각 배열의 포인터의 크기를 비교하여 더 작은 값을 넣어준다.


### 코드 1안(배열 정렬 이용)
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N, M = map(int, read().split())

A = list(map(int, read().split()))
B = list(map(int, read().split()))

answer = A + B
answer.sort()

print(*answer)
```


### 코드 2안(투 포인터 이용)
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N, M = map(int, read().split())

A = list(map(int, read().split()))
B = list(map(int, read().split()))
answer = []

a_pointer, b_pointer = 0, 0
a_length, b_length = len(A), len(B)

while a_pointer != a_length or b_pointer != b_length:
    if a_pointer == a_length:
        answer.append(B[b_pointer])
        b_pointer += 1
    elif b_pointer == b_length:
        answer.append(A[a_pointer])
        a_pointer += 1
    else:
        if A[a_pointer] < B[b_pointer]:
            answer.append(A[a_pointer])
            a_pointer += 1
        else:
            answer.append(B[b_pointer])
            b_pointer += 1

print(*answer)
```