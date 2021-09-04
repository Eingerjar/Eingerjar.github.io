---
title: "디스크 컨트롤러"
date: 2021-09-04 23:43:23 +0900
categories: algorithm
tags: programmers heap level3
---

## [디스크 컨트롤러](https://programmers.co.kr/learn/courses/30/lessons/42627)

힙을 이용한 대표적인 문제 이다.

```python
import heapq
def solution(jobs):
    answer = 0
    jobs.sort(reverse = True)
    for e in jobs:
        e[0], e[1] = e[1], e[0]
    queue = []
    time = []
    real_time = 0
    while jobs or queue:
        if not queue:
            heapq.heappush(queue, jobs.pop())
        temp = heapq.heappop(queue)
        if real_time < temp[1]:
            real_time = temp[1]

        real_time += temp[0]
        time.append(real_time - temp[1])

        for i in reversed(range(len(jobs))):
            if jobs[i][1] <= real_time:
                heapq.heappush(queue, jobs.pop())
    answer = sum(time)//len(time)
    return answer
```
