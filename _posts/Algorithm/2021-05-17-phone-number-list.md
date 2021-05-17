---
layout: post
title: 프로그래머스 전화번호 목록 (python 파이썬)
subtitle: 프로그래머스 전화번호 목록
comments: true
categories: [Algorithm]
tags: [Algorithm]
sitemap :
changefreq : daily
priority : 1.0
---
프로그래머스 전화번호 목록 문제를 Python으로 해결한 문제이다.  

* [프로그래머스 전화번호 목록 문제 링크](https://programmers.co.kr/learn/courses/30/lessons/42577){:target="_blank"}


### 문제 설명
전화번호부에 적힌 전화번호 중, 한 번호가 다른 번호의 접두어인 경우가 있는지 확인하려 합니다.
전화번호가 다음과 같을 경우, 구조대 전화번호는 영석이의 전화번호의 접두사입니다.

* 구조대 : 119
* 박준영 : 97 674 223
* 지영석 : 11 9552 4421

전화번호부에 적힌 전화번호를 담은 배열 phone_book 이 solution 함수의 매개변수로 주어질 때, 어떤 번호가 다른 번호의 접두어인 경우가 있으면 false를 그렇지 않으면 true를 return 하도록 solution 함수를 작성해주세요.


### 제한 사항
* phone_book의 길이는 1 이상 1,000,000 이하입니다.
    * 각 전화번호의 길이는 1 이상 20 이하입니다.
    * 같은 전화번호가 중복해서 들어있지 않습니다.


### 입출력 예

|phone_book|return|
|-----|-----|
|["119", "97674223", "1195524421"]|false|
|["123","456","789"]|true|
|["12","123","1235","567","88"]|false|


### 입출력 예 설명
**예제 #1**  
앞에서 설명한 예와 같습니다.

**예제 #2**  
한 번호가 다른 번호의 접두사인 경우가 없으므로, 답은 true입니다.


**예제 #3**  
첫 번째 전화번호, “12”가 두 번째 전화번호 “123”의 접두사입니다. 따라서 답은 false입니다.


### 문제풀이
1. 전화번호 리스트를 먼저 오름차순으로 정렬해준다.
2. zip을 이용하여 배열의 값을 비교하여 p1으로 시작하는 값이 있으면 False, 아니면 True를 return한다.

### 코드
```python
def solution(phone_book):
    phone_book.sort()
    for p1, p2 in zip(phone_book, phone_book[1:]):
        if p2.startswith(p1):
            return False
    return True
```
