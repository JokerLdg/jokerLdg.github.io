---
layout: post
title: 백준 15596번 정수 N개의 합 (python 파이썬)
subtitle: 백준 15596번 정수 N개의 합
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 15596번 정수 N개의 합 문제를 Python으로 해결한 문제이다.  

* [백준 15596번 정수 N개의 합 문제 링크](https://www.acmicpc.net/problem/15596){:target="_blank"}


### 문제 
정수 n개가 주어졌을 때, n개의 합을 구하는 함수를 작성하시오.

작성해야 하는 함수는 다음과 같다.

* C, C11, C (Clang), C11 (Clang): long long sum(int *a, int n);
	* a: 합을 구해야 하는 정수 n개가 저장되어 있는 배열 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
	* n: 합을 구해야 하는 정수의 개수
	* 리턴값: a에 포함되어 있는 정수 n개의 합
* C++, C++11, C++14, C++17, C++ (Clang), C++11 (Clang), C++14 (Clang), C++17 (Clang): long long sum(std::vector<int> &a);
	* a: 합을 구해야 하는 정수 n개가 저장되어 있는 배열 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
	* 리턴값: a에 포함되어 있는 정수 n개의 합
* python 2, Python 3, PyPy, PyPy3: def solve(a: list) -> int
	* a: 합을 구해야 하는 정수 n개가 저장되어 있는 리스트 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
	* 리턴값: a에 포함되어 있는 정수 n개의 합 (정수)
* Java: long sum(int[] a); (클래스 이름: Test)
	* a: 합을 구해야 하는 정수 n개가 저장되어 있는 배열 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
	* 리턴값: a에 포함되어 있는 정수 n개의 합
* Go: sum(a []int) int
	* a: 합을 구해야 하는 정수 n개가 저장되어 있는 배열 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
	* 리턴값: a에 포함되어 있는 정수 n개의 합


### 입력
N


### 출력
**<u>a에 포함되어 있는 정수 n개의 합</u>**


### 문제풀이
1. for문을 이용하여 a만큼 합을 더한다.
2. sum을 이용하여 바로 return도 가능하다.


### 코드
```python
def solve(a: list) -> int:
    total = 0
    for x in a:
        total += x
    return total
```