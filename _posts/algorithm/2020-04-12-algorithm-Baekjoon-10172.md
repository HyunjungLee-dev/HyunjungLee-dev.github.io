---
title:  "[algorithm]BAEKJOON 백준 10172번 개"
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

# Baekjoon Online Judge No.10172

<https://www.acmicpc.net/problem/10172>

## 문제

아래 예제와 같이 개를 출력하시오.

## 입력

없음.

## 출력

개를 출력한다.

## 예제 입력 1 

```

```

## 예제 출력 1

```
|\_/|
|q p|   /}
( 0 )"""\
|"^"`    |
||_/=\\__|
```

## 출처

[High School ](https://www.acmicpc.net/category/97)> [PLU High School Programming Contest ](https://www.acmicpc.net/category/96)> [PLU 2014 - Novice](https://www.acmicpc.net/category/detail/1275) 3번

## 알고리즘 분류

- [출력](https://www.acmicpc.net/problem/tag/출력)

## 코드

### C++

```c++
#include<iostream>
using namespace std;



int main()
{

	cout << "|\\_/|" << endl;
	cout << "|q p|   /}" << endl;
	cout << "( 0 )\"\"\"\\" << endl;
	cout << "|\"^\"`    |" << endl;
	cout << "||_/=\\\\__|" << endl;

	return 0;
}
```

앞서 10171 문제와 같은 것이 요구 되는 출력 문제이다. 백슬래시와 큰따옴표의 출력을 위해 어떻게 해야하는지를 생각해야한다. 큰따옴표를 문자열에서 출력하고 싶을 때는 `\"`와 같이 적어주어야하며 역슬래시를 출력하기 위해서는 `'\\'`이와 같이 두 번 입력해 주어야 한다