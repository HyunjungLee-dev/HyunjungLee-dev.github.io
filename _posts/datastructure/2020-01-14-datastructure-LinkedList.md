---
title:  "[data structure]연결 리스트(Linked List)"
comments: true
toc : true
toc_sticky : true
categories:
  - data structure
tags:
  - List
  - Linked list
  - C++
  - data structure
---

![LinkedList_001](https://user-images.githubusercontent.com/54986748/72061080-7dbd2180-3318-11ea-90c5-32914a0f5f32.jpg)

# 연결 리스트(Linked List)

- 고정 크기(크기가 정적)의 배열 등에 의해 구현된 [순차 리스트]([https://hyunjunglee-dev.github.io/data%20structure/datastructure-OrderedList/](https://hyunjunglee-dev.github.io/data structure/datastructure-OrderedList/))의 단점을 보완한 자료구조이다.
- 원소(element)와 원소 간의 **연결(link)**을 이용해서 리스트를 구현한 것이다. 



## 연결 리스트의 특징

- 저장 데이터 및 포인터에 의해 연결된 비순차적 자료구조
  - 동적 할당을 위하여 **구조체를 가리키는 포인터**를 이용한다.
  - 동적으로 크기가 변할 수 있으며 삭제, 삽입 등에 데이터 이동의 필요가 없다.
- 데이터가 필요할 때마다 하나씩 추가하여 사용할 수 있으며  리스트의 요소 하나를  **Node**(서로를 가리키는 통로)라고 말한다.

![LinkedList_002](https://user-images.githubusercontent.com/54986748/72063919-1bffb600-331e-11ea-83b6-623a1c04ba0c.jpg)

### Trade off

- 배열에 의한 연결 리스트의 구현 시에는, 요소의 추가, 삭제에 비교적 많은 시간이 소요된다.
- 연결 리스트의 경우 데이터를 검색할 때 느리며 상대적으로 구현이 어렵고, 포인터의 저장 필요에 저장 공간이 많이 소요된다. (추가적으로 공간이 필요하다)



## 연결 리스트의 구조

![LinkedList_003](https://user-images.githubusercontent.com/54986748/72252597-e7a03880-3642-11ea-8094-1f3b2e0e8e3e.png)

```c++
//Node(vertex)
typedef struct _node
{
    int data; //데이터를 담을 공간
    struct _node* next; //연결의 도구
}Node;
```

- **Head** :  연결리스트를 사용하기 위해서는 이 Head가 가리키는 첫 번째 노드를 찾아야 한다. 이를 잃어버리면 연결리스트 전체를 잃게 된다. Head가 아닌 First와 같은 이름을 사용하기도 한다.



## 연결 리스트의 구현

**<연결 리스트의 개념을 이해하기 위한 코드>**

### 초기화

```C++
	Node * head = NULL;    // NULL 포인터 초기화
	Node * tail = NULL;
	Node * cur = NULL;

	Node * newNode = NULL;
	int readData;
```



### 삽입

```C++
While(1)
{
		newNode = (Node*)malloc(sizeof(Node));
		newNode->data = readData;
		newNode->next = NULL;

		if (head == NULL) //첫 번째 Node 추가 
			head = newNode;
		else // 두 번째 이후 Node 추가과정
			tail->next = newNode;

		tail = newNode;
}
```



### 조회

```C++
if (head == NULL)
	{
		printf("저장된 자연수가 존재하지 않습니다. \n");
	}
	else
	{
		cur = head;
		printf("%d  ", cur->data);   // 첫 번째 데이터 출력

		while (cur->next != NULL)    // 두 번째 이후의 데이터 출력
		{
			cur = cur->next;
			printf("%d  ", cur->data);
		}
	}
```



### 삭제

```C++
if (head == NULL)
	{
		return 0;    // 해제할 노드가 존재하지 않는다.
	}
	else
	{
		Node * delNode = head;
		Node * delNextNode = head->next;

		printf("%d을(를) 삭제합니다. \n", head->data);
		free(delNode);    // 첫 번째 노드의 삭제

		while (delNextNode != NULL)    // 두 번째 이후의 노드 삭제 위한 반복문
		{
			delNode = delNextNode;
			delNextNode = delNextNode->next;

			printf("%d을(를) 삭제합니다. \n", delNode->data);
			free(delNode);    // 두 번째 이후의 노드 삭제
		}
	}
```



## 연결 리스트의 구분

- 단순 연결 리스트(Singly Linked Linear List)
- 이중 연결 리스트(Doubly Linked Linear List)
- 원형 연결 리스트 (Circularly Linked Linear List)



## Reference

- [생활코딩 Linked list](https://opentutorials.org/module/1335/8821)
- [정보통신기술용어해설 ](http://www.ktword.co.kr/abbr_view.php?m_temp1=3979)
- 윤성우 『열혈자료구조』 , 오렌지미디어 , 2012
- 아텐츠 게임 아카데미 수업 자료

------

오류가 있으면 댓글로 알려주세요.

이 포스트는 비정기적으로 내용이 추가/수정/삭제 될 수 있습니다.