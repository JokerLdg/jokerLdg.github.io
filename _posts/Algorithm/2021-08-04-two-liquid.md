---
layout: post
title: 백준 2470번 두 용액 (python 파이썬)
subtitle: 백준 2470번 두 용액
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 2470번 두 용액 문제를 Python으로 해결한 문제이다.  

* [백준 2470번 두 용액 문제 링크](https://www.acmicpc.net/problem/2470){:target="_blank"}


### 문제 
KOI 부설 과학연구소에서는 많은 종류의 산성 용액과 알칼리성 용액을 보유하고 있다. 각 용액에는 그 용액의 특성을 나타내는 하나의 정수가 주어져있다.  산성 용액의 특성값은 1부터 1,000,000,000까지의 양의 정수로 나타내고, 알칼리성 용액의 특성값은 -1부터 -1,000,000,000까지의 음의 정수로 나타낸다.

같은 양의 두 용액을 혼합한 용액의 특성값은 혼합에 사용된 각 용액의 특성값의 합으로 정의한다. 이 연구소에서는 같은 양의 두 용액을 혼합하여 특성값이 0에 가장 가까운 용액을 만들려고 한다. 

예를 들어, 주어진 용액들의 특성값이 [-2, 4, -99, -1, 98]인 경우에는 특성값이 -99인 용액과 특성값이 98인 용액을 혼합하면 특성값이 -1인 용액을 만들 수 있고, 이 용액이 특성값이 0에 가장 가까운 용액이다. 참고로, 두 종류의 알칼리성 용액만으로나 혹은 두 종류의 산성 용액만으로 특성값이 0에 가장 가까운 혼합 용액을 만드는 경우도 존재할 수 있다.

산성 용액과 알칼리성 용액의 특성값이 주어졌을 때, 이 중 두 개의 서로 다른 용액을 혼합하여 특성값이 0에 가장 가까운 용액을 만들어내는 두 용액을 찾는 프로그램을 작성하시오.


### 입력
첫째 줄에는 전체 용액의 수 N이 입력된다. N은 2 이상 100,000 이하이다. 둘째 줄에는 용액의 특성값을 나타내는 N개의 정수가 빈칸을 사이에 두고 주어진다. 이 수들은 모두 -1,000,000,000 이상 1,000,000,000 이하이다. N개의 용액들의 특성값은 모두 다르고, 산성 용액만으로나 알칼리성 용액만으로 입력이 주어지는 경우도 있을 수 있다.


### 출력
**<u>첫째 줄에 특성값이 0에 가장 가까운 용액을 만들어내는 두 용액의 특성값을 출력한다. 출력해야 하는 두 용액은 특성값의 오름차순으로 출력한다. 특성값이 0에 가장 가까운 용액을 만들어내는 경우가 두 개 이상일 경우에는 그 중 아무것이나 하나를 출력한다.</u>**


### 문제풀이
1. 입력받은 용액 값을 오름차순으로 정렬한다.
2. start 값에 0, end 값에 N-1, a_start 값에 start값, a_end값에 end값 대입한다.
    * 반복문을 통해 음수에서 양수로 넘어가는 부분까지 계산
    * 처음 값과 끝 값을 먼저 계산하여 answer에 대입하고 시작한다.
4. 현재의 start, end 인덱스에 존재하는 값의 합이 answer 보다 작다면 answer 값에 대입해주고 a_start와 a_end 값도 바꿔준다. 
    * answer 값이 0일 경우엔 더이상 while 문을 돌리지 않고 break
5. temp 값이 양수 이면 end -=1, temp 값이 음수 이면 start += 1


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

N = int(read())
liquid = list(map(int, read().split()))
liquid.sort()

start = 0
end = N-1

answer = liquid[start] + liquid[end]

a_start = start
a_end = end

while start < end:
    temp = liquid[start] + liquid[end]

    if abs(temp) < abs(answer):
        answer = temp
        a_start = start
        a_end = end

        if answer == 0:
            break

    if temp > 0:
        end -= 1
    else:
        start += 1

print(liquid[a_start], liquid[a_end])
```