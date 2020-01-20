---
title:  "[algorithm]BAEKJOON 백준 10952번 A+B - 5"
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

# Baekjoon Online Judge No.10952

[https://www.acmicpc.net/problem/10952](https://www.acmicpc.net/problem/10952)



## 문제

두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.



## 알고리즘 분류

- 사칙연산



## 입력

입력은 여러 개의 테스트 케이스로 이루어져 있다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)

입력의 마지막에는 0 두 개가 들어온다.

## 출력

각 테스트 케이스마다 A+B를 출력한다.



## 예제 입력 

```markdown
1 1
2 3
3 4
9 8
5 2
0 0
```



## 예제 출력

```markdown
2
5
7
17
7
```



## 코드 

```c++
#include <iostream>
using namespace std;
int main()
{
	int a, b;
	while (1)
	{
		cin >> a >> b;
		if (a == 0 && b == 0)
			break;
		cout << a + b << endl;
	}
	return 0;
}
```

입력되는 a, b 의 조건을 추가하면 되는 문제이다. 입력 마지막에 0이 들어온다는 것은 a와 b가 0일 경우 반복이 끝나고 종료된다는 것이므로 즉, 입력받은 a와 b가 0일 경우 반복문을 끝내는 의 조건을 추가해주면 된다.

## 
