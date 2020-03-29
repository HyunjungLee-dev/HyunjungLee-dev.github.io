---
title:  "[algorithm]BAEKJOON 백준 10820번 문자열 분석"
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

# Baekjoon Online Judge No.10820

<https://www.acmicpc.net/problem/10820>

## 문제

문자열 N개가 주어진다. 이때, 문자열에 포함되어 있는 소문자, 대문자, 숫자, 공백의 개수를 구하는 프로그램을 작성하시오.

각 문자열은 알파벳 소문자, 대문자, 숫자, 공백으로만 이루어져 있다.

## 입력

첫째 줄부터 N번째 줄까지 문자열이 주어진다. (1 ≤ N ≤ 100) 문자열의 길이는 100을 넘지 않는다.

## 출력

첫째 줄부터 N번째 줄까지 각각의 문자열에 대해서 소문자, 대문자, 숫자, 공백의 개수를 공백으로 구분해 출력한다.

## 예제 입력 1 

```
This is String
SPACE    1    SPACE
 S a M p L e I n P u T     
0L1A2S3T4L5I6N7E8
```

## 예제 출력 1 

```
10 2 0 2
0 10 1 8
5 6 0 16
0 8 9 0
```

## 코드

### C++

```c++
#include<iostream>
#include<string>
#include<algorithm>
using namespace std;


int main()
{

	while(1)
	{
		int lower = 0, upper = 0, space = 0, num = 0;
		string str;
		getline(cin, str);

		if (cin.eof() == true)
		{
			break;
		}

		for (int j = 0; j < str.length(); j++)
		{
			if (str[j] >= '0' && str[j] <= '9')
			{
				num++;
			}
			else if (str[j] >= 'A' && str[j] <= 'Z')
			{
				upper++;
			}
			else if (str[j] >= 'a' && str[j] <= 'z')
			{
				lower++;
			}
			else if (str[j] == ' ')
				space++;
		}
		cout << lower << ' ' << upper << ' ' << num << ' ' << space << endl;
	}
	return 0;
}
```

공백도 입력을 받기 위해서 cin이 아닌 getline 함수를 이용하고 언제 입력을 끝내는가에 대한 코드가 필요하기 때문에 cin.eof()를 이용하였다. cin.eof()는 파일이 종료될 때까지 입력받으며 윈도우 기준 ctrl+z를 하면 종료된다.

