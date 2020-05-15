---
title:  "[algorithm]BAEKJOON 백준 8958번 OX퀴즈"
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

# Baekjoon Online Judge No.8958

<https://www.acmicpc.net/problem/8958>

## 문제

"OOXXOXXOOO"와 같은 OX퀴즈의 결과가 있다. O는 문제를 맞은 것이고, X는 문제를 틀린 것이다. 문제를 맞은 경우 그 문제의 점수는 그 문제까지 연속된 O의 개수가 된다. 예를 들어, 10번 문제의 점수는 3이 된다.

"OOXXOXXOOO"의 점수는 1+2+0+0+1+0+0+1+2+3 = 10점이다.

OX퀴즈의 결과가 주어졌을 때, 점수를 구하는 프로그램을 작성하시오.

## 입력

첫째 줄에 테스트 케이스의 개수가 주어진다. 각 테스트 케이스는 한 줄로 이루어져 있고, 길이가 0보다 크고 80보다 작은 문자열이 주어진다. 문자열은 O와 X만으로 이루어져 있다.

## 출력

각 테스트 케이스마다 점수를 출력한다.

## 예제 입력 1

```
5
OOXXOXXOOO
OOXXOOXXOO
OXOXOXOXOXOXOX
OOOOOOOOOO
OOOOXOOOOXOOOOX
```

## 예제 출력 1 

```
10
9
7
55
30
```

## 코드	

### C++

```c++
#include<iostream>
using namespace std;

int main()
{
	int num;
	char str[80];
	cin >> num;
	for (int i = 0; i < num; i++)
	{
		int sum = 0, num = 0;
		cin >> str;
		for (int i = 0; i < 80; i++)
		{
			if (str[i] == 'O')
			{
				num++;
				sum += num;
			}
			else if (str[i] == 'X')
			{
				num = 0;
			}
			if (str[i + 1] == NULL)
			{
				cout << sum <<'\n';
				break;
			}

		}
	}
	
	
	return 0;
}
```

길이가 0보다 크고 80보다 작다고 하였기에 그에 맞게 배열의 길이를 설정해 주었고 O가 나올 경우 ++로 num이라는 변수가 1씩 증가 후 더해지기 때문에 연속된 경우 즉, OO와 같은 경우도 num이 1, num이 2가 되면서 총 3의 값을 얻을 수 있다 X가 나오면 더해지는 값이 0이 되기 때문에 0으로 해주고 OX 문장이 끝났을 때 점수를 출력해 준다.

```c++
#include<iostream>
using namespace std;

void ox(char str[], int index, int *score)
{
	if (str[index] == 'O')
	{
		*score+=1;
		ox(str, ++index,score);
	}
}

int main()
{
	int num;
	char str[80];
	cin >> num;
	for (int i = 0; i < num; i++)
	{
		int score = 0;
		cin >> str;
		int j = 0;
		while (str[j])
		{
			ox(str, j,&score);
			j++;
		}
		cout << score << '\n';
	}

	return 0;
}
```

첫 번째 코드의 경우 for 문과 if 문만으로 해결이 가능했다. 두 번째 방법으로 재귀 함수를 이용하여 해결할 수 있다. 'O'인 경우는 재귀 함수를 통해 다음에도 'O'가 있는지 확인하게 되며 점수가 1씩 증가하게 된다.

```c++
	ios_base::sync_with_stdio(false);
	cin.tie(NULL);
```

위의 두 해결 방법은 모두 시간이 4ms로 나왔고 충분히 시간을 0ms로 나올 수 있다고 생각이 들어 두 번째 코드를 알아보고 시도해본 것이다. 결론은 위의 두 코드를 추가함으로써 0ms가 나왔다. 위 코드는 15552번의 문제에서도 언급이 되는데 알고리즘 문제를 풀 때 시간이 초과되는 경우가 생기는데 그런 부분을 해결하기 위해서 빠른 입출력을 하기 위한 방법이 있다. https://www.acmicpc.net/board/view/22716의 주소를 참고해보자.