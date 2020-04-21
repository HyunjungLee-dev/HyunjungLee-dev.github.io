---
title:  "[algorithm]BAEKJOON 백준 2446번 별 찍기 - 9 "
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

# Baekjoon Online Judge No.2446

<https://www.acmicpc.net/problem/2446>

## 문제

예제를 보고 규칙을 유추한 뒤에 별을 찍어 보세요.

## 입력

첫째 줄에 N(1 ≤ N ≤ 100)이 주어진다.

## 출력

첫째 줄부터 2×N-1번째 줄까지 차례대로 별을 출력한다.

## 예제 입력 1 

```
5
```

## 예제 출력 1 

```
*********
 *******
  *****
   ***
    *
   ***
  *****
 *******
*********
```

## 코드	

### C++

```c++
#include<iostream>
using namespace std;

int main()
{
	int n;
	cin >> n;

	for (int i = 0; i < n-1; i++)
	{
		for (int j = 0; j <i; j++)
		{
			cout << " ";
		}
		for (int k = 2 * (n - i)-1; k > 0; k--)
		{
			cout << "*";
		}
		cout << "\n";
	}

	for (int i = n-1; i >= 0; i--)
	{
		for (int j = 0; j < i; j++)
		{
			cout << " ";
		}
		for (int k =0; k < 2 * (n - i) - 1; k++)
		{
			cout << "*";
		}
		cout << "\n";
	}

	return 0;
}
```


