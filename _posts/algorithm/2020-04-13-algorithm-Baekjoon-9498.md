---
title:  "[algorithm]BAEKJOON 백준 9498번 시험 성적"
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

# Baekjoon Online Judge No.9498

<https://www.acmicpc.net/problem/9498>

## 문제

시험 점수를 입력받아 90 ~ 100점은 A, 80 ~ 89점은 B, 70 ~ 79점은 C, 60 ~ 69점은 D, 나머지 점수는 F를 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 시험 점수가 주어진다. 시험 점수는 0보다 크거나 같고, 100보다 작거나 같은 정수이다.

## 출력

시험 성적을 출력한다.

## 예제 입력 1 

```
100
```

## 예제 출력 1 

```
A
```

## 알고리즘 분류

- [구현](https://www.acmicpc.net/problem/tag/구현)

## 코드

### C++

```c++
#include<iostream>
using namespace std;


int main()
{
	int a;
	cin >> a;
	if (a >= 90 && a <= 100)
		cout << "A";
	else if (a >= 80 && a <= 89)
		cout << "B";
	else if (a >= 70 && a <= 79)
		cout << "C";
	else if (a >= 60 && a <= 69)
		cout << "D";
	else
		cout << "F";
	return 0;
}
```

if문을 사용하는 문제이다. 비교 연산자를 이용해 비교하는 조건식을 넣어주고 그게 true라면 해당 성적을 출력해준다.