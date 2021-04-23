---
title: "[Algorithm] Knapsack Problem 정리"
date: 2021-04-23
categories: Knapsack DP 알고리즘
toc: true
toc_sticky: true
---

## :white_check_mark: Knapsack Problem
Knapsack에 넣을 item들이 주어졌을 때 최대 가치를 얻는 문제이다. 각 item에는 **가중치와 가치**가 있다. 운반 가능한 총 중량은 **W**일 때, 각 item의 무게와 가치를 고려하여 **최대 가치**를 얻어야 된다.

<span style="color:blue">[0-1 Knapsack problem] solved by **dynamic programming**</span>
<span style="color:green">[Fractional Knapsack problem] solved by **greedy algorithm**</span>

<span style="color:grey">만약, Brute-Force Approach로 문제를 해결할 경우, 시간복잡도는 O(2^n)이 될 것이다.</span>

## :white_check_mark: Recursive Formula

| Bag value  | w(k) > w  | w(k) <= w  |
| :------------: | :------------: | :------------: |
| B[k, w]  | B[k-1, w]  | max(B[k-1, w], B[k-1, w-w(k)]+b(k))  |

```
for w = 0 to W
	B[0, w] = 0
for i = 0 to n
	B[i, 0] = 0
	for w = 0 to W
		if w(i) <= w
			if b(i) + B[i-1, w-w(i)] > B[i-1, w]
				B[i, w] = b(i) + B[i-1, w-w(i)]
			else
				B[i, w] = B[i-1, w]
		else B[i, w] = B[i-1, w]
```

** Then, 시간 복잡도는 O(nW)가 될 것이다.**