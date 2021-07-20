---
layout: post
title: 백준 19939번 박 터뜨리기 (python 파이썬)
subtitle: 백준 19939번 박 터뜨리기
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
백준 19939번 박 터뜨리기 문제를 Python으로 해결한 문제이다.  

* [백준 19939번 박 터뜨리기 문제 링크](https://www.acmicpc.net/problem/19939){:target="_blank"}


### 문제 
K개의 팀이 박 터트리기 게임을 한다. 각 팀은 하나의 바구니를 가지고 있고, 바구니에 들어있는 공을 던져서 자기 팀의 박을 터트려야 한다.

우리는 게임을 준비하기 위해서, N개의 공을 K개의 바구니에 나눠 담아야 한다. 이때, 게임의 재미를 위해서 바구니에 담기는 공의 개수를 모두 다르게 하고 싶다. 즉, N개의 공을 K개의 바구니에 빠짐없이 나누어 담는데, 각 바구니에는 1개 이상의 공이 있어야 하고, 바구니에 담긴 공의 개수가 모두 달라야 한다.

게임의 불공정함을 줄이기 위해서, 가장 많이 담긴 바구니와 가장 적게 담긴 바구니의 공의 개수 차이가 최소가 되도록 담을 것이다.

공을 바구니에 나눠 담기 위한 규칙을 정리하면 다음과 같다.

1. N개의 공을 K개의 바구니에 빠짐없이 나누어 담는다.
2. 각 바구니에는 1개 이상의 공이 들어 있어야 한다.
3. 각 바구니에 담긴 공의 개수는 모두 달라야 한다.
4. 가장 많이 담긴 바구니와 가장 적게 담긴 바구니의 공의 개수 차이가 최소가 되어야 한다.

위의 규칙을 모두 만족하며 N개의 공을 K개의 바구니에 나눠 담을 때, 나눠 담을 수 있는지 여부를 결정하고, 담을 수 있는 경우에는 가장 많이 담긴 바구니와 가장 적게 담긴 바구니의 공의 개수 차이를 계산해서 출력하는 프로그램을 작성하시오.


### 입력
첫 번째 줄에 공의 개수를 나타내는 N과 팀의 수를 나타내는 정수 K가 주어진다.


### 출력
**<u>N개의 공을 K개의 바구니에 문제의 규칙을 만족하면서 나눠 담을 수 있다면, 가장 많이 담긴 바구니와 가장 적게 담긴 바구니의 공의 개수 차이를 출력한다. 나눠 담을 수 없는 경우에는 -1을 출력한다.</u>**


### 문제풀이
K개의 바구니에 들어있는 공의 개수가 1개 이상이며 전부 달라야 하기 때문에 공의 최솟값은 k(k+1)/2이다.

각 바구니가 순서대로 공의 개수가 결정된다면 전의 바구니보다 1개 더 많을 때가 최소이기 때문이다.  
그렇다면 최솟값보다 공의 개수가 적으면 -1을 반환하면 된다.

공의 개수가 더 많을 경우 1부터 n까지 세우고 남은 공의 개수를 생각해보자.  
만약 공의 개수가 바구니의 수와 맞아 떨어진다면 각각 (남은 공의 개수)/(바구니 수)를 각 바구니에 더한 것과 같으므로 무시하면 된다.  
그러면 가장 개수가 적은 바구니(1)과 가장 개수가 많은 바구니(k)의 차인 k-1을 반환한다.

바구니의 수와 맞아떨어지지 않으면 가장 개수가 많은 바구니부터 하나씩 더한다고 생각하면 되므로 가장 개수가 적은 바구니(1)와 가장 개수가 많은 바구니(k+1)의 차인 k를 반환한다.

### 코드
```python
import sys

read = sys.stdin.readline

N, K = map(int, read().rstrip().split())

minimum = K*(K+1) // 2

if minimum > N:
    print(-1)
elif (N - minimum) % K == 0:
    print(K-1)
else:
    print(K)
```