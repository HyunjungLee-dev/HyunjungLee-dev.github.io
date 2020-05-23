---
title:  "[algorithm]BAEKJOON 백준 1152번 단어의 개수"
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

# Baekjoon Online Judge No.1152

<https://www.acmicpc.net/problem/1152>

## 문제

영어 대소문자와 띄어쓰기만으로 이루어진 문자열이 주어진다. 이 문자열에는 몇 개의 단어가 있을까? 이를 구하는 프로그램을 작성하시오. 단, 한 단어가 여러 번 등장하면 등장한 횟수만큼 모두 세어야 한다.

## 입력

첫 줄에 영어 대소문자와 띄어쓰기로 이루어진 문자열이 주어진다. 이 문자열의 길이는 1,000,000을 넘지 않는다. 단어는 띄어쓰기 한 개로 구분되며, 공백이 연속해서 나오는 경우는 없다. 또한 문자열의 앞과 뒤에는 공백이 있을 수도 있다.

## 출력

첫째 줄에 단어의 개수를 출력한다.

## 예제 입력 1 

```
The Curious Case of Benjamin Button
```

## 예제 출력 1

```
6
```

## 예제 입력 2 

```
 Mazatneunde Wae Teullyeoyo
```

## 예제 출력 2 

```
3
```

## 예제 입력 3 

```
Teullinika Teullyeotzi 
```

## 예제 출력 3 

```
2
```

## 코드	

### C++

```c++
#include <iostream>
#include<string>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);
	string str;
	int count = 1;
	getline(cin, str);
	for (int i = 0; i < str.size(); i++)
	{
		if (str[i] == ' ')
			count++;
	}
	if (str[0] == ' ')
		count--;
	if (str[str.size() - 1] == ' ')
		count--;
	cout << count;
	
	return 0;
}
```

문자열 처리 문제이다. 이 문제에서 신경 써야 할 부분은 공백에 관한 부분이었다. 먼저 cin으로는 공백을 포함한 문자열 입력을 받지 못하기 때문에 getline을 통해 문자열을 입력받는다. 구하고자 하는 것은 단어의 개수이기 때문에 문장의 마지막 단어도 count 되기 위해 count 변수는 1로 초기화 시켜준다. for 문을 통해 공백이 나올 때 count++을 해주고 문장의 처음과 끝에 단어를 구분하는 공백이 아닌 공백이 있을 수 있기에 조건문을 통해 count--를 해준다. 여기서 size()를 통해 문자열의 길이를 가져왔지만 size()가 아닌 length()를 이용할 수도 있다.

`if (str[str.size() - 1] == ' ')` 여기서 -1을 해주는 이유는 문자열의 길이가 5라고 해도 인덱스 5에 접근하려 하면 문자열의 범위를 넘어가게 되기 때문이다.

> [Hashcode](https://hashcode.co.kr/questions/5777/c-string-클래스에-문자열을-저장할-때는-널문자가-없나요) string 클래스의 null 문자에 대한 답변이 상세하게 되어있다.

