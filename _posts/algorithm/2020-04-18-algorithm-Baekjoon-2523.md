---
title:  "[algorithm]BAEKJOON 백준 2523번 별 찍기 - 13"
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

# Baekjoon Online Judge No.2523

<https://www.acmicpc.net/problem/2523>

## 입력

첫째 줄에 N(1 ≤ N ≤ 100)이 주어진다.

## 출력

첫째 줄부터 2×N-1번째 줄까지 차례대로 별을 출력한다.

## 예제 입력 1 

```
3
```

## 예제 출력 1 

```
*
**
***
**
*
```

## 코드	

### C++

```c++
#include <iostream>
using namespace std;

int main() {
	int n;
	cin >> n;

	for (int i = 0; i < n; i++)
	{
		for (int j = 0; j <= i; j++)
		{
			cout << "*";
		}
		cout << "\n";
	}
	for (int i = n-1; i >0; i--)
	{
		for (int j =0; j<i; j++)
		{
			cout << "*";
		}
		cout << "\n";
	}
	return 0;
}
```

위아래를 따로 출력한다고 생각하면 된다. 위의 for 문은 찍히는 별이 늘어나도록 밑의 for 문은 반대로 줄어들도록 한다.

```c++
#include <iostream>
#include <algorithm>
using namespace std;
 
int main(int argc, char* argv[])
{
	int n;
 
	cin >> n;
 
	for (int i = 1; i <= n * 2 - 1; ++i) {
		for (int j = 1; j <= n - abs(n - i); ++j) {
			cout << "*";
		}
		cout << "\n";
	}
 
	return 0;
}
```

> https://j3sung.tistory.com/390?category=318509

다른 방법을 찾아보니 위와 같은 코드로도 출력이 가능하다. 사용되는 메모리는 같지만 코드의 길이를 훨씬 줄일 수 있다. 위 코드에서 사용된 abs() 함수는 절댓값을 구할 수 있는 함수이다. -1을 곱해주어도 절댓값을 구할 수 있지만 abs 함수를 사용함으로써 가독성을 높일 수 있다.