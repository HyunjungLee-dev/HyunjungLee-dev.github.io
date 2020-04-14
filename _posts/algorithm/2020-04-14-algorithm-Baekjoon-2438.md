---
title:  "[algorithm]BAEKJOON 백준 2438번 별 찍기 - 1 "
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

# Baekjoon Online Judge No.2438

<https://www.acmicpc.net/problem/2438>

## 문제

첫째 줄에는 별 1개, 둘째 줄에는 별 2개, N번째 줄에는 별 N개를 찍는 문제

## 입력

첫째 줄에 N(1 ≤ N ≤ 100)이 주어진다.

## 출력

첫째 줄부터 N번째 줄까지 차례대로 별을 출력한다.

## 예제 입력 1 

```
5
```

## 예제 출력 1 

```
*
**
***
****
*****
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
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

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

	return 0;

}
```

for 문 문제이다. 이중 for 문을 사용하게 되는데 j는 0부터 시작해  i보다 작거나 같을 때까지 1씩 더해주게 된다. i가 0이면 j는 0이 되며 별이 한 개, i가 1이면 j는 0, 1이 되니 별이 두 개 이런 식으로 한 줄씩 n개의 별을 출력하게 되는 것이다.

```c++
#include <iostream>
#include<string>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	int n;
	string str;
	cin >> n;
	for (int i = 0; i < n; i++)
	{
		str += "*";
		cout << str<<'\n';
	}

	return 0;

}
```

이중 for 문을 사용하지 않고 string을 사용할 수도 있다. i가 1씩 늘어날 때마다 *을 str 문자열에 넣어주고 바로 출력해주는 방법이다.

