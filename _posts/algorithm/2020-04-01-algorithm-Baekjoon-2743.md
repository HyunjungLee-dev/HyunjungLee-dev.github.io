---
title:  "[algorithm]BAEKJOON 백준 2743번 단어 길이 재기"
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

# Baekjoon Online Judge No.2743

<https://www.acmicpc.net/problem/2743>

## 문제

알파벳으로만 이루어진 단어를 입력받아, 그 길이를 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 영어 소문자와 대문자로만 이루어진 단어가 주어진다. 단어의 길이는 최대 100이다.

## 출력

첫째 줄에 입력으로 주어진 단어의 길이를 출력한다.

## 예제 입력 1 

```
pulljima
```

## 예제 출력 1 

```
8
```



## 코드

### C++

```c++
#include<iostream>
#include<string>
using namespace std;



int main()
{
	string str;
	cin >> str;

	cout << str.length();

}
```

string 클래스 멤버함수를 이용해서 해결할 수 있다. size와 length를 사용 가능하다. size의 경우는 실제 사용되고 있는 크기이고 length의 경우는 문자열의 길이를 반환한다. 위의 코드 작성한 것과 같이 string 헤더를 추가해주고 .length()와 같이 적어준다.