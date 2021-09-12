---
layout: post
title: 백준 1517번 버블 소트 (python 파이썬)
subtitle: 백준 1517번 버블 소트
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 1517번 버블 소트 문제를 Python으로 해결한 문제이다.  

* [백준 1517번 버블 소트 문제 링크](https://www.acmicpc.net/problem/1517){:target="_blank"}


### 문제 
N개의 수로 이루어진 수열 A[1], A[2], …, A[N]이 있다. 이 수열에 대해서 버블 소트를 수행할 때, Swap이 총 몇 번 발생하는지 알아내는 프로그램을 작성하시오.

버블 소트는 서로 인접해 있는 두 수를 바꿔가며 정렬하는 방법이다. 예를 들어 수열이 3 2 1 이었다고 하자. 이 경우에는 인접해 있는 3, 2가 바뀌어야 하므로 2 3 1 이 된다. 다음으로는 3, 1이 바뀌어야 하므로 2 1 3 이 된다. 다음에는 2, 1이 바뀌어야 하므로 1 2 3 이 된다. 그러면 더 이상 바꿔야 할 경우가 없으므로 정렬이 완료된다.

### 입력
첫째 줄에 N(1 ≤ N ≤ 500,000)이 주어진다. 다음 줄에는 N개의 정수로 A[1], A[2], …, A[N]이 주어진다. 각각의 A[i]는 0 ≤ |A[i]| ≤ 1,000,000,000의 범위에 들어있다.


### 출력
**<u>첫째 줄에 Swap 횟수를 출력한다</u>**


### 문제풀이
해당 문제는 버블 정렬에 대한 Swap을 물어보았지만, 버블정렬으로는 풀 수 없다.  
병합정렬을 이용하여 풀 수 있으므로 병합정렬을 이용하여 풀어 보았다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()


def merge_sort(start, end):
    global swap_count, A

    if start < end:
        mid = (start + end) // 2
        merge_sort(start, mid)
        merge_sort(mid + 1, end)

        a, b = start, mid + 1
        temp = []

        while a <= mid and b <= end:
            if A[a] <= A[b]:
                temp.append(A[a])
                a += 1
            else:
                temp.append(A[b])
                b += 1
                swap_count += (mid - a + 1)

        if a <= mid:
            temp = temp + A[a:mid + 1]
        if b <= end:
            temp = temp + A[b:end + 1]

        for i in range(len(temp)):
            A[start + i] = temp[i]


swap_count = 0
N = int(read())
A = list(map(int, read().split()))
merge_sort(0, N - 1)
print(swap_count)
```