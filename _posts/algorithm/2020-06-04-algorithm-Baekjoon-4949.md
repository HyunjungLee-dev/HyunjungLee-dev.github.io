---
title:  "[algorithm]BAEKJOON 백준 4949번 균형잡힌 세상"
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

# Baekjoon Online Judge No.4949

<https://www.acmicpc.net/problem/4949>

## 문제

세계는 균형이 잘 잡혀있어야 한다. 양과 음, 빛과 어둠 그리고 왼쪽 괄호와 오른쪽 괄호처럼 말이다.

정민이의 임무는 어떤 문자열이 주어졌을 때, 괄호들의 균형이 잘 맞춰져 있는지 판단하는 프로그램을 짜는 것이다.

문자열에 포함되는 괄호는 소괄호("()") 와 대괄호("[]")로 2종류이고, 문자열이 균형을 이루는 조건은 아래와 같다.

- 모든 왼쪽 소괄호("(")는 오른쪽 소괄호(")")와만 짝을 이뤄야 한다.
- 모든 왼쪽 대괄호("[")는 오른쪽 대괄호("]")와만 짝을 이뤄야 한다.
- 모든 오른쪽 괄호들은 자신과 짝을 이룰 수 있는 왼쪽 괄호가 존재한다.
- 모든 괄호들의 짝은 1:1 매칭만 가능하다. 즉, 괄호 하나가 둘 이상의 괄호와 짝지어지지 않는다.
- 짝을 이루는 두 괄호가 있을 때, 그 사이에 있는 문자열도 균형이 잡혀야 한다.

정민이를 도와 문자열이 주어졌을 때 균형잡힌 문자열인지 아닌지를 판단해보자.

## 입력

하나 또는 여러줄에 걸쳐서 문자열이 주어진다. 각 문자열은 영문 알파벳, 공백, 소괄호("( )") 대괄호("[ ]")등으로 이루어져 있으며, 길이는 100글자보다 작거나 같다.

입력의 종료조건으로 맨 마지막에 점 하나(".")가 들어온다.

## 출력

각 줄마다 해당 문자열이 균형을 이루고 있으면 "yes"를, 아니면 "no"를 출력한다.

## 예제 입력 1 복사

```
So when I die (the [first] I will see in (heaven) is a score list).
[ first in ] ( first out ).
Half Moon tonight (At least it is better than no Moon at all].
A rope may form )( a trail in a maze.
Help( I[m being held prisoner in a fortune cookie factory)].
([ (([( [ ] ) ( ) (( ))] )) ]).
 .
.
```

## 예제 출력 1 복사

```
yes
yes
no
no
no
yes
yes
```

## 힌트

7번째의 " ."와 같이 괄호가 하나도 없는 경우도 균형잡힌 문자열로 간주할 수 있다.

## 코드	

### C++

```c++
#include<iostream>
#include<string>
#include<stack>
using namespace std;



int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	while (true)
	{

		string str;
		stack<char> s;
		bool check = true;

		getline(cin, str);
		if (str == ".")
			break;

		for (int i = 0; i < str.length(); i++)
		{
			if (str[i] == '(' || str[i] == '[')
				s.push(str[i]);
			else if (str[i] == ')')
			{
				if (!s.empty() && s.top() == '(')
				{
					s.pop();
				}
				else
				{
					check = false;
					break;
				}
			}
			else if (str[i] == ']')
			{
				if (!s.empty() && s.top() == '[')
				{
					s.pop();
				}
				else
				{
					check = false;
					break;
				}
			}
		}
		if (check && s.empty())
			cout << "yes" << '\n';
		else
			cout << "no"<<'\n';

	}

	return 0;
}
```

stack을 이용하여 풀 수 있는 문제이다. stack은 LIFO로 마지막에 들어온 값이 가장 먼저 나가는 자료구조임을 이용하여 문제를 해결할 수 있다.

9012번 괄호 문제와 비슷한 문제이며 4949번에서는 '( )'만이 아닌 '[ ]' 도 추가로 확인해야 한다는 점이 달라진 문제이다. 괄호가 짝지어 있어 균형 잡힌 문자열이면 yes 아니면 no를 출력하는 문제이기에 먼저 균형 잡힌 문자열인지 확인해야 한다. 그렇게 하기 위해서 입력받은 문자열을 검사하여 '(' 일 때와 '[' 일 때는 push()를 통해 stack에 원소를 추가해 준다. 그리고 ')'일 때와 ']' 일 때는 top()을 이용해 마지막 원소와 짝 지어지는지를 확인한다. 짝 지어지면 스택에서 pop()을 이용해 마지막 원소를 빼준다. 그렇게 되면 괄호가 짝 지어져서 pop이 되면 stack이 비게 됨으로 그것을 확인하면 된다.

bool 자료형을 따로 만들어서 체크를 하게 되는 이유는 stack에는 '(' 와 '[' 만 들어가기