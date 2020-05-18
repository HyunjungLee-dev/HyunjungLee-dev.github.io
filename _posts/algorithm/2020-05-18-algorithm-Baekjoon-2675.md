---
title:  "[algorithm]BAEKJOON 백준 2675번 문자열 반복"
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

# Baekjoon Online Judge No.2675

<https://www.acmicpc.net/problem/2675>

## 문제

문자열 S를 입력받은 후에, 각 문자를 R번 반복해 새 문자열 P를 만든 후 출력하는 프로그램을 작성하시오. 즉, 첫 번째 문자를 R번 반복하고, 두 번째 문자를 R번 반복하는 식으로 P를 만들면 된다. S에는 QR Code "alphanumeric" 문자만 들어있다.

QR Code "alphanumeric" 문자는 `0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ\$%*+-./:` 이다.

## 입력

첫째 줄에 테스트 케이스의 개수 T(1 ≤ T ≤ 1,000)가 주어진다. 각 테스트 케이스는 반복 횟수 R(1 ≤ R ≤ 8), 문자열 S가 공백으로 구분되어 주어진다. S의 길이는 적어도 1이며, 20글자를 넘지 않는다. 

## 출력

각 테스트 케이스에 대해 P를 출력한다.

## 예제 입력 1 

```
2
3 ABC
5 /HTP
```

## 예제 출력 1 

```
AAABBBCCC
/////HHHHHTTTTTPPPPP
```

## 출처

[![img](https://licensebuttons.net/l/by-nc-sa/3.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/3.0/)

[ICPC ](https://www.acmicpc.net/category/1)> [Regionals ](https://www.acmicpc.net/category/7)> [North America ](https://www.acmicpc.net/category/8)> [Greater New York Region ](https://www.acmicpc.net/category/9)> [2011 Greater New York Programming Contest](https://www.acmicpc.net/category/detail/5) A번

- 문제를 번역한 사람: [baekjoon](https://www.acmicpc.net/user/baekjoon)
- 문제의 오타를 찾은 사람: [jh05013](https://www.acmicpc.net/user/jh05013)
- 잘못된 데이터를 찾은 사람: [pichulia](https://www.acmicpc.net/user/pichulia)

## 링크

- [ACM-ICPC Live Archive](https://icpcarchive.ecs.baylor.edu/index.php?option=com_onlinejudge&Itemid=8&page=show_problem&problem=3811)
- [HDU Online Judge](http://acm.hdu.edu.cn/showproblem.php?pid=4236)

## 코드	

### C++

```c++
#include <iostream>
#include<string>
using namespace std;

int main()
{
	int t, r;
	string str;
	cin >> t;
	for (int i = 0; i < t; i++)
	{
		cin >> r;
		cin >> str;
		for (int j = 0; j < str.size(); j++)
		{
			for (int k = 0; k < r; k++)
			{
				cout << str[j];
			}
		}
		cout << '\n';
	}
	
	return 0;
}
```

문자열을 다루는 문제이다. 테스트 케이스 t를 입력받고 for 문을 통해 t 번 입력 받을 수 있도록 한다. 이때 반복 횟수인 r과 문장을 입력받는다. str의 사이즈만큼 반복하여 한 글자씩 r 번 반복한다. 한 문장의 반복 출력이 끝났으면 '\n'으로 줄바꿈을 해주고 다시 반복 횟수와 문장을 입력받게 된다.
