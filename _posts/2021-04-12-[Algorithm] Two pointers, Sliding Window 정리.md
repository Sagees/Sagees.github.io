---
title: "[Algorithm] Two Pointers, Sliding Window 정리"
date: 2021-04-12
categories: TwoPointers SlidingWindow 알고리즘
toc: true
toc_sticky: true
---

## :white_check_mark: Two pointers

start, end 라는 2 개의 포인터(index 가리키는)를 사용한다.
start는 부분배열의 front index를 가리키고, end는 back index를 가리킨다.

<span style="color:red">start, end 둘다 0번째 index에서 시작하며, 항상 start<=end를 만족해야 한다.</span>

**부분 배열의 범위 [s, e)**

    while (s<=e && e<n)

* 부분 배열의 합 < 구하는 값
  * end를 오른쪽으로 한칸 이동 (++end), 배열 크기 증가
  * 합 += Array[e];
* 부분 배열의 합 >= 구하는 값
  * 합 -= Array[s];
  * start를 오른쪽으로 한칸 이동(start++), 배열 크기 감소
* 부분 배열의 합 == 구하는 값
  * result 계산

<span style="color:blue">**시간 복잡도 : O(n)**</span>

> 응용해서 다른 유형에서 s = 0, e = n-1로 두고 문제 해결할 수도 있음

## :white_check_mark: Sliding Window

####*DP여도 모든 **Memoization**이 필요하진 않다.*

**바로 이전 정보 + 현재 정보만 필요하다. 즉, 기존 배열에 덮어쓰기하여 다음 루프에서 사용이 가능하다.**
*플로이드 워셜 알고리즘*이 Sliding Window + DP 사용


`window size = 3`이고, `[7, 3, 5, 8, 1, 11, 4]` 배열에서 **가장 큰 부분합의 값**을 구하고 싶다고 가정하자.

<img src="https://user-images.githubusercontent.com/34927658/114418557-9720dd80-9bed-11eb-99c7-1735304f348f.jpg" width="450" height="450">

위의 그림과 같이, <span style="color:red">이전 window_start, 이전 window_sum, 그리고 현재 window_end 정보</span>만으로 충분히 다른 메모리 낭비없이 구현할 수 있다.

<span style="color:blue">**시간 복잡도 O(n), 공간 복잡도 O(1)**</span>
