---
title:  "[algorithm]BAEKJOON 백준 2439번 별 찍기 - 2 "
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

# Baekjoon Online Judge No.2439

<https://www.acmicpc.net/problem/2439>

## 문제

첫째 줄에는 별 1개, 둘째 줄에는 별 2개, N번째 줄에는 별 N개를 찍는 문제

하지만, 오른쪽을 기준으로 정렬한 별(예제 참고)을 출력하시오.

## 입력

첫째 줄에 N(1 ≤ N ≤ 100)이 주어진다.

## 출력

첫째 줄부터 N번째 줄까지 차례대로 별을 출력한다.

## 예제 입력 1 복사

```
5
```

## 예제 출력 1 복사

```
    *
   **
  ***
 ****
*****
```

## 알고리즘 분류

- [출력](https://www.acmicpc.net/problem/tag/출력)



## 코드

### C++

```c++
#include <iostream>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	int n;
	cin >> n;
	for (int i = 0; i < n; i++) // 1부터 n줄 
	{
		for (int j = n-1; j >=0; j--) // 4,3,2,1,0
		{
			if (j > i)
				cout << " ";
			else
				cout << "*";
		}
		cout << '\n';
	}

	return 0;

}
```

for 문 문제이다. 이중 for 문을 사용하게 되는데 먼저 공백이 출력 될때와 별이 출력 될때를 생각해야하기 때문에 조건문을 사용하게 된다.  i의 경우 몇 줄을 출력할 것인가에 대한 반복문이며 j의 경우는 공백과 별을 출력하는 것이다. 

[n = 5 일때]

| i    | j                 |
| ---- | ----------------- |
| 0    | 4~1(" ") 0("*")   |
| 1    | 4~2(" ") 1~0("*") |
| 2    | 4~3(" ") 2~0("*") |
| 3    | 4(" ") 3~0("*")   |
| 4    | 4~0("*")          |

