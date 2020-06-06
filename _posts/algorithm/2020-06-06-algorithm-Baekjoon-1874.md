---
title:  "[algorithm]BAEKJOON 백준 1874번 스택 수열"
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

# Baekjoon Online Judge No.1874

<https://www.acmicpc.net/problem/1874>

## 문제

스택 (stack)은 기본적인 자료구조 중 하나로, 컴퓨터 프로그램을 작성할 때 자주 이용되는 개념이다. 스택은 자료를 넣는 (push) 입구와 자료를 뽑는 (pop) 입구가 같아 제일 나중에 들어간 자료가 제일 먼저 나오는 (LIFO, Last in First out) 특성을 가지고 있다.

1부터 n까지의 수를 스택에 넣었다가 뽑아 늘어놓음으로써, 하나의 수열을 만들 수 있다. 이때, 스택에 push하는 순서는 반드시 오름차순을 지키도록 한다고 하자. 임의의 수열이 주어졌을 때 스택을 이용해 그 수열을 만들 수 있는지 없는지, 있다면 어떤 순서로 push와 pop 연산을 수행해야 하는지를 알아낼 수 있다. 이를 계산하는 프로그램을 작성하라.

## 입력

첫 줄에 n (1 ≤ n ≤ 100,000)이 주어진다. 둘째 줄부터 n개의 줄에는 수열을 이루는 1이상 n이하의 정수가 하나씩 순서대로 주어진다. 물론 같은 정수가 두 번 나오는 일은 없다.

## 출력

입력된 수열을 만들기 위해 필요한 연산을 한 줄에 한 개씩 출력한다. push연산은 +로, pop 연산은 -로 표현하도록 한다. 불가능한 경우 NO를 출력한다.

## 예제 입력 1 

```
8
4
3
6
8
7
5
2
1
```

## 예제 출력 1 

```
+
+
+
+
-
-
+
+
-
+
+
-
-
-
-
-
```

## 예제 입력 2 

```
5
1
2
5
3
4
```

## 예제 출력 2 

```
NO
```

## 힌트

1부터 n까지에 수에 대해 차례로 [push, push, push, push, pop, pop, push, push, pop, push, push, pop, pop, pop, pop, pop] 연산을 수행하면 수열 [4, 3, 6, 8, 7, 5, 2, 1]을 얻을 수 있다.

## 출처

- 문제를 만든 사람: [author5](https://www.acmicpc.net/user/author5)
- 문제의 오타를 찾은 사람: [bgjuw12](https://www.acmicpc.net/user/bgjuw12)
- 데이터를 추가한 사람: [djm03178](https://www.acmicpc.net/user/djm03178)

## 알고리즘 분류

- [스택](https://www.acmicpc.net/problem/tag/스택)

## 코드	

### C++

```c++
#include <iostream>
#include <vector>
#include<stack>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	int n;
	vector<int> v;
	vector<char> v2;
	stack<int> s;
	int num = 0;

	cin >> n;
	for (int i = 0; i < n; i++)
	{
		int k;
		cin >> k;
		v.push_back(k);
	}

	for (int i = 1; i <= n; i++)
	{
		s.push(i);
		v2.push_back('+');
		while (!s.empty())
		{
			if (s.top() == v[num])
			{
				s.pop();
				v2.push_back('-');
				num++;
			}
			else
				break;
		}
	}

	if (s.empty())
	{
		for (int i = 0; i < v2.size(); i++)
		{
			cout << v2[i] << '\n';
		}
	}
	else
		cout << "NO" << '\n';

	return 0;
}
```

스택(stack)을 이용하여 해결하는 문제이다. 

```c++
cin >> n;
	for (int i = 0; i < n; i++)
	{
		int k;
		cin >> k;
		v.push_back(k);
	}
```

임의의 수열을 입력받기 위해 반복문을 이용하여 정수를 입력받고 vector에 push_back()을 통해 값을 넣어준다.

```c++
for (int i = 1; i <= n; i++)
	{
		s.push(i);
		v2.push_back('+');
		while (!s.empty())
		{
			if (s.top() == v[num])
			{
				s.pop();
				v2.push_back('-');
				num++;
			}
			else
				break;
		}
	}
```

1부터 n까지의 수를 스택에 넣어 만든 수열을 vector(v)에 추가했던 임의의 수열을 스택을 이용해 만들 수 있는가를 확인해야 한다.

stack(s)에 i부터 n까지 push를 하게 된다. 이때 stack(s)의 top과 임의의 수열을 받았던 벡터의 값과 비교를 해준다. 같으면 pop 해주고 다음 값을 비교한다. 또한 수열을 만들기 위해 push의 경우 '+', pop의 경우 '-'로 표현해야 하기 때문에 벡터(v2)에 추가해 준다.



[위의 예제의 값으로 실행 했을때]

| i = 1 | + s.top() = 1   | v[0] = 4 |
| ----- | --------------- | -------- |
| i= 2  | + s.top() = 2   | v[0] = 4 |
| i = 3 | + s.top() = 3   | v[0] = 4 |
| i = 4 | + - s.top() = 4 | v[0] = 4 |
|       | - s.top() = 3   | v[1] = 3 |
|       | s.top() = 2     | v[2] = 6 |
| i = 5 | + s.top() = 5   | v[2] = 6 |
| i = 6 | + - s.top() = 6 | v[2] = 6 |
|       | s.top() = 5     | v[3] = 8 |
| i = 7 | + s.top() = 7   | v[3] = 8 |
| i = 8 | + - s.top() = 8 | v[3]= 8  |
|       | - s.top() = 7   | v[4] = 7 |
|       | - s.top() = 5   | v[5] = 5 |
|       | - s.top() = 2   | v[6] = 2 |
|       | - s.top() = 1   | v[7] = 1 |

위와 같이 실행되면 pop 되어 스택은 비게 된다. 

```c++
if (s.empty())
	{
		for (int i = 0; i < v2.size(); i++)
		{
			cout << v2[i] << '\n';
		}
	}
	else
		cout << "NO" << '\n';

```

최종적으로 비어 있으면 연산의 +, -를 추가했던 v2를 출력하고 아닌 경우는 수열을 만드는 것이 불가능하였다는 의미로 NO를 출력하게 된다.

> 문제를 잘 이해하지 못해서 https://yeodo95.tistory.com/11 의 풀이 과정을 참고하였다.