---
title: "[Algorithm] DFS, BFS 정리"
date: 2021-04-10
categories: DFS BFS 완전탐색 알고리즘
toc: true
toc_sticky: true
---

알고리즘의 기본, 그리고 기업의 코딩테스트 빈출 유형인 탐색 알고리즘 DFS, BFS에 대해 정리해보려고 한다.

개인적으로 이론은 다 이해를 했으나, 구현하는 데에서 많이 막힌 유형이라 계속 업데이트할 예정이다.

---
## :sparkles: DFS(Depth First Search)란?

**DFS는 깊이우선탐색 알고리즘**이다. 

#### pseudocode
    DFS(G) {
    	for each vertex u in G->V {
    		u->color = WHITE;
    	}
    	time = 0;
    	for each vertex u in G->V {
    		if (u->color = WHITE)
    			DFS_Visit(u);
    	}
    }
    
    DFS_Visit(u) {
    	u->color = GREY;
    	time = time+1;
    	u->d = time;
    	for each v in u->Adj[] {
    		if (v->color == WHITE)
    			DFS_Visit(v);
    	}
    	u->color = BLACK;
    	time = time+1;
    	u->f = time;
    }

## :sparkles: BFS(Breadth First Search)란?

**BFS는 너비우선탐색 알고리즘**이다. 

#### pseudocode
    BFS(G, s) {
    	initialize vetices;
    	Q = {s};
    	while (Q not empty) {
    		u = RemoveTop(Q);
    		for each v in u->adj {
    			if (v->color == WHITE) {
    				v->color = GREY;
    				v->d = u->d + 1;
    				v->p = u;
    				Enqueue(Q, v);
    			}
    		}
    		u->color = BLACK;
    	}
    }