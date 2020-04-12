---
title:  "[algorithm]BAEKJOON 백준 10718번 We love kriii"
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

# Baekjoon Online Judge No.10718

<https://www.acmicpc.net/problem/10718>

## 문제

ACM-ICPC 인터넷 예선, Regional, 그리고 World Finals까지 이미 2회씩 진출해버린 kriii는 미련을 버리지 못하고 왠지 모르게 올 해에도 파주 World Finals 준비 캠프에 참여했다.

대회를 뜰 줄 모르는 지박령 kriii를 위해서 격려의 문구를 출력해주자.

## 입력

본 문제는 입력이 없다.

## 출력

두 줄에 걸쳐 "강한친구 대한육군"을 한 줄에 한 번씩 출력한다.

## 예제 입력 1

```

```

## 예제 출력 1 

```
강한친구 대한육군
강한친구 대한육군
```

## 출처

[Contest ](https://www.acmicpc.net/category/45)> [Coder's High ](https://www.acmicpc.net/category/215)> [Coder's High 2015 Side Contest](https://www.acmicpc.net/category/detail/1335) P1번

- 문제를 만든 사람: [tae](https://www.acmicpc.net/user/tae)

## 알고리즘 분류

- [출력](https://www.acmicpc.net/problem/tag/출력)

## 코드

### C++

```c++
#include<iostream>
#include<string>
using namespace std;



int main()
{

	string str = "강한친구 대한육군";
	for (int i = 0; i < 2; i++)
	{
		cout << str << endl;
	}

	return 0;
}
```

기본 출력 문제이다. string을 사용하기 위해 `<string>` 헤더 파일이 필요하며 입력은 없다고 나와있었기에 str에  문자열 값을 넣어주었다. 여기에서는 for 문을 이용하였지만 한 줄에 한 번씩 총 두번 출력하는 것이기에 `cout << str << endl;`를 두 번 작성해 주어도 무방하다. 메모리와 시간에는 차이가 없다.