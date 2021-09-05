---
title: "전화번호 목록"
date: 2021-09-05 22:23:47 +0900
categories: algorithm
tags: programmers hash level2
---

## [전화번호 목록](https://programmers.co.kr/learn/courses/30/lessons/42577)

자료구조의 해시 테이블에 대한 기초 문제 입니다.
해시 테이블은 key와 value 매핑할 수 있는 구조 입니다.
해시 함수에 의해 value가 정해지는 데 big-O는 O(1)으로 키가 값에 바로 매칭이 되어 검색관련 문제에 쓰기 좋습니다.

이 문제에서는 정렬을 하게 되면 풀리게 되는 문제입니다.

```python
def solution(phone_book):
    answer = True
    phone_book.sort()
    for i in range(len(phone_book)-1):
        if phone_book[i+1].find(phone_book[i]) == 0:
            return False
    return answer
```
