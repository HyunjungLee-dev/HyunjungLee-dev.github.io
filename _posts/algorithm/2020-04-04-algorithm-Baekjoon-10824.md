---
title:  "[algorithm]BAEKJOON 백준 10842번 네 수"
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

# Baekjoon Online Judge No.10842

<https://www.acmicpc.net/problem/10824>

## 문제

네 자연수 A, B, C, D가 주어진다. 이때, A와 B를 붙인 수와 C와 D를 붙인 수의 합을 구하는 프로그램을 작성하시오.

두 수 A와 B를 합치는 것은 A의 뒤에 B를 붙이는 것을 의미한다. 즉, 20과 30을 붙이면 2030이 된다.

## 입력

첫째 줄에 네 자연수 A, B, C, D가 주어진다. (1 ≤ A, B, C, D ≤ 1,000,000)

## 출력

A와 B를 붙인 수와 C와 D를 붙인 수의 합을 출력한다.

## 예제 입력 1 

```
10 20 30 40
```

## 예제 출력 1 

```
4060
```



## 코드

### C++

```c++
#include<iostream>
#include<string>
using namespace std;



int main()
{
	string str, str2;
	int  a, b, c, d;
	unsigned long long result;

	cin >> a >> b>>c>>d;

	str = to_string(a) + to_string(b);
	str2 = to_string(c) + to_string(d);
	
	result = stoull(str) + stoull(str2);

	cout << result;
	return 0;
}
```

1. 먼저 네 자연수 a,b,c,d를 cin으로 입력 받는다.

2. 두 수 a와 b , c와 b를 합치기 위해 + 연산자를 이용하여 각각의 문자열을 더해준다.

   이때 a,b,c,d는 int형이기 때문에 string으로 변환이 필요하다. string 헤더 파일에 있는 to_string 함수를 사용하여 int형 값을 string으로 반환해준다.

3. 각각의 붙인 수의 합을 구한다.

   결과값의 데이터 타입을 unsigned  long long으로 해주었는데 그 이유는 문제에서 네 자연수의 값은 1부터 1,000,000이라고 나와있다. 이때 a도 b도 1,000,000일 경우 합치게 되면 10000001000000이 되는데 int 형식의 값의 범위를 넘어가게 된다. 그렇기 때문에 unsigned long long을 사용한 것이다.

   문자열끼리 더하면 문자열을 붙이는 결과가 나오게 되므로 정수로 바꿔야한다. string 헤더 파일에 있는 stoull 함수는 string에서 unsigned long long으로 바꿔준다.(문자열을 정수로 바꿔주는 함수는 데이터 타입별로 다르다. 예를들어 string에서 int는 stoi)

   | 형식 이름          | 바이트 | 기타 이름                                 | 값의 범위                       |
   | ------------------ | ------ | ----------------------------------------- | ------------------------------- |
   | int                | 4      | signed                                    | -2,147,483,648 to 2,147,483,647 |
   | unsigned long long | 8      | none (but equivalent to unsigned __int64) | 0 to 18,446,744,073,709,551,615 |

    데이터 타입 출처: https://offbyone.tistory.com/115 [쉬고 싶은 개발자]

4. 결과를 출력한다.

