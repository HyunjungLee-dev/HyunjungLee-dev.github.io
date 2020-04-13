---
title:  "[algorithm]BAEKJOON 백준 1330번 두 수 비교하기"
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

# Baekjoon Online Judge No.1330

<https://www.acmicpc.net/problem/1330>

## 문제

두 정수 A와 B가 주어졌을 때, A와 B를 비교하는 프로그램을 작성하시오.

## 입력

첫째 줄에 A와 B가 주어진다. A와 B는 공백 한 칸으로 구분되어져 있다.

## 출력

첫째 줄에 다음 세 가지 중 하나를 출력한다.

- A가 B보다 큰 경우에는 '`>`'를 출력한다.
- A가 B보다 작은 경우에는 '`<`'를 출력한다.
- A와 B가 같은 경우에는 '`==`'를 출력한다.

## 제한

- -10,000 ≤ A, B ≤ 10,000

## 예제 입력 1 

```
1 2
```

## 예제 출력 1 

```
<
```

## 예제 입력 2 

```
10 2
```

## 예제 출력 2 

```
>
```

## 예제 입력 3 

```
5 5
```

## 예제 출력 3 

```
==
```

## 코드

### C++

```c++
#include<iostream>
using namespace std;


int main()
{
	int a, b;
	cin >> a >> b;
	if (a > b)
		cout << ">";
	else if (a < b)
		cout << "<";
	else
		cout << "==";
	return 0;
}
```

if문을 사용하는 문제이다. 비교 연산자를 이용해 비교하는 조건식을 넣어주고 그게 true라면 해당 비교 연산자를 출력한다.