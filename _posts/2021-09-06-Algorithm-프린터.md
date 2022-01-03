---
title: "프린터"
date: 2021-09-05 22:55:03 +0900
categories: algorithm
tags: programmers queue level2
---

## [프린터](https://programmers.co.kr/learn/courses/30/lessons/42587)

자료구조 중에 간단한 queue에 관한 문제입니다.
큐는 FIFO이므로 먼저 들어간 것은 먼저 나오는 자료구조입니다.
이미 줄서는 경험을 한번이라도 해본 분들은 바로 이해가 되셨을 겁니다.

프린터 문제는 max_value를 정의하고 먼저 큐에서 나온것이 우선순위가 max_value 보다
낮으면 뒤로 다시 넣어주는 방식으로 구현 하였습니다.

```python
def solution(priorities, location):
    answer = 0
    queue = [i for i in range(len(priorities))]

    while queue:
        max_value = max(priorities)
        #우선순위가 높은 문서가 존재하는 경우 뒤로 넘김
        if priorities[0] < max_value:
            i = priorities.index(max_value)
            priorities = priorities[i:] + priorities[:i]
            queue = queue[i:] + queue[:i]
        else:
            if queue[0] == location:
                answer += 1
                break
            else:
                queue.pop(0)
                priorities.pop(0)
                answer += 1

    return answer
```
