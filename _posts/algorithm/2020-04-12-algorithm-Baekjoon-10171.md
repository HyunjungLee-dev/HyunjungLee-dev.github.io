---
title:  "[algorithm]BAEKJOON 백준 10171번 고양이"
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

# Baekjoon Online Judge No.10171

<https://www.acmicpc.net/problem/10171>

## 문제

아래 예제와 같이 고양이를 출력하시오.

## 입력

없음.

## 출력

고양이를 출력한다.

## 예제 입력 1 

```

```

## 예제 출력 1 

```
\    /\
 )  ( ')
(  /  )
 \(__)|
```

## 출처

[High School ](https://www.acmicpc.net/category/97)> [PLU High School Programming Contest ](https://www.acmicpc.net/category/96)> [PLU 2014 - Novice](https://www.acmicpc.net/category/detail/1275) 2번

## 알고리즘 분류

- [출력](https://www.acmicpc.net/problem/tag/출력)

## 코드

### C++

```c++
#include<iostream>
using namespace std;



int main()
{

	cout << "\\    /\\ " << endl;
	cout << " )  ( ')" << endl;
	cout << "(  /  )" << endl;
	cout << " \\(__)|" << endl;


	return 0;
}
```

기본 출력 문제이다. 이 문제에서 신경 써야 하는 부분은 `'\'`이다. 역슬래시(백슬래시)의 경우는 단독으로 다른 문자와 함께 사용되는 경우기 있기 때문에(ex `\t`, `\n`) 역슬래시를 출력하기 위해서는 `'\\'`이와 같이 두 번 입력해 주어야 한다. 참고로 쌍따옴표를 문자열에서 출력하고 싶을 때는 `\"`와 같이 적어주면 된다.