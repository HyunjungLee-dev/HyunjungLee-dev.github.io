---
title:  "[algorithm]BAEKJOON 백준 10809번 알파벳 찾기"
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

# Baekjoon Online Judge No.10809

<https://www.acmicpc.net/problem/10809>

## 문제

- 알파벳 소문자로만 이루어진 단어 S가 주어진다. 각각의 알파벳에 대해서, 단어에 포함되어 있는 경우에는 처음 등장하는 위치를, 포함되어 있지 않은 경우에는 -1을 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 단어 S가 주어진다. 단어의 길이는 100을 넘지 않으며, 알파벳 소문자로만 이루어져 있다.

## 출력

각각의 알파벳에 대해서, a가 처음 등장하는 위치, b가 처음 등장하는 위치, ... z가 처음 등장하는 위치를 공백으로 구분해서 출력한다.

만약, 어떤 알파벳이 단어에 포함되어 있지 않다면 -1을 출력한다. 단어의 첫 번째 글자는 0번째 위치이고, 두 번째 글자는 1번째 위치이다.



## 알고리즘 분류

- 문자열 처리



## 예제 입력 1

```
baekjoon
```

## 예제 출력 1

```
1 0 -1 -1 2 -1 -1 -1 -1 4 3 -1 -1 7 5 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1
```



## 코드

### C++ 11

```c++
#include<iostream>
#include<string>
#include<algorithm>
using namespace std;


int main()
{

	string str;

	cin >> str;

	for (char i = 'a'; i <= 'z'; i++)
	{
		auto it = find(str.begin(), str.end(), i);
		if (it == str.end())
		{
			cout << -1 << ' ';
		}
		else
		{
			cout << (it - str.begin()) << ' ';
		}
	}
	cout << endl;
	return 0;
}
```

find 함수를 이용하여 문제를 해결한다.  C++ 11에서 auto가 추가 되었고 auto는 초기화 시 초기화 하는 값에 따라 자동으로 자료형을 판단하여 사용한다. 사용 방법은 자료형 대신 auto를 사용하면 된다.

### C++

```c++
#include<iostream>
#include<string>
using namespace std;


int main()
{
	string str;
	string alphabet = "abcdefghijklmnopqrstuvwxyz";
	cin >> str;
	for (int i = 0; i < alphabet.length(); i++)
	{
		if (str.find(alphabet[i]) == string::npos)
			cout << -1 << ' ';
		else
		{
			cout << str.find(alphabet[i]) << ' ';
		}
	}
	cout << endl;
	return 0;
}
```

string의 find 함수를 이용한다.  string::find는 찾는 문자열의 첫번째 인덱스를 반환해준다. 찾는 문자열이 없는 경우에는 string::npos를 반환한다.

```c++
#include<iostream>
#include<string>
#include<vector>
using namespace std;


int main()
{
	string str;
	cin >> str;

	vector<int> v(26, -1);
	for (int i = 0; i < str.length(); i++)
	{
		if (v[str.at(i) - 97] == -1)
			v[str.at(i) - 97] = i;
	}
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++)
		cout << *it << ' ';
	return 0;
}
```

vector  컨테이너를 이용한다. 알파벳 갯수만큼 -1로 초기화 해준다. 출력 하면 알파벳 갯수만큼 -1이 출력 될 것이다. 이때 입력 받은 문자의 알파벳이 있으면 있는 위치를 출력하기 위해 string의 at함수를 사용한다. 

at 함수는 문자열에서 특정위치의 문자를 액세스 하는 함수로 at(i)라고 한다면 i에 위치한 문자가 무엇인지 확인하게 된다. 만약 str.at(i)가 'b'였다면 아스키코드로는 98이 되고 97(소문자 a의 아스키코드)를 빼면 v[1]의 위치에 (알파벳 갯수만큼 초기화 해줬으니 b의 위치가 될 것이다) i 라는 위치를 넣게 된다.