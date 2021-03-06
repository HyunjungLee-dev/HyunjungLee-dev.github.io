---
title:  "[algorithm]BAEKJOON 백준 10773번 제로"
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

# Baekjoon Online Judge No.10773

<https://www.acmicpc.net/problem/10773>

## 문제

나코더 기장 재민이는 동아리 회식을 준비하기 위해서 장부를 관리하는 중이다.

재현이는 재민이를 도와서 돈을 관리하는 중인데, 애석하게도 항상 정신없는 재현이는 돈을 실수로 잘못 부르는 사고를 치기 일쑤였다.

재현이는 잘못된 수를 부를 때마다 0을 외쳐서, 가장 최근에 재민이가 쓴 수를 지우게 시킨다.

재민이는 이렇게 모든 수를 받아 적은 후 그 수의 합을 알고 싶어 한다. 재민이를 도와주자!

## 입력

첫 번째 줄에 정수 K가 주어진다. (1 ≤ K ≤ 100,000)

이후 K개의 줄에 정수가 1개씩 주어진다. 정수는 0에서 1,000,000 사이의 값을 가지며, 정수가 "0" 일 경우에는 가장 최근에 쓴 수를 지우고, 아닐 경우 해당 수를 쓴다.

정수가 "0"일 경우에 지울 수 있는 수가 있음을 보장할 수 있다.

## 출력

재민이가 최종적으로 적어 낸 수의 합을 출력한다. 최종적으로 적어낸 수의 합은 231-1보다 작거나 같은 정수이다.

## 예제 입력 1 

```
4
3
0
4
0
```

## 예제 출력 1 

```
0
```

## 예제 입력 2 

```
10
1
3
5
4
0
0
7
0
0
6
```

## 예제 출력 2

```
7
```

## 힌트

예제 2의 경우를 시뮬레이션 해보면,

- [1]
- [1,3]
- [1,3,5]
- [1,3,5,4]
- [1,3,5] (0을 불렀기 때문에 최근의 수를 지운다)
- [1,3] (0을 불렀기 때문에 그 다음 최근의 수를 지운다)
- [1,3,7]
- [1,3] (0을 불렀기 때문에 최근의 수를 지운다)
- [1] (0을 불렀기 때문에 그 다음 최근의 수를 지운다)
- [1,6]

합은 7이다.

## 코드	

### C++

```c++
#include<iostream>
#include<stack>
using namespace std;



int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);


	stack<int> s;
	int k, result = 0;

	cin >> k;
	for (int i = 0; i < k; i++)
	{
		int n;
		cin >> n;
		if (n == 0)
			s.pop();
		else
		{
			s.push(n);
		}
	}

	while(!s.empty())
	{
		result += s.top();
		s.pop();
	}

	cout << result;


}
```

stack을 이용하여 풀 수 있는 문제이다. stack은 LIFO로 마지막에 들어온 값이 가장 먼저 나가는 자료구조로 문제와 같이 마지막으로 들어온 값이 잘못되어 지우게 해야 하는 것이니깐 stack을 이용하는 것이 좋을 것이다.

문제를 보면 정수가 "0"일 경우에는 가장 최근에 쓴 수를 지우고(pop), 아닐 경우 해당 수를 쓴다(push). 정수를 입력받고 0일 경우는 pop으로 지우고 아닐 경우 push로 넣어준다. 최종적으로는 stack 안에 있는 모든 수의 합을 구하기 위해서 `result += s.top();`와 같이 top()은 통해 스택의 가장 끝에 있는 원소를 반환해 주기에 그 값을 더해주고 다음 값을 더하기 위해 가장 끝, 즉 마지막 값은 pop()을 통해 삭제해 준다.