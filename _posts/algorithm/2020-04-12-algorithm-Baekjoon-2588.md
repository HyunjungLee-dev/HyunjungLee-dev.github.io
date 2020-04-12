---
title:  "[algorithm]BAEKJOON 백준 2588번 곱셈"
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

# Baekjoon Online Judge No.2588

<https://www.acmicpc.net/problem/2588>

## 문제

(세 자리 수) × (세 자리 수)는 다음과 같은 과정을 통하여 이루어진다.

![img](https://www.acmicpc.net/upload/images/f5NhGHVLM4Ix74DtJrwfC97KepPl27s%20(1).png)

(1)과 (2)위치에 들어갈 세 자리 자연수가 주어질 때 (3), (4), (5), (6)위치에 들어갈 값을 구하는 프로그램을 작성하시오.

## 입력

첫째 줄에 (1)의 위치에 들어갈 세 자리 자연수가, 둘째 줄에 (2)의 위치에 들어갈 세자리 자연수가 주어진다.

## 출력

첫째 줄부터 넷째 줄까지 차례대로 (3), (4), (5), (6)에 들어갈 값을 출력한다.

## 예제 입력 1 

```
472
385
```

## 예제 출력 1

```
2360
3776
1416
181720
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
	cout << a * (b % 10) << endl;
	cout << a * ((b / 10) % 10) << endl;
	cout << a * (((b / 10) / 10) % 10) << endl;
	cout << a * b << endl;


	return 0;
}
```

% 연산자 응용하는 문제였다. % 연산자를 이용하면 숫자의 자리수 구분이 가능하다.

123이라는 숫자로 예를 들어보자

- 123 % 10 = 3
- 123 / 10 = 12
- 12 % 10 = 2
- 12 / 10 = 1
- 1 % 10 = 1

이걸 이용해 각 자리수의 값을 구할 수 있으며 숫자를 반대로 뒤집는 것도 가능하다. 위의 코드는 간단히 작성 가능하지만 가독성이 떨어지고 변수에 세 자리 이상이 들어오는 경우가 생길 수도 있다 때문에 밑의 코드와 같이 반복문을 이용할 수 있다.

```c++
#include <iostream>
using namespace std;

int main(void)
{
	int a, b,result;
	cin >> a>> b;
	result = a * b;
	while (b)
	{
		cout << b % 10 * a << endl;
		b /= 10;
	}
	cout << result << endl;

	return 0;

}
```

b % 10을 해주면 마지막 자릿수를 구할 수 있고 b/=10을 해줌으로써 곱이 끝난 자릿수를 제외한 수가 되고 다시 반복해서 b%10을 해주면 그 수의 마지막 자릿수를 구할 수 있게 된다.

