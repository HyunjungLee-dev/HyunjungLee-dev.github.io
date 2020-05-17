---
title:  "[algorithm]BAEKJOON 백준 11654번 아스키 코드"
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

# Baekjoon Online Judge No.11654

<https://www.acmicpc.net/problem/11654>

## 문제

알파벳 소문자, 대문자, 숫자 0-9중 하나가 주어졌을 때, 주어진 글자의 아스키 코드값을 출력하는 프로그램을 작성하시오.

## 입력

알파벳 소문자, 대문자, 숫자 0-9 중 하나가 첫째 줄에 주어진다.

## 출력

입력으로 주어진 글자의 아스키 코드 값을 출력한다.

## 예제 입력 1 

```
A
```

## 예제 출력 1 

```
65
```

## 예제 입력 2 

```
C
```

## 예제 출력 2 

```
67
```

## 예제 입력 3 

```
0
```

## 예제 출력 3 

```
48
```

## 예제 입력 4 

```
9
```

## 예제 출력 4 

```
57
```

## 예제 입력 5 

```
a
```

## 예제 출력 5 

```
97
```

## 예제 입력 6 

```
z
```

## 예제 출력 6 

```
122
```

## 알고리즘 분류

- [문자열 처리](https://www.acmicpc.net/problem/tag/문자열 처리)

## 코드	

### C++

```c++
#include <iostream>
using namespace std;

int main()
{
	char ch;
	cin >> ch;
	cout << (int)ch;
	return 0;
}
```

> 초창기에는 다양한 방법으로 문자를 표현했는데, 호환 등 여러 문제가 발생했다. 이런 문제를 해결하기 위해 ANSI [1)](https://terms.naver.com/entry.nhn?docId=2270339&cid=51173&categoryId=51173#footNote1)에서 ASCII(American Standard Code for Information Interchange)라는 표준 코드 체계를 제시했고, 현재 이 코드가 일반적으로 사용되고 있다.
>
> ASCII는 각 문자를 7비트로 표현하므로 총 128(= 27)개의 문자를 표현할 수 있다.
>
> **[네이버 지식백과]** [ASCII](https://terms.naver.com/entry.nhn?docId=2270339) (컴퓨터 개론, 2013. 3. 10., 김종훈, 김종진)

char형으로 입력을 받고 int형으로 변환하여 출력해 주면 아스키코드값이 출력 된다. 대문자 A가 아스키코드값으로 65이고 소문자 a가 97이다. 대문자와 소문자의 값의 차이는 32라는 것을 알아두는 것이 좋다. 