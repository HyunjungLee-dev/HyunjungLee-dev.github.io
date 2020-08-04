---
title:  "[algorithm]BAEKJOON 백준 10987번 모음의 개수"
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

# Baekjoon Online Judge No.10987

<https://www.acmicpc.net/problem/10987>

## 문제

알파벳 소문자로만 이루어진 단어가 주어진다. 이때, 모음(a, e, i, o, u)의 개수를 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 단어가 주어진다. 단어의 길이는 1보다 크거나 같고, 100보다 작거나 같으며, 알파벳 소문자로만 이루어져 있다.

## 출력

첫째 줄에 모음의 개수를 출력한다.

## 예제 입력 1 복사

```
baekjoon
```

## 예제 출력 1 복사

```
4
```

## 출처

- 문제를 만든 사람: [baekjoon](https://www.acmicpc.net/user/baekjoon)

## 알고리즘 분류

- [문자열 처리](https://www.acmicpc.net/problem/tag/문자열 처리)

## 코드	

### C++

```c++
#include<iostream>
#include<string>
using namespace std;

int main()
{
	string str;
	int num = 0;
	cin >> str;
	
	for (int i = 0; i < str.length(); i++)
	{
		if (str[i] == 'a' || str[i] == 'e' || str[i] == 'o' || str[i] == 'u' || str[i] == 'i')
		{
			num++;
		}
	}
	cout << num;
}
```

문자열 처리 문제로 모음의 개수를 구하는 문제이다. string 변수를 선언하고 모음의 개수를 위한 int형 변수도 선언해준다. string 변수에 단어를 입력받고 length() 함수를 이용해 문자의 길이 구해 길이만큼 반복되도록 하고  if문을 통해 글자가 모음인지 논리 연산자 중 or (논리합)으로 조건문을 작성하고 모음일 경우 개수를 1씩 더해주고 반복문이 끝나면 최종적으로 cout으로 출력해준다. 
