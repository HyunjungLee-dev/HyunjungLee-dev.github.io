---
title:  "[algorithm]BAEKJOON 백준 15552번 빠른 A+B"
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

# Baekjoon Online Judge No.15552

<https://www.acmicpc.net/problem/15552>

## 문제

본격적으로 for문 문제를 풀기 전에 주의해야 할 점이 있다. 입출력 방식이 느리면 여러 줄을 입력받거나 출력할 때 시간초과가 날 수 있다는 점이다.

C++을 사용하고 있고 `cin`/`cout`을 사용하고자 한다면, `cin.tie(NULL)`과 `sync_with_stdio(false)`를 둘 다 적용해 주고, `endl` 대신 개행문자(`\n`)를 쓰자. 단, 이렇게 하면 더 이상 `scanf`/`printf`/`puts`/`getchar`/`putchar` 등 C의 입출력 방식을 사용하면 안 된다.

Java를 사용하고 있다면, `Scanner`와 `System.out.println` 대신 `BufferedReader`와 `BufferedWriter`를 사용할 수 있다. `BufferedWriter.flush`는 맨 마지막에 한 번만 하면 된다.

Python을 사용하고 있다면, `input` 대신 `sys.stdin.readline`을 사용할 수 있다. 단, 이때는 맨 끝의 개행문자까지 같이 입력받기 때문에 문자열을 저장하고 싶을 경우 `.rstrip()`을 추가로 해 주는 것이 좋다.

또한 입력과 출력 스트림은 별개이므로, 테스트케이스를 전부 입력받아서 저장한 뒤 전부 출력할 필요는 없다. 테스트케이스를 하나 받은 뒤 하나 출력해도 된다.

자세한 설명 및 다른 언어의 경우는 [이 글](http://www.acmicpc.net/board/view/22716)에 설명되어 있다.

[이 블로그 글](http://www.acmicpc.net/blog/view/55)에서 BOJ의 기타 여러 가지 팁을 볼 수 있다.

## 입력

첫 줄에 테스트케이스의 개수 T가 주어진다. T는 최대 1,000,000이다. 다음 T줄에는 각각 두 정수 A와 B가 주어진다. A와 B는 1 이상, 1,000 이하이다.

## 출력

각 테스트케이스마다 A+B를 한 줄에 하나씩 순서대로 출력한다.

## 예제 입력 1 

```
5
1 1
12 34
5 500
40 60
1000 1000
```

## 예제 출력 1 

```
2
46
505
100
2000
```

## 코드

### C++

```c++
#include <iostream>
using namespace std;

int main(void)
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	int t, a, b;
	cin >> t;
	for (int i = 0; i < t; i++)
	{
		cin >> a >> b;
		cout << a + b << '\n';
	}

	return 0;

}
```

for문 문제이다. 이 문제에서는 시간 초과가 없도록 코드를 작성하는 것이 a+b를 출력하는 것 이외에 문제를 해결하는 것에 또 하나의 목표이다.

 입출력 방식에 따라서 속도의 차이가 있게 되는데 c++의 경우에 입출력 속도를 빠르게 하고 싶다면  cin, cout을 사용할 때는 `cin.tie(NULL)` 과 `ios_base::sync_with_stdio(false)`를 사용하는 것이 좋고 `ios_base::sync_with_stdio(false)`를 사용할 때는 scanf, printf와 섞어서 사용해서는 안 된다. 한편으로 cin과 cout을 사용하지 않아도 scanf/prinf는 충분히 속도가 빠르기 때문에 cin,cout 쓰지 않고 scanf와 printf를 사용하는 것으로 속도 문제는 해결될 것이다. 또한 endl 을 '\n' 으로 바꾸어주는 것으로 시간 향상이 된다.



> 입출력 방법에 따른 속도 참조/참고 사이트
>
> - [eine.tistory](https://eine.tistory.com/entry/CC-입출력-방법에-따른-속도-정리)
> - https://www.acmicpc.net/board/view/22716

