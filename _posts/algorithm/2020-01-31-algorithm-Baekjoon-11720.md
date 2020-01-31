---
title:  "[algorithm]BAEKJOON 백준 11720번 숫자의 합"
comments: true
toc : true
toc_sticky : true
categories:
  - algorithm
tags:
  - Baekjoon
  - C++
  - C
  - algorithm
---

# Baekjoon Online Judge No.11720

[https://www.acmicpc.net/problem/11720](https://www.acmicpc.net/problem/11720)

## 문제

N개의 숫자가 공백 없이 쓰여있다. 이 숫자를 모두 합해서 출력하는 프로그램을 작성하시오.

## 알고리즘 분류

- 출력



## 입력

첫째 줄에 숫자의 개수 N (1 ≤ N ≤ 100)이 주어진다. 둘째 줄에 숫자 N개가 공백없이 주어진다.

## 출력

입력으로 주어진 숫자 N개의 합을 출력한다.



## 예제 입력 1

```
1
1  
```

## 예제 출력 1

```
1
```



## 예제 입력 2

```
5
54321
```

## 예제 출력 2

```
15
```



## 예제 입력 3

```
25
7000000000000000000000000
```

## 예제 출력 3

```
7
```



## 예제 입력 4

```
11
10987654321
```

## 예제 출력 4

```
46
```



## 코드

- 코드 1

```c++
#include<iostream>
using namespace std;

int main()
{
	int n;
	char c;
	int sum = 0;

	cin >> n;//1
	for (int i = 0; i < n; i++)
	{
		cin >> c;
		sum += c - '0';//아스키코드에 대한 지식 필요 문자->정수
	}
	cout << sum;
	return 0;
}
```

- 코드 2

```c
#include<stdio.h>

int main()
{
	int n;
	int sum = 0;
	scanf("%d", &n);
	for (int i = 0; i < n; i++)
	{
		int num;
		scanf("%1d", &num);
		sum += num;
	}
	printf("%d", sum);
	return 0;
}
```

숫자가 연속 되어 입력이 되었을때 `scanf("%1d",&변수);` 를 통해 하나씩 받을 수 있다.