---
title:  "[algorithm]BAEKJOON 백준 10799번 쇠막대기"
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

# Baekjoon Online Judge No.10799

[https://www.acmicpc.net/problem/10799](https://www.acmicpc.net/problem/10799)

## 문제

여러 개의 쇠막대기를 레이저로 절단하려고 한다. 효율적인 작업을 위해서 쇠막대기를 아래에서 위로 겹쳐 놓고, 레이저를 위에서 수직으로 발사하여 쇠막대기들을 자른다. 쇠막대기와 레이저의 배치는 다음 조건을 만족한다.

- 쇠막대기는 자신보다 긴 쇠막대기 위에만 놓일 수 있다. - 쇠막대기를 다른 쇠막대기 위에 놓는 경우 완전히 포함되도록 놓되, 끝점은 겹치지 않도록 놓는다.
- 각 쇠막대기를 자르는 레이저는 적어도 하나 존재한다.
- 레이저는 어떤 쇠막대기의 양 끝점과도 겹치지 않는다. 

아래 그림은 위 조건을 만족하는 예를 보여준다. 수평으로 그려진 굵은 실선은 쇠막대기이고, 점은 레이저의 위치, 수직으로 그려진 점선 화살표는 레이저의 발사 방향이다.

<img width="267" alt="1" src="https://user-images.githubusercontent.com/54986748/74079568-7d7d8680-4a7c-11ea-96aa-517e01cc09e7.png">

이러한 레이저와 쇠막대기의 배치는 다음과 같이 괄호를 이용하여 왼쪽부터 순서대로 표현할 수 있다.

1. 레이저는 여는 괄호와 닫는 괄호의 인접한 쌍 ‘( ) ’ 으로 표현된다. 또한, 모든 ‘( ) ’는 반드시 레이저를 표현한다.
2. 쇠막대기의 왼쪽 끝은 여는 괄호 ‘ ( ’ 로, 오른쪽 끝은 닫힌 괄호 ‘) ’ 로 표현된다. 

위 예의 괄호 표현은 그림 위에 주어져 있다.

쇠막대기는 레이저에 의해 몇 개의 조각으로 잘려지는데, 위 예에서 가장 위에 있는 두 개의 쇠막대기는 각각 3개와 2개의 조각으로 잘려지고, 이와 같은 방식으로 주어진 쇠막대기들은 총 17개의 조각으로 잘려진다. 

쇠막대기와 레이저의 배치를 나타내는 괄호 표현이 주어졌을 때, 잘려진 쇠막대기 조각의 총 개수를 구하는 프로그램을 작성하시오.

## 알고리즘 분류

- 스택



## 입력

한 줄에 쇠막대기와 레이저의 배치를 나타내는 괄호 표현이 공백없이 주어진다. 괄호 문자의 개수는 최대 100,000이다. 

## 출력

잘려진 조각의 총 개수를 나타내는 정수를 한 줄에 출력한다.



## 예제 입력 1

```
()(((()())(())()))(())
```

## 예제 출력 1

```
17
```

## 예제 입력 2

```
(((()(()()))(())()))(()())
```

## 예제 출력 2

```
24
```



## 코드

```c++
#include <iostream>
#include <stack>
#include<string>
using namespace std;

int main() {
	
	string str;
	int num = 0;

	cin >> str;

	stack<char>st;

	for (int i = 0; i < str.length(); i++)
	{
		if(str[i] == '(')
			st.push(str[i]);
		else
		{
			st.pop();

			if (str[i-1] == '(')
				num += st.size();
			else
				num++;
		}
	}
	cout << num << endl;
}

```

스택을 이용하여 풀 수 있는 문제이다. 이 문제에서는 ')' 일 때 이것은 쇠막대기의 끝일수도 있고 레이저일 수도 있다는 것이 생각해야 하는 부분인데. 그렇다면 언제 끝이고 레이저인가에 대해 생각해보면 닫힌 괄호가 단독으로 나오면 쇠막대기의 끝이고 여는 괄호와 닫힌 괄호가 인접한 쌍으로 나오면 레이저가 된다.

그렇다면 세 가지 경우의 코드가 필요하다. 

- '(' 일때

```c++
if(str[i] == '(')
			st.push(str[i]);
```

- ')' 이고 인접한 여는 괄호로 쌍이 되는 경우(레이저)  /    ')' 이고 쇠막대기의 끝일 때

```c++
st.pop();

if (str[i-1] == '(')
 	num += st.size();
else
	num++;
```



그렇다면 예제를 살펴보자 예제 1은 쇠막대기 조각은 총 17개가 된다. 왜 이렇게 되는 걸까, 앞의 일부분을 확인해보자. 

<img width="450" alt="1-2" src="https://user-images.githubusercontent.com/54986748/74088201-d417ae80-4ad6-11ea-87a4-af21afdbf78d.png">



**( )** 부터 보면 `'(' push`  ->  `')' pop`

바로 전이 `'('` 이므로 레이저이다. 하지만 pop 되고 스택은 비게 되었으니 스택 사이즈는 0이다.

**( ( ( ( ) ( ) )**

`'(' push` -> `'(' push`-> `'(' push` ->`'(' push` -> `')' pop`

바로 전이 `'('` 이므로 레이저이다.  그림을 보며 생각해보면  레이저로 잘린 부분이 하나의 단면이 된다고 생각해보면 된다. `'(' push`로 (아직은) 끝이 없는 막대기가 하나 생겼고 레이저로 잘리게 되면서 단면이 생겨 막대 조각이 생겼다고 보면 된다. 그러면 이것이 막대 조각 1개가 되는 것이다. 여기에서 `'('` 이 스택에 3개가 들어가 있으니 스택 사이즈는 3 즉 막대 조각이 3개인 것이다.



`'(' push` -> `')' pop `-> `')' pop`

`')'`의 전이 여는 괄호이므로 레이저이다.  앞에서부터 이어져 오던 막대기가 레이저로 인해 한번 잘렸었다. 그 막대기는 아직 끝이 아니니깐 레이저이면 또 잘리게 되어 막대 조각이 생길 것이다.  스택의 사이즈는 3으로 막대 조각이 3개가 더 생기게 되어 지금까지 총 6개의 막대 조각이 생기게 된다.

그 후`')'`이므로 pop이 되고 하지만 전이 여는 괄호가 아니었기 때문에 이것은 막대의 끝을 말하는 것이 된다. pop으로 인해 스택의 사이즈는 2가 되었고 (이해를 위해 하나의 막대가 레이저 작업이 끝나서 작업할 막대가 2개 남아 있다고 생각해보자)  전에 레이저로 잘린 단면부터 막대의 끝을 이으면 하나의 막대 조각이 되므로 막대 조각의 개수를 1개 추가해준다. 그렇게 지금까지 7개의 막대가 된다.



<img width="450" alt="1-1" src="https://user-images.githubusercontent.com/54986748/74087680-0246bf80-4ad2-11ea-95ec-efbc9d1561c6.png">



이 과정을 반복해서 진행하게 되면 위 이미지와 같이 막대 조각이 총 17개 인 것을 확인 할 수 있다.