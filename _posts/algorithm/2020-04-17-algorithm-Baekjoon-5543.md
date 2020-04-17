---
title:  "[algorithm]BAEKJOON 백준 5543번 상근날드"
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

# Baekjoon Online Judge No.5543

<https://www.acmicpc.net/problem/5543>

## 문제

상근날드에서 가장 잘 팔리는 메뉴는 세트 메뉴이다. 주문할 때, 자신이 원하는 햄버거와 음료를 하나씩 골라, 세트로 구매하면, 가격의 합계에서 50원을 뺀 가격이 세트 메뉴의 가격이 된다.

햄버거는 총 3종류 상덕버거, 중덕버거, 하덕버거가 있고, 음료는 콜라와 사이다 두 종류가 있다.

햄버거와 음료의 가격이 주어졌을 때, 가장 싼 세트 메뉴의 가격을 출력하는 프로그램을 작성하시오.

## 입력

입력은 총 다섯 줄이다. 첫째 줄에는 상덕버거, 둘째 줄에는 중덕버거, 셋째 줄에는 하덕버거의 가격이 주어진다. 넷째 줄에는 콜라의 가격, 다섯째 줄에는 사이다의 가격이 주어진다. 모든 가격은 100원 이상, 2000원 이하이다.

## 출력

첫째 줄에 가장 싼 세트 메뉴의 가격을 출력한다.

## 예제 입력 1 

```
800
700
900
198
330
```

## 예제 출력 1 

```
848
```

## 예제 입력 2 

```
1999
1999
100
189
100
```

## 예제 출력 2 

```
150
```

## 알고리즘 분류

- [구현](https://www.acmicpc.net/problem/tag/구현)

## 코드	

### C++

```c++
#include <iostream>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	int burger[3];
	int drink[2];
	cin >> burger[0] >> burger[1] >> burger[2];
	cin >> drink[0] >> drink[1];

	int bcheck = burger[0];
	for (int i = 1; i < 3; i++)
	{
		if (bcheck > burger[i])
			bcheck = burger[i];
	}
	int dcheck = drink[0] > drink[1] ? drink[1] : drink[0];
	cout << bcheck + dcheck - 50;



	return 0;

}
```

```c++
#include <iostream>
using namespace std;

int main()
{
	cin.tie(NULL);
	ios_base::sync_with_stdio(false);

	int burger, drink, set ,temp;

	cin >> burger>>temp;
	if (burger > temp)
		burger = temp;
	cin >> temp;
	if (burger > temp)
		burger = temp;
	cin >> drink >> temp;
	if (drink > temp)
		drink = temp;
	set = burger + drink - 50;
	cout << set;

	return 0;

}
```

if문을 이용하는 문제이다. 각각을 비교해서 더 값이 낮은 값을 버거 값, 음료 값으로 한 후 더한 후 50원을 빼준다.

