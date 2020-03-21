---
title:  "[algorithm]BAEKJOON 백준 1158번 요세푸스 문제"
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

# Baekjoon Online Judge No.1158

[https://www.acmicpc.net/problem/1158](https://www.acmicpc.net/problem/1158)

## 문제

요세푸스 문제는 다음과 같다.

1번부터 N번까지 N명의 사람이 원을 이루면서 앉아있고, 양의 정수 K(≤ N)가 주어진다. 이제 순서대로 K번째 사람을 제거한다. 한 사람이 제거되면 남은 사람들로 이루어진 원을 따라 이 과정을 계속해 나간다. 이 과정은 N명의 사람이 모두 제거될 때까지 계속된다. 원에서 사람들이 제거되는 순서를 (N, K)-요세푸스 순열이라고 한다. 예를 들어 (7, 3)-요세푸스 순열은 <3, 6, 2, 7, 5, 1, 4>이다.

N과 K가 주어지면 (N, K)-요세푸스 순열을 구하는 프로그램을 작성하시오.

## 알고리즘 분류

- 큐

## 입력

첫째 줄에 N과 K가 빈 칸을 사이에 두고 순서대로 주어진다. (1 ≤ K ≤ N ≤ 5,000)

## 출력

예제와 같이 요세푸스 순열을 출력한다.



## 예제 입력 

```
7 3
```

## 예제 출력 

```
<3, 6, 2, 7, 5, 1, 4>
```



## 코드

```c++
#include<iostream>
#include<queue>
using namespace std;


int main()
{

	queue<int> q;

	int num1,num2;

	cin >> num1 >> num2;

	for (int i = 1; i <= num1; i++)
	{
		q.push(i);
	}
	cout << "<";
	while (!q.empty())
	{
		if (q.size() == 1)
		{
			cout <<q.front()<< ">";
			q.pop();
			break;
		}
		for (int i = 1; i < num2; i++)
		{
			q.push(q.front());
			q.pop();
		}
		cout << q.front() << ", ";
		q.pop();
	}
	
	return 0;
}
}
```

------

```c++
for (int i = 1; i <= num1; i++)
	{
		q.push(i);
	}
```

처음에 push()를 이용해 num1까지 넣어준다. 예제에서는 7이었으니 1부터 7까지 들어가게 된다.

------

```c++
cout << "<";
	while (!q.empty()) // size()를 이용할 수 있다.
	{
		if (q.size() == 1)
		{
			cout <<q.front()<< ">";
			q.pop();
			break;
		}
		for (int i = 1; i < num2; i++)
		{//int temp로 fornt()의 수를 받아 pop후 temp를 push 해도 된다
			q.push(q.front()); 
			q.pop();
		}
		cout << q.front() << ", ";
		q.pop();
	}
```

여기서 생각해야하는 것은 큐를 회전하는 원형 같은 형태라고 생각해보자.  문제에 의하면 M번째 사람을 제거하게 된다. 이 코드에서는 num2로 받은 수가 될 것이다. 예제에서는 3이었기에 3을 예로 생각해보자. 3을 빼려면 앞의 1,2가 없어야한다. 여기에서는 1,2가 남아 있어야 하기 때문에  pop()을 먼저 해주는 것이 아니라 push를 먼저 해준 후 pop을 한다. 이렇게 반복하게 되면 예제 출력과 같이 출력 된다.