---
title:  "[BAEKJOON 백준]1001번 A-B"
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

# Baekjoon Online Judge No.1001

[https://www.acmicpc.net/problem/1001](https://www.acmicpc.net/problem/1001)



## 문제

두 정수 A와 B를 입력받은 다음, A-B를 출력하는 프로그램을 작성하시오.



## 입력

첫째 줄에 A와 B가 주어진다. (0 < A, B < 10)



## 출력

첫째 줄에 A-B를 출력한다.



## 예제 입력 

```markdown
3 2
```



## 예제 출력

```markdown
1
```



## 코드

```c++
#include <iostream>
using namespace std;
int main()
{
	int a, b;
	cin >> a >> b;
	cout << a - b << endl;
	return 0;
}
```

