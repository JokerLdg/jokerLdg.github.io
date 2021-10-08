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

* [백준 10809번 알파벳 찾기 문제 링크](https://www.acmicpc.net/problem/10809){:target="_blank"}


### 문제 
알파벳 소문자로만 이루어진 단어 S가 주어진다. 각각의 알파벳에 대해서, 단어에 포함되어 있는 경우에는 처음 등장하는 위치를, 포함되어 있지 않은 경우에는 -1을 출력하는 프로그램을 작성하시오.


### 입력
첫째 줄에 단어 S가 주어진다. 단어의 길이는 100을 넘지 않으며, 알파벳 소문자로만 이루어져 있다.


### 출력
**<u>각각의 알파벳에 대해서, a가 처음 등장하는 위치, b가 처음 등장하는 위치, ... z가 처음 등장하는 위치를 공백으로 구분해서 출력한다. 만약, 어떤 알파벳이 단어에 포함되어 있지 않다면 -1을 출력한다. 단어의 첫 번째 글자는 0번째 위치이고, 두 번째 글자는 1번째 위치이다.</u>**


### 문제풀이
1. 26개의 배열을 만들어 준다.
	* 알파벳의 개수가 26개이므로 26개의 배열
2. 입력받은 S의 값을 list로 변환한다.
3. 각 list를 반복문을 돌린다.
	* 각 단어를 ascii 코드값으로 변환 후 -97을 한다.
	* 26개의 배열에서 그 값 번째의 값이 -1이 아니면 count를 1 증가시키고 다음 단어를 진행한다.
	* 포함이 안되면 그 값 번째에 count를 대입하고 1 증가시킨다.
4. 파이썬의 * 를 이용하여 배열을 출력한다.


### 코드
```python
import sys

read = lambda: sys.stdin.readline().rstrip()

S = list(read())
answer = [-1] * 26

count = 0

for word in S:
    s = ord(word) - 97
    if answer[s] != -1:
        count += 1
        continue
    else:
        answer[s] = count
        count += 1

print(*answer)
```
