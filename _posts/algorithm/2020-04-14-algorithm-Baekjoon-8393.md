---
title:  "[algorithm]BAEKJOON 백준 8393번 합"
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

# Baekjoon Online Judge No.8393

<https://www.acmicpc.net/problem/8393>

## 문제

n이 주어졌을 때, 1부터 n까지 합을 구하는 프로그램을 작성하시오.

## 입력

첫째 줄에 n (1 ≤ n ≤ 10,000)이 주어진다.

## 출력

1부터 n까지 합을 출력한다.

## 예제 입력 1

```
3
```

## 예제 출력 1 

```
6
```

## 코드

### C++

```c++
#include <iostream>
using namespace std;

int main(void)
{
	int n;
	int sum = 0;

	cin >> n;

	for (int i = 1; i <= n; i++)
	{
		sum += i;
	}
	cout << sum;

	return 0;

}
```

for 문을 이용하는 문제이다. 입력받을 변수와 합을 구하기 위한 변수를 만들고 1부터 n까지 for 문을 통해 합을 출력하도록 한다.