---
title:  "[algorithm]BAEKJOON 백준 11655번 ROT13"
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

# Baekjoon Online Judge No.11655

<https://www.acmicpc.net/problem/11655>

## 문제

ROT13은 카이사르 암호의 일종으로 영어 알파벳을 13글자씩 밀어서 만든다.

예를 들어, "Baekjoon Online Judge"를 ROT13으로 암호화하면 "Onrxwbba Bayvar Whqtr"가 된다. ROT13으로 암호화한 내용을 원래 내용으로 바꾸려면 암호화한 문자열을 다시 ROT13하면 된다. 앞에서 암호화한 문자열 "Onrxwbba Bayvar Whqtr"에 다시 ROT13을 적용하면 "Baekjoon Online Judge"가 된다.

ROT13은 알파벳 대문자와 소문자에만 적용할 수 있다. 알파벳이 아닌 글자는 원래 글자 그대로 남아 있어야 한다. 예를 들어, "One is 1"을 ROT13으로 암호화하면 "Bar vf 1"이 된다.

문자열이 주어졌을 때, "ROT13"으로 암호화한 다음 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 알파벳 대문자, 소문자, 공백, 숫자로만 이루어진 문자열 S가 주어진다. S의 길이는 100을 넘지 않는다.

## 출력

첫째 줄에 S를 ROT13으로 암호화한 내용을 출력한다.

## 예제 입력 1 

```
Baekjoon Online Judge
```

## 예제 출력 1 

```
Onrxwbba Bayvar Whqtr
```

## 예제 입력 2 

```
One is 1
```

## 예제 출력 2 

```
Bar vf 1
```

## 코드

### C++

```c++
#include<iostream>
#include<string>
using namespace std;



int main()
{
	string str, result;
	getline(cin, str);

	for (int i = 0; i < str.length(); i++)
	{
		if (str[i] >= '0' && str[i] <= '9'  || str[i] == ' ')
		{
			result += str[i];
		}
		else if (str[i] >= 'A' && str[i] <= 'M' || str[i] >= 'a' && str[i] <= 'm')
		{
			result += str[i] + 13;
		}
		else
			result += str[i] - 13;
	}
	cout << result;
	return 0;
}
```

아스키코드를 알고 있는가, 공백을 포함한 문장을 입력 받으려면 어떻게 해야하는가 이 두가지가 문제의 포인트인 것 같다. 공백을 포함한 문장을 입력 받으려면 getline()을 사용하여 입력 받으면 된다. 

숫자나 공백의 경우 13글자 밀어서 만들 필요가 없기 때문에 그대로 두면 되고 아스키코드 13개의 값 단위로 처리한다. 만약 아스키 코드 'n'의 경우 +13을 해주면 122('z') 를 넘어가 123이 되기 때문이다. 그렇기 때문에 -13을 해주어야 하며 결과로 a가 나온다.