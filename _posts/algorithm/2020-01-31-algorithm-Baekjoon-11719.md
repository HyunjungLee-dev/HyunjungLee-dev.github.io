---
title:  "[algorithm]BAEKJOON 백준 11719번 그대로 출력하기2"
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

# Baekjoon Online Judge No.11719

[https://www.acmicpc.net/problem/11719](https://www.acmicpc.net/problem/11719)

## 문제

입력 받은 대로 출력하는 프로그램을 작성하시오.

## 알고리즘 분류

- 출력



## 입력

입력이 주어진다. 입력은 최대 100줄로 이루어져 있고, 알파벳 소문자, 대문자, 공백, 숫자로만 이루어져 있다. 각 줄은 100글자를 넘지 않으며, 빈 줄이 주어질 수도 있고, 각 줄의 앞 뒤에 공백이 있을 수도 있다.

## 출력

입력받은 그대로 출력한다.



## 예제 입력 

```
    Hello

Baekjoon     
   Online Judge    
```



## 예제 출력

```
    Hello

Baekjoon     
   Online Judge    
```



## 코드 

```c++
#include<iostream>
#include<string>
using namespace std;

int main()
{
	string str;

	while (1)
	{
		getline(cin, str);
		if (cin.eof() == true) {
			break;
		}
		cout << str << endl;
	}
	return 0;
}
```

No. 11718과 다른 점은 11718번은 공백을 입력받을 경우 루프를 탈출하는 것이었고 이번 문제는 빈 줄과 공백이 가능하기 때문에  EOF(End Of Flie)에 대한 이해가 필요한 문제이다.