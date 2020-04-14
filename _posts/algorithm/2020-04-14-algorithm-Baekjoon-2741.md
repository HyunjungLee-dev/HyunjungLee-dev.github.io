---
title:  "[algorithm]BAEKJOON 백준 2741번 N 찍기"
comments: true
toc : true
toc_sticky : true
categories:
  - algorithm
tags:
  - Baekjoon
  - C++
  - algorithm
---

# Baekjoon Online Judge No.2741

<https://www.acmicpc.net/problem/2741>

## 문제

자연수 N이 주어졌을 때, 1부터 N까지 한 줄에 하나씩 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 100,000보다 작거나 같은 자연수 N이 주어진다.

## 출력

첫째 줄부터 N번째 줄 까지 차례대로 출력한다.

## 예제 입력 1 

```
5
```

## 예제 출력 1 

```
1
2
3
4
5
```

## 알고리즘 분류

- [출력](https://www.acmicpc.net/problem/tag/출력)

## 코드

### C++

```c++
#include <iostream>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	int n;
	cin >> n;
	for (int i = 1; i <= n; i++)
	{
		cout << i << '\n';
	}

	return 0;

}
```

for 문 문제이다. int형 변수 n에 입력을 받은 후 1부터 n까지 for 문을 통해 차례대로 출력해준다.