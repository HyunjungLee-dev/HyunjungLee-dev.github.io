---
title:  "[algorithm]BAEKJOON 백준 2562번 최댓값"
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

# Baekjoon Online Judge No.2562

<https://www.acmicpc.net/problem/2562>

## 문제

9개의 서로 다른 자연수가 주어질 때, 이들 중 최댓값을 찾고 그 최댓값이 몇 번째 수인지를 구하는 프로그램을 작성하시오.

예를 들어, 서로 다른 9개의 자연수

3, 29, 38, 12, 57, 74, 40, 85, 61

이 주어지면, 이들 중 최댓값은 85이고, 이 값은 8번째 수이다.

## 입력

첫 째 줄부터 아홉 번째 줄까지 한 줄에 하나의 자연수가 주어진다. 주어지는 자연수는 100 보다 작다.

## 출력

첫째 줄에 최댓값을 출력하고, 둘째 줄에 최댓값이 몇 번째 수인지를 출력한다.

## 예제 입력 1 

```
3
29
38
12
57
74
40
85
61
```

## 예제 출력 1 

```
85
8
```

## 코드	

### C++

```c++
#include <iostream>
using namespace std;

int main()
{
	int index, arr[9];
	int max = 0;

	for (int i = 0; i < 9; i++)
	{
		cin >> arr[i];
		if (arr[i] > max)
		{
			max = arr[i];
			index = i;
		}
	}


	cout << max<< '\n' << index + 1 <<'\n';

	return 0;
}
```

1차원 배열을 이용하는 문제이다. 배열에 for 문을 통해 9개의 수를 입력받고 처음 입력된 수를 와 max 값을 비교해가며 최댓값을 구한다. 입력받은 정수의 비교가 끝났다면 max 값을 출력하고 index 값 또한 출력해 준다. 여기서 index 값은 몇 번째 수 인지 출력해 주기 위한 변수이므로 +1을 해준다.