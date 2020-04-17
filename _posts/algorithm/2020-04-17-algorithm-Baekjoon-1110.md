---
title:  "[algorithm]BAEKJOON 백준 1110번 더하기 사이클"
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

# Baekjoon Online Judge No.1110

<https://www.acmicpc.net/problem/1110>

## 문제

0보다 크거나 같고, 99보다 작거나 같은 정수가 주어질 때 다음과 같은 연산을 할 수 있다. 먼저 주어진 수가 10보다 작다면 앞에 0을 붙여 두 자리 수로 만들고, 각 자리의 숫자를 더한다. 그 다음, 주어진 수의 가장 오른쪽 자리 수와 앞에서 구한 합의 가장 오른쪽 자리 수를 이어 붙이면 새로운 수를 만들 수 있다. 다음 예를 보자.

26부터 시작한다. 2+6 = 8이다. 새로운 수는 68이다. 6+8 = 14이다. 새로운 수는 84이다. 8+4 = 12이다. 새로운 수는 42이다. 4+2 = 6이다. 새로운 수는 26이다.

위의 예는 4번만에 원래 수로 돌아올 수 있다. 따라서 26의 사이클의 길이는 4이다.

N이 주어졌을 때, N의 사이클의 길이를 구하는 프로그램을 작성하시오.

## 입력

첫째 줄에 N이 주어진다. N은 0보다 크거나 같고, 99보다 작거나 같은 정수이다.

## 출력

첫째 줄에 N의 사이클 길이를 출력한다.

## 예제 입력 1 

```
26
```

## 예제 출력 1 

```
4
```

## 예제 입력 2 

```
55
```

## 예제 출력 2 

```
3
```

## 예제 입력 3 

```
1
```

## 예제 출력 3

```
60
```

## 알고리즘 분류

- [수학](https://www.acmicpc.net/problem/tag/수학)



## 코드	

### C++

```c++
#include<iostream>
using namespace std;

int main()
{
	int n,cycle = 0;   
	int a, b, sum, num;
	cin >> n;

	while (1)
	{
		if (cycle == 0)
		{
			if (n <= 0)
				a = 0;
			else
				a = n / 10;
			b = n % 10;
		}
		else
		{
			a = num / 10;
			b = num % 10;
		}
		sum = a + b;
		if (sum > 9)
			num = (b * 10) + sum % 10;
		else
			num = (b * 10) + sum;
		cycle++;
		if (num == n)
			break;
	}
	cout << cycle;
	return 0;
}
```

첫 번째 코드이다. 하나하나 조건을 생각하고 구현을 한다고 코드가 길어졌다.

```c++
#include<iostream>
using namespace std;

int main()
{
	int n,cycle = 0;   
	int fnum, bnum;
	int temp;

	cin >> n;
	temp = n;

	while (1)
	{
		fnum = temp / 10;
		bnum = temp % 10;

		temp = bnum * 10 + ((fnum + bnum) % 10);
		cycle++;

		if (temp == n)
		{
			cout << cycle;
			break;
		}
	}
	return 0;
}
```

두 번째 코드이다. 선언한 변수도 코드의 길이도 짧아졌다.

이 문제는 while 문을 사용하는 문제이다. 필요한 변수는 처음 입력받는 수, 십의 자리수, 일의 자리수, 처음 입력받는 수를 가진 수이다. 처음 입력받은 수를 temp에 넣어주고 temp를 10으로 나누면 십의 자리수가 나오며 10으로 나눈 나머지는 일의 자리수가 나온다. 그것을 문제와 같이 새로운 수를 만들어 temp에 넣어준다. 그렇게 반복될 때마다 cycle은 1씩 더해지고 temp가 처음 받은 수 n과 같아지만 cycle을 출력하고 반복문은 끝나게 된다.