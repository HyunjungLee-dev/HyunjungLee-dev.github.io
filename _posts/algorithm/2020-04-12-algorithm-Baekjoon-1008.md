---
title:  "[algorithm]BAEKJOON 백준 1008번 A/B"
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

# Baekjoon Online Judge No.1008

<https://www.acmicpc.net/problem/1008>

## 문제

두 정수 A와 B를 입력받은 다음, A/B를 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 A와 B가 주어진다. (0 < A, B < 10)

## 출력

첫째 줄에 A/B를 출력한다. 실제 정답과 출력값의 절대오차 또는 상대오차가 10^-9 이하이면 정답이다.

## 예제 입력 1 

```
1 3
```

## 예제 출력 1 

```
0.33333333333333333333333333333333
```

10-9 이하의 오차를 허용한다는 말은 꼭 소수 9번째 자리까지만 출력하라는 뜻이 아니다.

## 예제 입력 2 

```
4 5
```

## 예제 출력 2 

```
0.8
```



## 알고리즘 분류

- [사칙연산](https://www.acmicpc.net/problem/tag/사칙연산)
- [수학](https://www.acmicpc.net/problem/tag/수학)



## 코드

### C++

```c++
#include<iostream>
using namespace std;



int main()
{

	double a, b;
	cin >> a >> b;
	cout.precision(15);
	cout << a / b << endl;

	return 0;
}
```

출력 결과로 소수가 나오기 때문에 정수형인 int가 아닌 실수형인 double을 사용하였고 문제에서  출력값의 절대오차 또는 상대오차가 10^-9 이하이면 정답이라고 하였기에 소수점 자릿수를 맞추어주어 출력하기 위해 precision 함수를 사용한다. 원형은  `streamsize precision(streamsize prec);`이며 prec에 새로운 부동 소수점 정밀도 값이 들어가게 된다.

> precision 함수 참고 사이트
>
> [모두의 코드](https://modoocode.com/157)