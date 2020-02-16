---
title:  "[algorithm]BAEKJOON 백준 10845번 큐"
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

# Baekjoon Online Judge No.10845

[https://www.acmicpc.net/problem/10845](https://www.acmicpc.net/problem/10845)

## 문제

정수를 저장하는 큐를 구현한 다음, 입력으로 주어지는 명령을 처리하는 프로그램을 작성하시오.

명령은 총 여섯 가지이다.

- push X: 정수 X를 큐에 넣는 연산이다.
- pop: 큐에서 가장 앞에 있는 정수를 빼고, 그 수를 출력한다. 만약 큐에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- size: 큐에 들어있는 정수의 개수를 출력한다.
- empty: 큐가 비어있으면 1, 아니면 0을 출력한다.
- front: 큐의 가장 앞에 있는 정수를 출력한다. 만약 큐에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- back: 큐의 가장 뒤에 있는 정수를 출력한다. 만약 큐에 들어있는 정수가 없는 경우에는 -1을 출력한다.

## 알고리즘 분류

- 큐

## 입력

첫째 줄에 주어지는 명령의 수 N (1 ≤ N ≤ 10,000)이 주어진다. 둘째 줄부터 N개의 줄에는 명령이 하나씩 주어진다. 주어지는 정수는 1보다 크거나 같고, 100,000보다 작거나 같다. 문제에 나와있지 않은 명령이 주어지는 경우는 없다.

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



## 코드

```c++
#include<iostream>
#include<string>
#include<queue>
using namespace std;


int main()
{

	queue<int> q; 

	int N;
	cin >> N;

	for (int i = 0; i < N; i++)
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
				cout << "-1" << endl;
			else
			{
				cout << q.front() << endl;
				q.pop();
			}
		}
		else if (str == "front")
		{
			if (q.empty())
				cout << "-1" << endl;
			else
				cout << q.front() << endl;
		}
		else if (str == "back")
		{
			if (q.empty())
				cout << "-1" << endl;
			else
				cout << q.back() << endl;
		}
		else if (str == "size")
		{
			cout << q.size() << endl;
		}
		else if (str == "empty")
		{
			cout << q.empty() << endl;
		}
	}
	return 0;
}
```

큐는 먼저 들어온 데이터가 먼저 나가는 즉 선입선출의 자료구조이다. C++ STL을 사용하였다. STL을 사용하지 않고 직접 구현을 할 수 있는데 나중에 큐에 대한 포스팅에 같이 올리고자 한다. 



