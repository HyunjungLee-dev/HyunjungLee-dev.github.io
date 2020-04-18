---
title:  "[algorithm]BAEKJOON 백준 10817번 세 수 "
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

# Baekjoon Online Judge No.10817

<https://www.acmicpc.net/problem/10817>



## 문제

세 정수 A, B, C가 주어진다. 이때, 두 번째로 큰 정수를 출력하는 프로그램을 작성하시오. 

## 입력

첫째 줄에 세 정수 A, B, C가 공백으로 구분되어 주어진다. (1 ≤ A, B, C ≤ 100)

## 출력

두 번째로 큰 정수를 출력한다.

## 예제 입력 1 

```
20 30 10
```

## 예제 출력 1 

```
20
```

## 예제 입력 2 

```
30 30 10
```

## 예제 출력 2 

```
30
```

## 예제 입력 3 

```
40 40 40
```

## 예제 출력 3 

```
40
```

## 예제 입력 4 

```
20 10 10
```

## 예제 출력 4 

```
10
```

## 코드	

### C++

```c++
#include <iostream>
using namespace std;

int main() {
	int a, b, c, result;
	cin >> a >> b >> c;
	if (a >= b && a >= c)
	{
		if (b > c) result = b;
		else result = c;
	}
	else if (b >= a && b >= c)
	{
		if (a > c) result = a;
		else result = c;
	}
	else 
	{
		if (a > b) result = a;
		else result = b;
	}
	cout << result;
}
```

if 문으로 a가 가장 클 때, b가 가장 클 때, c가 가장 클 때를 조건식으로 하여 비교한 후 두 번째로 큰 정수를 result 변수에 넣어 출력할 수 있다.

```c++
#include <iostream>
#include<algorithm>
using namespace std;

int main() {
	int arr[3];
	for (int i = 0; i < 3; i++)
	{
		cin >> arr[i];
	}
	sort(arr, arr + 3);
	cout << arr[1];
}
```

이 코드는 sort 알고리즘을 이용한 코드이다. 배열을 통해 세 개의 수를 입력받고 sort 함수를 통해 default(오름차순)으로 정렬한다. 그 후 두 번째로 큰 정수를 출력해야 하기 때문에 arr[1]을 출력해 준다.