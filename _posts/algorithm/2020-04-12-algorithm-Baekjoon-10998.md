---
title:  "[algorithm]BAEKJOON 백준 10998번 A×B"
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

# Baekjoon Online Judge No.10998

<https://www.acmicpc.net/problem/10998>

## 문제

두 정수 A와 B를 입력받은 다음, A×B를 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 A와 B가 주어진다. (0 < A, B < 10)

## 출력

첫째 줄에 A×B를 출력한다.

## 예제 입력 1 

```
1 2
```

## 예제 출력 1 

```
2
```

## 예제 입력 2 

```
3 4
```

## 예제 출력 2 

```
12
```

## 알고리즘 분류

- [사칙연산](https://www.acmicpc.net/problem/tag/사칙연산)



## 코드

### C++

```c++
#include<iostream>
using namespace std;



int main()
{

	int a, b;
	cin >> a >> b;
	cout << a*b << endl;

	return 0;
}
```

두 숫자를 입력 받고 곱을 출력하는 문제이다. 입력 함수 cin을 이용해 숫자를 입력 받고 cout으로 출력해준다. 이대 a와 b의 곱을 위해 사칙 연산자 * 기호를 사용하여 곱을 출력해준다.