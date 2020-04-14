---
title:  "[algorithm]BAEKJOON 백준 2742번 기찍 N "
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

# Baekjoon Online Judge No.2742

<https://www.acmicpc.net/problem/2742>

## 문제

자연수 N이 주어졌을 때, N부터 1까지 한 줄에 하나씩 출력하는 프로그램을 작성하시오.

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
5
4
3
2
1
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
	for (int i = n; i >= 1; i--)
	{
		cout << i << '\n';
	}

	return 0;
}
```

 2741번과 유사한 for 문 문제이다. int형 변수 n에 입력을 받은 후 n부터 1까지 for 문을 통해 차례대로 출력해준다.