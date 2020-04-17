---
title:  "[algorithm]BAEKJOON 백준 10039번 평균 점수"
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

# Baekjoon Online Judge No.10039

<https://www.acmicpc.net/problem/10039>

## 문제

상현이가 가르치는 아이폰 앱 개발 수업의 수강생은 원섭, 세희, 상근, 숭, 강수이다.

어제 이 수업의 기말고사가 있었고, 상현이는 지금 학생들의 기말고사 시험지를 채점하고 있다. 기말고사 점수가 40점 이상인 학생들은 그 점수 그대로 자신의 성적이 된다. 하지만, 40점 미만인 학생들은 보충학습을 듣는 조건을 수락하면 40점을 받게 된다. 보충학습은 거부할 수 없기 때문에, 40점 미만인 학생들은 항상 40점을 받게 된다.

학생 5명의 점수가 주어졌을 때, 평균 점수를 구하는 프로그램을 작성하시오.

## 입력

입력은 총 5줄로 이루어져 있고, 원섭이의 점수, 세희의 점수, 상근이의 점수, 숭이의 점수, 강수의 점수가 순서대로 주어진다.

점수는 모두 0점 이상, 100점 이하인 5의 배수이다. 따라서, 평균 점수는 항상 정수이다. 

## 출력

첫째 줄에 학생 5명의 평균 점수를 출력한다.

## 예제 입력 1 

```
10
65
100
30
95
```

## 예제 출력 1 

```
68
```

## 힌트

숭과 원섭이는 40점 미만이고, 보충학습에 참여할 예정이기 때문에 40점을 받게 된다. 따라서, 점수의 합은 340점이고, 평균은 68점이 된다.

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

	int num,sum = 0;
	for (int i = 0; i < 5; i++)
	{
		cin >> num;
		if (num < 40)
			num = 40;
		sum += num;
	}
	cout << sum / 5;
	return 0;

}
```

5명의 학생의 점수를 받고 40점 미만인 경우 점수를 40점으로 하고 5명의 평균을 구하는 문제이다.

for 문을 통해 5번(명)의 점수를 입력받고 if 문으로 num가 40미만일 경우에 대한 조건문을 통해 true 이면 num를 40으로 하고 총 값에 더해준다. 5명의 점수를 모두 더한 후 최종적으로 cout으로 5명의 평균을 출력해 준다.