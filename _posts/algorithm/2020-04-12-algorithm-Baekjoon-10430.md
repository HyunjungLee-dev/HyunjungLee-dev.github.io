---
title:  "[algorithm]BAEKJOON 백준 10430번 나머지"
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

# Baekjoon Online Judge No.10430

<https://www.acmicpc.net/problem/10430>

## 문제

(A+B)%C는 ((A%C) + (B%C))%C 와 같을까?

(A×B)%C는 ((A%C) × (B%C))%C 와 같을까?

세 수 A, B, C가 주어졌을 때, 위의 네 가지 값을 구하는 프로그램을 작성하시오.

## 입력

첫째 줄에 A, B, C가 순서대로 주어진다. (2 ≤ A, B, C ≤ 10000)

## 출력

첫째 줄에 (A+B)%C, 둘째 줄에 ((A%C) + (B%C))%C, 셋째 줄에 (A×B)%C, 넷째 줄에 ((A%C) × (B%C))%C를 출력한다.

## 예제 입력 1 

```
5 8 4
```

## 예제 출력 1 

```
1
1
0
0
```

## 알고리즘 분류

- [사칙연산](https://www.acmicpc.net/problem/tag/사칙연산)
- [나머지 연산](https://www.acmicpc.net/problem/tag/나머지 연산)

## 코드

### C++

```c++
#include<iostream>
using namespace std;



int main()
{

	int a, b,c;
	cin >> a >> b>>c;
	cout << (a+b)%c<< endl;
	cout << ((a%c)+(b%c))%c<< endl;
	cout << (a*b)%c << endl;
	cout << ((a%c)*(b%c))%c << endl;


	return 0;
}
```

a,b,c 세 변수를 선언하고 입력을 받은 후 나머지 연산식을 출력하는 문제이다.