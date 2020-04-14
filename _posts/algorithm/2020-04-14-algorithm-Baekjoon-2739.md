---
title:  "[algorithm]BAEKJOON 백준 2739번 구구단"
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

# Baekjoon Online Judge No.2739

<https://www.acmicpc.net/problem/2739>

## 문제

N을 입력받은 뒤, 구구단 N단을 출력하는 프로그램을 작성하시오. 출력 형식에 맞춰서 출력하면 된다.

## 입력

첫째 줄에 N이 주어진다. N은 1보다 크거나 같고, 9보다 작거나 같다.

## 출력

출력형식과 같게 N*1부터 N*9까지 출력한다.

## 예제 입력 1

```
2
```

## 예제 출력 1 

```
2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
2 * 4 = 8
2 * 5 = 10
2 * 6 = 12
2 * 7 = 14
2 * 8 = 16
2 * 9 = 18
```

## 알고리즘 분류

- [출력](https://www.acmicpc.net/problem/tag/출력)

## 코드

### C++

```c++
#include <iostream>
using namespace std;

int main()
{
	int n;
	cin >> n;
	for (int i = 1; i <= 9; i++)
	{
		cout << n << " * " << i << " = " << n * i<<endl;
	}

	return 0;

}
```

```c++
#include <iostream>
#include<stdio.h>
using namespace std;

int main()
{
	int n;
	char buf[256];
	cin >> n;
	for (int i = 1; i <= 9; i++)
	{
		sprintf(buf, "%d * %d = %d",n,i,n*i);
		cout << buf<<endl;
	}

	return 0;

}
```

for 문을 이용하는 문제이다. 구구단은 1부터 9까지 곱한 결과가 나와야 하기에 1부터 9까지 for 문을 이용해 문장을 출력하였다. 이때 출력을 하기 위한 방식은 여러 가지가 될 수 있을 것이다.  cout 하나로 출력을 끝낼 수도 있고 <stdio.h> 헤더 파일에 있는 sprintf 함수를 통해 서식을 지정하여 문자열을 만들 수도 있다.