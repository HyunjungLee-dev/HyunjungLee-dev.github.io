---
title:  "[algorithm]BAEKJOON 백준 10951번 A+B - 4"
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

# Baekjoon Online Judge No.10951

https://www.acmicpc.net/problem/10951



## 문제

두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.



## 알고리즘 분류

- 사칙연산



## 입력

입력은 여러 개의 테스트 케이스로 이루어져 있다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)

## 출력

각 테스트 케이스마다 A+B를 출력한다.



## 예제 입력 

```markdown
1 1
2 3
3 4
9 8
5 2
```



## 예제 출력

```markdown
2
5
7
17
7
```



## 코드 확인

### 오류 코드 1

```c++
#include <iostream>
using namespace std;
int main()
{
	int a, b;
	cin >> a >> b;
	cout << a + b << endl;
}
```

처음에는 조건 없이 입력 받고 더해서 출력만 하면 된다고 생각했었다. 여기에서는 문제에 제시 된 '여러 개'의 테스트 케이스가 빠져있다.



### 오류 코드 2

```C++
#include <iostream>
using namespace std;
int main()
{
	int a, b;
	while (1)
	{
		cin >> a >> b;
		cout << a + b << endl;
	}
}
```

그렇다면 여러 개를 입력 받을 수 있도록 while을 이용하면 어떨까라는 생각으로 작성하였으나  <span style="color:red">`출력 초과`</span>라는 결과가 나왔다. 이 결과가 나오는 이유는 while을 탈출하는 조건(종료 조건)을 주지 않았기 때문이다. EOF(End Of File)에 대한 이해가 필요하다.

**EOF(End Of File)** 파일의 끝을 표현하기 위한 함수(-1의 값을 가진다) 콘솔의 경우 Ctrl + z 가 파일의 EOF를 의미한다.

**cin.eof()** bool타입을 가지며 파일의 끝을 의미하는 EOF를 읽게 되면, true 값으로 바뀌게 된다.

### 최종 코드

```C++
#include <iostream>//C++
using namespace std;
 
int main(void) {
   int a,b;
 
   while(true) {
       cin >> a >> b;
       if(cin.eof() == true) {
           break;
       }
       cout << a + b << endl;
   }
}

```

```c++
#include <iostream> //C++
using namespace std;
int main()
{
	int a, b;
	while (cin >> a >> b)
	{
		cout << a + b << endl;
	}
	return 0;
}
```

```c

#include <stdio.h> //C

int main()
{
	int a, b;
	while (scanf("%d %d",&a,&b)!= EOF)
    {
        printf("%d\n", a+b);
    }
	
	return 0;
}
```

## Reference

https://lollolzkk.tistory.com/15

https://takeknowledge.tistory.com/20

[솔개 블로그](https://9m1i9n1.github.io/devlog/2019/04/04/백준-10951-A+B-4-(입력-종료-조건-없을-때)/)
