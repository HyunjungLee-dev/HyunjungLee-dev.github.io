---
title:  "[algorithm]BAEKJOON 백준 15596번 정수 N개의 합"
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

# Baekjoon Online Judge No.15596

<https://www.acmicpc.net/problem/15596>

## 문제

정수 n개가 주어졌을 때, n개의 합을 구하는 함수를 작성하시오.

작성해야 하는 함수는 다음과 같다.

- C, C11, C (Clang), C11 (Clang):

   

  ```
  long long sum(int *a, int n);
  ```

  - `a`: 합을 구해야 하는 정수 `n`개가 저장되어 있는 배열 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
  - `n`: 합을 구해야 하는 정수의 개수
  - 리턴값: a에 포함되어 있는 정수 `n`개의 합

- C++, C++11, C++14, C++17, C++ (Clang), C++11 (Clang), C++14 (Clang), C++17 (Clang):

   

  ```
  long long sum(std::vector<int> &a);
  ```

  - `a`: 합을 구해야 하는 정수 `n`개가 저장되어 있는 배열 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
  - 리턴값: `a`에 포함되어 있는 정수 `n`개의 합

- Python 2, Python 3, PyPy, PyPy3:

   

  ```
  def solve(a: list) -> int
  ```

  - `a`: 합을 구해야 하는 정수 `n`개가 저장되어 있는 리스트 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
  - 리턴값: `a`에 포함되어 있는 정수 `n`개의 합 (정수)

- Java:

   

  ```
  long sum(int[] a);
  ```

   

  (클래스 이름: Test)

  - `a`: 합을 구해야 하는 정수 `n`개가 저장되어 있는 배열 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
  - 리턴값: `a`에 포함되어 있는 정수 `n`개의 합

- Go: 

  ```
  sum(a []int) int
  ```

  - `a`: 합을 구해야 하는 정수 `n`개가 저장되어 있는 배열 (0 ≤ a[i] ≤ 1,000,000, 1 ≤ n ≤ 3,000,000)
  - 리턴값: `a`에 포함되어 있는 정수 `n`개의 합

## 제출할 수 있는 언어

C++14, Java, Python 3, C11, PyPy3, C, C++, C++11, C++17, Python 2, PyPy2, Go, C (Clang), C++ (Clang), C++11 (Clang), C++14 (Clang), C11 (Clang), C++17 (Clang)

## 채점

- 예제는 채점하지 않는다.

## 코드	

### C++

```c++
#include<vector>
using namespace std;

long long sum(vector<int> &a)
{
	long long ans = 0;
	for (vector<int>::iterator iter = a.begin(); iter < a.end(); iter++)
	{
		ans += (*iter);
	}

	return ans;

```

처음에 문제를 제대로 안 읽고 함수를 작성했을 때 틀렸다고 나와서 다시 문제를 읽어보니 가이드가 나와있었다. 

```c++
#include <vector>
long long sum(std::vector<int> &a) {
	long long ans = 0;
	return ans;
}
```

위와 같은 가이드 함수가 작성되어 있었고 여기에서 정수 n 개의 합을 구하기 위해서는 vector이기에 반복자를 통해 순차열의 시작인 begin()부터 끝인 end()까지 다음 원소로 이동하며 * 연산자를 통해 원소에 접근하여 더해주고 그 값을 return 해준다.