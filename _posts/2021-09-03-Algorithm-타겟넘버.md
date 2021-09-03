---
title: "타겟 넘버"
date: 2021-09-03 22:43:12 +0900
categories: algorithm
tags: programmers BFS DFS level2
---

## [타겟 넘버](https://programmers.co.kr/learn/courses/30/lessons/43165)

프로그래머스 bfs/dfs 알고리즘 고득점 kit에 있는 level2 난이도 문제 입니다.
개인적으로 level2보다 높아야 하지 않을 까? 할 정도로 푸는 데 굉장히 애먹었던 문제입니다.

array를 입력받고 덧셈뺄셈을 이용하여 target값이 나오는 지 확인해야 합니다.
모든 값을 다 해보아야 하므로 두가지 길이 있다고 생각하면 됩니다.
덧셈으로 가는 길과 뺄셈으로 가는 길 둘중 하나를 선택하고 끝까지 도착하여 계산한 결과값이 target과 같으면 정답에 1을 더해줍니다.

```python
answer = 0
def dfs(array,i,cnt,target):
    global answer
    if i == len(array):
        if cnt == target:
            answer += 1
        return None
    dfs(array,i+1,cnt+array[i],target)
    dfs(array,i+1,cnt-array[i],target)

def solution(numbers, target):

    dfs(numbers,0,0,target)
    return answer
```

bfs/dfs문제인가? 생각해보면 끼워 맞추기라고 생각합니다.
