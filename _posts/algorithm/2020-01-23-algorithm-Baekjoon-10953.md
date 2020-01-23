---
title:  "[algorithm]BAEKJOON 백준 10953번 A+B - 6"
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

# Baekjoon Online Judge No.10953

[https://www.acmicpc.net/problem/10953](https://www.acmicpc.net/problem/10953)



## 문제

두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.



## 알고리즘 분류

- 사칙연산



## 입력

첫째 줄에 테스트 케이스의 개수 T가 주어진다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. A와 B는 콤마(,)로 구분되어 있다. (0 < A, B < 10)

## 출력

각 테스트 케이스마다 A+B를 출력한다.



## 예제 입력 

```markdown
5
1,1
2,3
3,4
9,8
5,2
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
	int a, b,T;
	char ch;
	cin >> T;
	for (int i = 0; i < T; i++)
	{
		cin >> a >> ch >> b;
		cout << a + b<<endl;
	}
}
```


