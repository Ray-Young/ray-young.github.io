---
layout: post
title: "Back Tracking Algorithm"
date: 2016-09-08
comments: true
---

### Back tracking
Mostly back tracking need to use recursive algorithm. Some times such problem 
can be solved with dynamic programming algorithm.

### Question
Climbing Stairs is a typical back tracking problem. 

You are climbing a stair case. It takes n steps to reach to the top.

Each time you can either climb 1 or 3 steps. In how many distinct ways can you climb to the top? Give all solution sets.

### Solution 1:  Back Tracking
```java
	if (i == 0 && distance > 0) {
		solution.add(1);
		distance--;
		// Trick. If you use distance - 1, it will make the back track fail, because one set is not removed.
		helper(results, solution, distance, 1);
		distance++; 
	} 
	else if (i == 1 && distance >= 3) {
		solution.add(3); 
		distance = distance - 3; 
		helper(results, solution, distance, 3); 
		distance = distance + 3; 
		solution.remove(solution.size() - 1); 
	}
```

### Solution 2: DP
Also, you can solve this problem by dynamic programming. If there is k1 ways to reach n-3, k2 ways to reach n-1, then it must be k1 + k2 ways to reach k.

```java
	int three_step_before = 3;
	int one_step_before = 1;
	int all_ways;
	for (int i = 3; i < n; i++) {
	    all_ways = three_step_before + one_step_before;
	    three_step_before = one_step_before;
	    one_step_before = all_ways;
	}
```

This algorithm will calculate the number of all distinct sets.
