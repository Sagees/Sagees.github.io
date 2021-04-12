---
title: "[Algorithm] MST 정리 - Kruskal, Prim 알고리즘 정리"
date: 2021-04-13
categories: MST Kruskal Prim 알고리즘
toc: true
toc_sticky: true
---

## :white_check_mark: Kruskal's Algorithm

    Kruskal() {
    	T = {};
    	for each v in V
    		MakeSet(v);
    	sort E by increasing edge weight w
    	for each (u, v) in E (in sorted order)
    		if FindSet(u) != FindSet(v)
    			T = T + {{u, v}};
    			Union(FindSet(u), FindSet(v));
    }
	

## :white_check_mark: Prim's Algorithm

	Prim(G, w, r) {
		Q = V[G];
		for each u in Q
			key[u] = INF;
		key[r] = 0;
		p[r] = NULL;
		while (Q not empty) 
			u = ExtractMin(Q);
			for each v in Adj[u]
				if (v in Q and w(u,v) < key[v])
					p[v] = u;
					key[v] = w(u,v);
	}