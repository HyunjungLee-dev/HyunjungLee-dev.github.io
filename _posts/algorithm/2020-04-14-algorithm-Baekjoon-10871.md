---
title:  "[algorithm]BAEKJOON 백준 10871번 X보다 작은 수"
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

# Baekjoon Online Judge No.10871

<https://www.acmicpc.net/problem/10871>

## 문제

정수 N개로 이루어진 수열 A와 정수 X가 주어진다. 이때, A에서 X보다 작은 수를 모두 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 N과 X가 주어진다. (1 ≤ N, X ≤ 10,000)

둘째 줄에 수열 A를 이루는 정수 N개가 주어진다. 주어지는 정수는 모두 1보다 크거나 같고, 10,000보다 작거나 같은 정수이다.

## 출력

X보다 작은 수를 입력받은 순서대로 공백으로 구분해 출력한다. X보다 작은 수는 적어도 하나 존재한다.

## 예제 입력 1 

```
10 5
1 10 4 9 2 3 8 5 7 6
```

## 예제 출력 1 

```
1 4 2 3
```

## 알고리즘 분류

- [구현](https://www.acmicpc.net/problem/tag/구현)



## 코드

### C++

```c++
#include <iostream>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	int n, x;
	cin >> n>>x;
	for (int i = 0; i < n; i++)
	{
		int num;
		cin >> num;
		if (temp < x)
			cout << num << " ";
	}
	return 0;

}
```

for 문과 if를 같이 사용하는 문제이며 수열을 저장하지 않고 수열을 입력받으면 x의 값과 바로 비교하여 작을 경우 출력하는 코드이다.

### C++ STL

```c++
#include <iostream>
#include<vector>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	int n, x;
	vector<int> v;
	cin >> n>>x;
	for (int i = 0; i < n; i++)
	{
		int temp;
		cin >> temp;
		v.push_back(temp);
	}
	for (int i = 0; i < v.size(); i++)
	{
		if (v[i] < x)
			cout << v[i] << " ";
	}


	return 0;

}
```

C++ STL의 vector 컨테이너를 사용한 코드이다. 입력받은 수열을 push_back()을 이용하여 v에 원소를 추가해 주고 vector는 배열 기반의 컨테이너이기 때문에 인덱스 접근이 가능하다. 그렇기에 size()로 원소의 개수만큼 for 문으로 x보다 작은 값들을 출력해 주도록 한다.