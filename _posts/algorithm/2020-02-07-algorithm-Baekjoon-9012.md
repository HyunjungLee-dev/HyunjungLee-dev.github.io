---
title:  "[algorithm]BAEKJOON 백준 9012번 괄호"
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

# Baekjoon Online Judge No.9012

[https://www.acmicpc.net/problem/9012](https://www.acmicpc.net/problem/9012)

## 문제

괄호 문자열(Parenthesis String, PS)은 두 개의 괄호 기호인 ‘(’ 와 ‘)’ 만으로 구성되어 있는 문자열이다. 그 중에서 괄호의 모양이 바르게 구성된 문자열을 올바른 괄호 문자열(Valid PS, VPS)이라고 부른다. 한 쌍의 괄호 기호로 된 “( )” 문자열은 기본 VPS 이라고 부른다. 만일 x 가 VPS 라면 이것을 하나의 괄호에 넣은 새로운 문자열 “(x)”도 VPS 가 된다. 그리고 두 VPS x 와 y를 접합(concatenation)시킨 새로운 문자열 xy도 VPS 가 된다. 예를 들어 “(())()”와 “((()))” 는 VPS 이지만 “(()(”, “(())()))” , 그리고 “(()” 는 모두 VPS 가 아닌 문자열이다. 

여러분은 입력으로 주어진 괄호 문자열이 VPS 인지 아닌지를 판단해서 그 결과를 YES 와 NO 로 나타내어야 한다. 

## 알고리즘 분류

- 스택



## 입력

입력 데이터는 표준 입력을 사용한다. 입력은 T개의 테스트 데이터로 주어진다. 입력의 첫 번째 줄에는 입력 데이터의 수를 나타내는 정수 T가 주어진다. 각 테스트 데이터의 첫째 줄에는 괄호 문자열이 한 줄에 주어진다. 하나의 괄호 문자열의 길이는 2 이상 50 이하이다. 



## 출력

출력은 표준 출력을 사용한다. 만일 입력 괄호 문자열이 올바른 괄호 문자열(VPS)이면 “YES”, 아니면 “NO”를 한 줄에 하나씩 차례대로 출력해야 한다. 



## 예제 입력 1

```
6
(())())
(((()())()
(()())((()))
((()()(()))(((())))()
()()()()(()()())()
(()((())()(
```

## 예제 출력 1

```
NO
NO
YES
NO
YES
NO
```

## 코드

```c++
#include<iostream>
#include<stack>
#include<string>
using namespace std;

bool VPSCheck(string str)
{
	stack<char>st;
	bool check = true;
	for (int i = 0; i < str.length(); i++)
	{
		if (str[i] == '(')
			st.push(str[i]);
		else if (str[i] == ')')
		{
			if (st.empty())
				check = false;
			else
				st.pop();
		}
	}
	if (st.empty() && check)
		return true;
	else
		return false;
}

int main(void)
{
	int T;
	cin >> T;

	for (int i = 0; i < T; i++)
	{
		string str;
		cin >> str;

		if (VPSCheck(str))
			cout << "YES" << endl;
		else
			cout << "NO" << endl;
	}
	return 0;
}
```

스택을 이용해서 풀 수 있는 문제이다. 먼저 VPSCheck 함수를 살펴보면 '(' 이면 push')' 일 때는 살펴봐야 하는 게 있는데 스택이 비었는가 아닌가를 봐야 한다. 스택이 비어있다면  괄호는 짝이 다 맞아 있다는 것이고 ')'로 인해  짝이 맞지 않게 되었다는 것을 확인할 수 있다. 그렇기에 false를 해주고 비어있지 않는다면 안에 '(' 가 있다는 것이고 pop을 해주면 된다.

- push '(' pop ')' -> 스택은 빈 상태가 된다(올바른 괄호라는 것)

for 문이 끝나면 비어있고 앞서 check가 false가 되지 않았다면 올바른 괄호(짝이 맞는)이기 때문에 true를 반환하여 main에서 "YES"를 출력하게 된다.

자료구조의 경우 글만으로 이해가 어려울 때 예제를 그림으로  그려가며 이해해 보면 조금 더 이해가 잘되어서 그림을 그려보는 것도 좋은 것 같다.