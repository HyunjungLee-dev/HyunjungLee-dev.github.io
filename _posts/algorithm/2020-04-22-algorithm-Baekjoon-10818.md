---
title:  "[algorithm]BAEKJOON 백준 10818번 최소, 최대 "
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

# Baekjoon Online Judge No.10818

<https://www.acmicpc.net/problem/10818>

## 문제

N개의 정수가 주어진다. 이때, 최솟값과 최댓값을 구하는 프로그램을 작성하시오.

## 입력

첫째 줄에 정수의 개수 N (1 ≤ N ≤ 1,000,000)이 주어진다. 둘째 줄에는 N개의 정수를 공백으로 구분해서 주어진다. 모든 정수는 -1,000,000보다 크거나 같고, 1,000,000보다 작거나 같은 정수이다.

## 출력

첫째 줄에 주어진 정수 N개의 최솟값과 최댓값을 공백으로 구분해 출력한다.

## 예제 입력 1 

```
5
20 10 35 30 7
```

## 예제 출력 1 

```
7 35
```

## 코드	

### C++

```c++
#include <iostream>
using namespace std;

int main()
{
	int n,min, max;
	cin >> n;
	
	int *arr = new int[n];

	for (int i = 0; i < n; i++)
	{
		cin >> arr[i];
	}

	min = arr[0];
	max = arr[0];

	for (int i = 1; i < n; i++)
	{
		if (arr[i] < min)
			min = arr[i];
		if (arr[i] > max)
			max = arr[i];
	}

	cout << min << " " << max;
	delete[] arr;

	return 0;
}
```

1차원 배열을 이용하는 문제이다. 정수 n 개를 입력받고 동적할당을 통해 배열을 만들어준다. for 문을 통해 n 개의 수를 입력받고 처음 입력된 수를 기준으로 값을 비교해가며 최솟값, 최댓값을 구한다. 마지막으로 출력을 하고 동적할당을 해주었기 때문에 해제도 해주어야 한다. delete를 통해 할당받은 메모리의 해제를 해준다.

