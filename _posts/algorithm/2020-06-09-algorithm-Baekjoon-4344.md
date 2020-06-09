---
title:  "[algorithm]BAEKJOON 백준 4344번 평균은 넘겠지"
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

# Baekjoon Online Judge No.4344

<https://www.acmicpc.net/problem/4344>

## 문제

대학생 새내기들의 90%는 자신이 반에서 평균은 넘는다고 생각한다. 당신은 그들에게 슬픈 진실을 알려줘야 한다.

## 입력

첫째 줄에는 테스트 케이스의 개수 C가 주어진다.

둘째 줄부터 각 테스트 케이스마다 학생의 수 N(1 ≤ N ≤ 1000, N은 정수)이 첫 수로 주어지고, 이어서 N명의 점수가 주어진다. 점수는 0보다 크거나 같고, 100보다 작거나 같은 정수이다.

## 출력

각 케이스마다 한 줄씩 평균을 넘는 학생들의 비율을 반올림하여 소수점 셋째 자리까지 출력한다.

## 예제 입력 1

```
5
5 50 50 70 80 100
7 100 95 90 80 70 60 50
3 70 90 80
3 70 90 81
9 100 99 98 97 96 95 94 93 91
```

## 예제 출력 1

```
40.000%
57.143%
33.333%
66.667%
55.556%
```

## 출처

[Contest ](https://www.acmicpc.net/category/45)> [Waterloo's local Programming Contests ](https://www.acmicpc.net/category/98)> [28 September, 2002](https://www.acmicpc.net/category/detail/504) D번

- 문제를 번역한 사람: [busyhuman](https://www.acmicpc.net/user/busyhuman)
- 문제의 오타를 찾은 사람: [choiking10](https://www.acmicpc.net/user/choiking10) [eric00513](https://www.acmicpc.net/user/eric00513)
- 어색한 표현을 찾은 사람: [djm03178](https://www.acmicpc.net/user/djm03178)

## 링크

- [PKU Judge Online](http://poj.org/problem?id=2350)
- [ZJU Online Judge](http://acm.zju.edu.cn/onlinejudge/showProblem.do?problemCode=1915)
- [TJU Online Judge](http://acm.tju.edu.cn/toj/showp1412.html)

## 코드	

### C++

```c++
#include<iostream>
#include<math.h>
using namespace std;


int main()
{

	int num;
	float per;
	cin >> num;

	for (int i = 0; i < num; i++)
	{
		int stuNum, sum = 0, Count = 0;
		float ave;
		cin >> stuNum;
		int *arr = new int[stuNum];
		for (int j = 0; j < stuNum; j++)
		{
			cin >> arr[j];
			sum += arr[j];
		}
		ave = sum / stuNum;
		for (int k = 0; k < stuNum; k++)
		{
			if (arr[k] > ave)
				Count++;
		}
		per = ((float)Count / stuNum) * 100;
		cout.precision(3);
		cout << fixed<< per<< '%' << '\n';
		delete[] arr;
	}


	return 0;
}
```

배열을 다루는 문제이다. 학생 수를 입력받게 되는데 학생의 점수 또한 학생 수만큼 입력을 받아야 하고 고정된 값이 아니기 때문에 동적할당을 통해 학생의 수만큼의 크기를 가진 배열을 할당해 준다. 점수를 입력받음과 동시에 총점을 구해주고 평균을 구한다.

평균을 넘는 학생들의 비율을 구하기 위해서 평균보다 점수가 높은 학생 수를 Count 해주고 백분율을 구해준다. 소수 셋째 자리까지 출력해 주기 위해서 precision 함수를 이용해 준다. 이 함수는 소수점 자리수를 조절해 주는데 단어의 뜻과 같이 출력 시 얼마의 정밀도로 나타낼 것인지 의미한다. fixed를 사용하는 이유는 precision로 설정해 준 정밀도 보다 적다면 0을 붙여서 정밀도 개수를 맞춰주기에 예제와 같이 40.000% 출력이 가능해진다.

> precision 함수의 설명 참조 블로그 https://modoocode.com/157 