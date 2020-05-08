---
title:  "[algorithm]BAEKJOON 백준 2577번 숫자의 개수"
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

# Baekjoon Online Judge No.2577

<https://www.acmicpc.net/problem/2577>

## 문제

세 개의 자연수 A, B, C가 주어질 때 A×B×C를 계산한 결과에 0부터 9까지 각각의 숫자가 몇 번씩 쓰였는지를 구하는 프로그램을 작성하시오.

예를 들어 A = 150, B = 266, C = 427 이라면 

A × B × C = 150 × 266 × 427 = 17037300 이 되고, 

계산한 결과 17037300 에는 0이 3번, 1이 1번, 3이 2번, 7이 2번 쓰였다.

## 입력

첫째 줄에 A, 둘째 줄에 B, 셋째 줄에 C가 주어진다. A, B, C는 모두 100보다 같거나 크고, 1,000보다 작은 자연수이다.

## 출력

첫째 줄에는 A×B×C의 결과에 0 이 몇 번 쓰였는지 출력한다. 마찬가지로 둘째 줄부터 열 번째 줄까지 A×B×C의 결과에 1부터 9까지의 숫자가 각각 몇 번 쓰였는지 차례로 한 줄에 하나씩 출력한다.

## 예제 입력 1

```
150
266
427
```

## 예제 출력 1 

```
3
1
0
2
0
0
0
2
0
0
```

## 코드	

### C++

```c++
#include <iostream>
using namespace std;

int main()
{
	int result;
	int a,b,c;
	int arr[10] = { 0 };

	cin >> a >> b >> c;
	result = a * b*c;

	while (result > 0)
	{
		arr[result % 10]++;
		result /= 10;
	}

	for (int i = 0; i < 10; i++)
	{
		cout << arr[i] << '\n';
	}

	return 0;
}
```

1차원 배열을 이용하는 문제이다. `arr[result % 10]++;` % 연산을 이용하면 숫자의 자리수 구분이 가능하다. % 10을 해주게 되면 첫째 자리의 숫자가 나오게 되고 ++로 배열에 +1을 해준다. `result /= 10;` 첫째 자리 숫자를 구했으니 그 수를 제외하기 위해 /10을 해주면 첫째 자리를 제외한 수가 되고 이를 반복해 주게 되면 해당 수에 숫자가 몇 번 쓰였는지를 알 수 있게 된다.

