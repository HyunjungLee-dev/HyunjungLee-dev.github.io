---
title:  "[algorithm]BAEKJOON 백준 18258번 큐2"
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

# Baekjoon Online Judge No.18258

<https://www.acmicpc.net/problem/18258>

## 문제

정수를 저장하는 큐를 구현한 다음, 입력으로 주어지는 명령을 처리하는 프로그램을 작성하시오.

명령은 총 여섯 가지이다.

- push X: 정수 X를 큐에 넣는 연산이다.
- pop: 큐에서 가장 앞에 있는 정수를 빼고, 그 수를 출력한다. 만약 큐에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- size: 큐에 들어있는 정수의 개수를 출력한다.
- empty: 큐가 비어있으면 1, 아니면 0을 출력한다.
- front: 큐의 가장 앞에 있는 정수를 출력한다. 만약 큐에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- back: 큐의 가장 뒤에 있는 정수를 출력한다. 만약 큐에 들어있는 정수가 없는 경우에는 -1을 출력한다.

## 입력

첫째 줄에 주어지는 명령의 수 N (1 ≤ N ≤ 2,000,000)이 주어진다. 둘째 줄부터 N개의 줄에는 명령이 하나씩 주어진다. 주어지는 정수는 1보다 크거나 같고, 100,000보다 작거나 같다. 문제에 나와있지 않은 명령이 주어지는 경우는 없다.

## 출력

출력해야하는 명령이 주어질 때마다, 한 줄에 하나씩 출력한다.

## 예제 입력 1 

```
15
push 1
push 2
front
back
size
empty
pop
pop
pop
size
empty
pop
push 3
empty
front
```

## 예제 출력 1 

```
1
2
2
0
1
2
-1
0
1
-1
0
3
```

## 출처

- 문제를 만든 사람: [jh05013](https://www.acmicpc.net/user/jh05013)

## 시간 제한 안내

아래 적혀있지 않은 시간 제한은 [언어 도움말](https://www.acmicpc.net/help/language)에 적혀있는 기준을 따른다.

- Python 3: 3초
- PyPy3: 3초
- Python 2: 3초
- PyPy2: 3초

## 코드	

### C++

```c++
#include<iostream>
#include<string>
#include<queue>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	queue<int> q;

	int n;
	cin >> n;

	for (int i = 0; i < n; i++)
	{
		string str;
		cin >> str;
		
		if (str == "push")
		{
			int num;
			cin >> num;
			q.push(num);
		}
		else if (str == "pop")
		{
			if (q.empty())
			{
				cout << "-1" << '\n';
			}
			else
			{
				cout << q.front() << '\n';
				q.pop();
			}
		}
		else if (str == "size")
		{
			cout << q.size() << '\n';
		}
		else if (str == "empty")
		{
			cout << q.empty() << '\n';
		}
		else if (str == "front")
		{
			if (q.empty())
				cout << "-1" << '\n';
			else
				cout << q.front() << '\n';
		}
		else if (str == "back")
		{
			if (q.empty())
				cout << "-1" << '\n';
			else
				cout << q.back() << '\n';
		}
	}

	return 	0;
}
```

자료구조 중 큐 문제이다. 큐는 먼저 넣은 데이터가 먼저 나오는 FIFO(First In First Out)의 구조이다. C++로 문제를 풀기에 STL이 제공하는 큐를 통해 간단하게 풀 수 있다.`#include<queue>` 헤더 파일을 추가해 주고 `queue<자료형>이름` 과 같은 형태로 선언하여 사용할 수 있다. 이 문제에서는 큐의 기본 함수가 어떤 것이 있는지 어떤 것을 반환하는지에 대해 생각해볼 수 있는 문제이다.

| 함수                             | 역할                                          |
| -------------------------------- | --------------------------------------------- |
| void push(const value_type& val) | 큐에 element를 추가한다.                      |
| void pop()                       | 큐에 있는 원소를 삭제한다.                    |
| value_type& front()              | 큐 제일 앞에 있는 원소를 반환한다.            |
| value_type& back()               | 큐 제일 뒤에 있는 원소를 반환한다.            |
| bool empty() const               | 큐가 비어있으면 true 아니면 false를 반환한다. |
| size_type size() const           | 큐의 사이즈를 반환한다.                       |

