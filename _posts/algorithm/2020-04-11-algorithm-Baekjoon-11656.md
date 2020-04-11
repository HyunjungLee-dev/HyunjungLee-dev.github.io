---
title:  "[algorithm]BAEKJOON 백준 11656번 접미사 배열"
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

# Baekjoon Online Judge No.11656

<https://www.acmicpc.net/problem/11656>

## 문제

접미사 배열은 문자열 S의 모든 접미사를 사전순으로 정렬해 놓은 배열이다.

baekjoon의 접미사는 baekjoon, aekjoon, ekjoon, kjoon, joon, oon, on, n 으로 총 8가지가 있고, 이를 사전순으로 정렬하면, aekjoon, baekjoon, ekjoon, joon, kjoon, n, on, oon이 된다.

문자열 S가 주어졌을 때, 모든 접미사를 사전순으로 정렬한 다음 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 문자열 S가 주어진다. S는 알파벳 소문자로만 이루어져 있고, 길이는 1,000보다 작거나 같다.

## 출력

첫째 줄부터 S의 접미사를 사전순으로 한 줄에 하나씩 출력한다.

## 예제 입력 1 복사

```
baekjoon
```

## 예제 출력 1 복사

```
aekjoon
baekjoon
ekjoon
joon
kjoon
n
on
oon
```

## 알고리즘 분류

- [문자열 처리](https://www.acmicpc.net/problem/tag/문자열 처리)

## 코드

### C++

```c++
#include<iostream>
#include<string>
#include<vector>
#include<algorithm>
using namespace std;



int main()
{
	string str;
	cin >> str;

	vector<string> v;

	for (int i = 0; i < str.length(); i++)
		v.push_back(str.substr(i, str.length()));

	sort(v.begin(), v.end());
	for (int i = 0; i < v.size(); i++)
		cout << v[i] << endl;
	return 0;
}
```

이 문제에서 생각해야할 것은 첫 번째로 어떻게 접미사를 구하는가와 두 번째로는 사전순으로 어떻게 나열할 것인가이다. 

**<첫 번째 >**

1. substr 함수를 사용한다.

substr의 경우 string 헤더 파일에 있다. 원형은 `basic_string substr(size_type pos = 0, size_type count = npos) const;`로 문자열의 일부를 리턴한다. 

첫 번째 인자는 첫번째 문자의 위치를 넣어주면 되고 두번째 인자는 부분 문자열의 길이이다. 코드의 내용으로 본다면 i번째부터 str의 길이까지가 된다. 

2. erase 함수를 사용한다.

substr의 경우는 문자열의 일부를 리턴하는 것이라면 erase는 원하는 범위의 문자들을 삭제한다. 

```
basic_string& erase(size_type index = 0, size_type count = npos);  (1)
iterator erase(const_iterator position);           (2)               
iterator erase(const_iterator first, const_iterator last); (3)
```

(1) index로부터 count 개의 문자를 지우며 count가 문자열 끝을 넘어간다면 그 이상 지우지 않는며 지워진 문자열이 리턴된다.

(2) position 위치에 있는 문자를 지운며 마지막으로 지워진 문자 바로 다음을 가르키는 반복자를 리턴한다.

(3) first부터 last전까지의 문자를 지운며 마지막으로 지워진 문자 바로 다음을 가르키는 반복자를 리턴한다.

**<두번째>**

algorithm 헤터파일을 선언해야하며 sort 함수를 이용한다. 

```
template <typename T>
void sort(T start, T end)
```

```
template <typename T>
void sort(T start, T end, Compare comp)
```

sort 함수는 default로 오름차순으로 정렬이 된다. 이때 세 번째 인자에 사용자 정의 함수도 사용 가능하며 greater<자료형>()의 경우는 내림차순 less<자료형>()의 경우 오름차순 정렬이 된다.

사전순이므로 default인 오름차순으로 하면 되기에 `sort(v.begin(), v.end()); ` 라고 작성해준다.



> Reference
>
> - [modoocode substr](https://modoocode.com/235)
> - [modoocode erase](https://modoocode.com/240)
> - [blockdmask sort](https://blockdmask.tistory.com/178)

