---
title: "프로그래머스 위클리 챌린지 1주차"
date: 2021-09-02 22:50:20 +0900
categories: algorithm
tags: programmers
---

# 부족한 금액 계산하기

[위클리 챌린지 1주차 문제](https://programmers.co.kr/learn/courses/30/lessons/82612)

구현 문제로 문제를 잘 읽고 그대로 구현해 주면 쉽게 풀 수 있다.
놀이 기구를 한번 탈때마다 가격이 인상되는 부분을 구현 해주고 얼마가 부족한지 출력한다.

```python
def solution(price, money, count):
    total = 0
    for i in range(1,count+1):
        total += i*price
    answer = total-money
    if answer < 0:
        return 0
    return answer
```
