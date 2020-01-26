---
title:  "[algorithm]BAEKJOON 백준 11718번 그대로 출력하기"
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

# Baekjoon Online Judge No.11718

[https://www.acmicpc.net/problem/11718](https://www.acmicpc.net/problem/11718)

## 문제

입력 받은 대로 출력하는 프로그램을 작성하시오.

## 알고리즘 분류

- 출력



## 입력

입력이 주어진다. 입력은 최대 100줄로 이루어져 있고, 알파벳 소문자, 대문자, 공백, 숫자로만 이루어져 있다. 각 줄은 100글자를 넘지 않으며, 빈 줄은 주어지지 않는다. 또, 각 줄은 공백으로 시작하지 않고, 공백으로 끝나지 않는다.

## 출력

입력받은 그대로 출력한다.



## 예제 입력 

```markdown
Hello
Baekjoon
Online Judge
```



## 예제 출력

```markdown
Hello
Baekjoon
Online Judge
```



## 코드 

```c++
#include<iostream>
#include<string>
using namespace std;

int main()
{
   string str;
    
   while(1)
   {
     getline(cin,str);
     if(str == "")
         break;
       cout<<str<<endl;
   }
    return 0;
}
```

c++에서 문자열을 받는 string 자료형을 이용하였고 공백 문자도 포함 시킬 수 있는 getline 함수를 이용해야한다.

