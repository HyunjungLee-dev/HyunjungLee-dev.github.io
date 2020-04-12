---
title:  "[algorithm]BAEKJOON 백준 10869번 사칙연산"
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

# Baekjoon Online Judge No.10869

<https://www.acmicpc.net/problem/10869>

## 문제

두 자연수 A와 B가 주어진다. 이때, A+B, A-B, A*B, A/B(몫), A%B(나머지)를 출력하는 프로그램을 작성하시오. 

## 입력

두 자연수 A와 B가 주어진다. (1 ≤ A, B ≤ 10,000)

## 출력

첫째 줄에 A+B, 둘째 줄에 A-B, 셋째 줄에 A*B, 넷째 줄에 A/B, 다섯째 줄에 A%B를 출력한다.

## 예제 입력 1

```
7 3
```

## 예제 출력 1

```
10
4
21
2
1
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
	cout << a + b << endl;
	cout << a - b << endl;
	cout << a * b << endl;
	cout << a / b << endl;
	cout << a % b << endl;

	return 0;
}
```

사칙 연산자를 사용하고 결과 값을 출력하는 문제이다. 입력 함수 cin을 이용해 숫자를 입력 받고 cout으로 출력해준다. 