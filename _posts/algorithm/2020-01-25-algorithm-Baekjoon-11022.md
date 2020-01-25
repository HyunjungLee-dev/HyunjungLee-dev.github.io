---
title:  "[algorithm]BAEKJOON 백준 11022번 A+B - 8"
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

# Baekjoon Online Judge No.11022

[https://www.acmicpc.net/problem/11022](https://www.acmicpc.net/problem/11022)



## 문제

두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.



## 알고리즘 분류

- 사칙연산



## 입력

첫째 줄에 테스트 케이스의 개수 T가 주어진다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)

## 출력

각 테스트 케이스마다 "Case #x: A + B = C" 형식으로 출력한다. x는 테스트 케이스 번호이고 1부터 시작하며, C는 A+B이다.



## 예제 입력 

```markdown
5
1 1
2 3
3 4
9 8
5 2
```



## 예제 출력

```markdown
Case #1: 1 + 1 = 2
Case #2: 2 + 3 = 5
Case #3: 3 + 4 = 7
Case #4: 9 + 8 = 17
Case #5: 5 + 2 = 7
```



## 코드 

```c++
#include<iostream>
using namespace std;

int main()
{
 int T,a,b;
 cin >> T;
 for(int i=0; i<T; i++){
   cin >>a>>b;
   cout << "Case #"<<i+1<<": "<<a<<" + "<<b<<" = "<<a+b<<endl;
}
 return 0;   
}
```


