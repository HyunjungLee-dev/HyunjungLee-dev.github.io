---
title:  "[data structure]단순 연결 리스트(Singly Linked List)"
comments: true
toc : true
toc_sticky : true
categories:
  - data structure
tags:
  - List
  - Singly Linked List
  - C
  - data structure
---

![DLinkedList_001](https://user-images.githubusercontent.com/54986748/72410751-8f854580-37ac-11ea-956b-6ed9991063d1.jpg)

# 단순 연결 리스트(Singly Linked List)

![Single_linked_list](https://user-images.githubusercontent.com/54986748/73063680-b21d0a00-3ee2-11ea-8148-daa2a45c5988.png)

​                                                         **Singly Linked list (출처 : wikipedia)**

단순 연결 리스트는 각 노드에 자료 공간과 한 개의 포인터 공간이 있고, 각 노드의 포인터는 다음 노드를 가리키는 자료구조로 연결의 형태가 한쪽으로 전개되기에 시작과 끝이 분명하게 존재한다.



## 단순 연결 리스트의 ADT 

- void ListInit(List* plist); 초기화
- void Linsert(List* plist, LData data); 삽입
- int Lfirst(List* plist, LData data); 조회(첫 번째)
- int LNext(List* plist, LData data); 조회(두 번째~)
- LData LRemove(List* plist); 삭제
- void SetSortRule(List* plist, int(*comp)(LData d1, LData d2));정렬
- int LCount(List* plist); 데이터의 수 검색



## 구현 사항의 결정

**Q. head와 tail이 있는데 tail로 데이터가 추가되지 않다면  tail이 필요 없지 않을까?**

**A.** 새 노드의 추가 위치에 따라 장단점이 존재한다.

- 머리에 추가하는 경우는 포인터 변수 tail이 불필요하지만 저장된 순서를 유지하지 않는다.

- 꼬리에 추가하는 경우는 저장된 순서가 유지되지만, 포인터 변수 tail이 필요하게 된다.

하지만 머리로 추가 했을 때 저장된 순서를 유지하지 않는 단점은 자료구조에서 필요 사항이 아니기도 하고 연결 관계를 의미하는 포인터 변수는 하나라도 줄면 코드가 보기 좋아진다 즉, tail을 사용해서 생기는 코드 적인 코스트를 제거하는 것이 족이므로 머리에 추가하는 것이 좋다.

```c
if (head == NULL) //첫 번째 Node 상황
			head = newNode;
		else // 두 번째 이후 Node 상황
			tail->next = newNode;
```

**Q. 첫 번째 Node 상황과 두 번째 Node 상황이 나뉘지 않고 항상 같은 상황으로 만들 수 있지 않을까?**

**A.** **더미 노드(Dummy Node)**를 이용하면 된다. 더미 노드는 유효한 데이터를 지니지 않는 빈 노드를 의미하며 유효한 데이터가 추가되는 노드가 구조상 두 번째 노드가 되므로 가 첫 번째 노드와 두 번째 노드에 차이가 있는 것을 없애고 일관된 형태로 구성된다. 

**<Dummy Node 추가 했을 경우의 코드 변화>**

<img width="511" alt="dummynode" src="https://user-images.githubusercontent.com/54986748/73064218-0eccf480-3ee4-11ea-9283-bc349ba64767.png">

```c
head = (Node*)malloc(sizeof(Node)); /*더미노드*/
tail = head;

/*** 노드의 추가과정 ***/
		newNode = (Node*)malloc(sizeof(Node));
		newNode->data = readData;
		newNode->next = NULL;
        /*
        if(head == NULL)
            head = newNode;
        else
            tail->next = newNode;
        */ //생략 되는 코드
		tail->next = newNode;

		tail = newNode;
```



## 더미노드 기반 연결리스트 구현

#### 헤더 파일의 구현

```c
#ifndef __D_LINKED_LIST_H__
#define __D_LINKED_LIST_H__

#define TRUE	1
#define FALSE	0

typedef int LData;

typedef struct _node 
{
	LData data;
	struct _node * next;
} Node;

// Main에서 필요한 List : 단일 변수로 구현하게 되면 List가 여러 개일때 어려움을 겪게 된다.

typedef struct _linkedList 
{
	Node * head; // 더미 노드를 가리키는 멤버
	Node * cur; // 참조 및 삭제를 돕는 멤버
	Node * before; // 삭제를 돕는 멤버
	int numOfData; // 저장된 데이터 수를 기록하기 위한 멤버
	int(*comp)(LData d1, LData d2); //정렬의 기준을 등록하기 위한 멤버
} LinkedList;


typedef LinkedList List;

void ListInit(List * plist); // 초기화
void LInsert(List * plist, LData data); //삽입

int LFirst(List * plist, LData * pdata); // 조회
int LNext(List * plist, LData * pdata); // 조회

LData LRemove(List * plist); // 삭제
int LCount(List * plist); // 데이터 수 검색

void SetSortRule(List * plist, int(*comp)(LData d1, LData d2)); // 정렬 기준 등록

#endif

```

#### 초기화

```c
void ListInit(List * plist)
{
	plist->head = (Node*)malloc(sizeof(Node)); // Dummy Node의 생성
	plist->head->next = NULL;
	plist->comp = NULL;
	plist->numOfData = 0;
}
```

#### 삽입

```c
void LInsert(List * plist, LData data)
{
	if(plist->comp == NULL) // 정렬 기준이 설정 되어 있지 않으면(없으면)
		FInsert(plist, data); // 머리에 Node를 추가한다.
	else
		SInsert(plist, data);// 정렬 기준이 있으면 그것에 근거하여 Node를 추가한다.
}

```

#### FInsert 구현

```c
void FInsert(List * plist, LData data)
{
	Node * newNode = (Node*)malloc(sizeof(Node));// 새 노드 생성
	newNode->data = data;// 새 노드에 데이터 저장

	newNode->next = plist->head->next; // 새 노드가 다른 노드를 가리킨다
	plist->head->next = newNode;// 더미 노드가 새 노드를 가리킨다(머리에 추가하니깐)

	(plist->numOfData)++;//저장된 노드 수를 증가
}
```

#### 조회

```c
// 더미노드 다음에 오는 노드가 첫 번째 노드
int LFirst(List * plist, LData * pdata) 
{
	if(plist->head->next == NULL) // 더미노드가 NULL을 가리키면 반환할 데이터가 없다
		return FALSE;

	plist->before = plist->head; // before은 더미노드를 가리킨다
	plist->cur = plist->head->next; // cur은  첫 번째 노드(유효한 값을 가진)를 가리킨다

	*pdata = plist->cur->data; // 데이터 전달
	return TRUE;
}

int LNext(List * plist, LData * pdata)
{
	if(plist->cur->next == NULL)//cur이 NULL을 가리키면 반환할 데이터가 없다.
		return FALSE;

	plist->before = plist->cur; 
    // cur이 가리키던 것을 before가 가리킨다(cur은 다음으로 넘어가니깐)
	plist->cur = plist->cur->next; 
    //cur은 그 다음 노드를 가리킨다(다음에 있는 것을 조회해야 하니깐)

	*pdata = plist->cur->data; // cur이 가리키는 노드의 데이터 전달
	return TRUE;
}

```

#### 삭제

```c
LData LRemove(List * plist)
{
    // 소멸 대상을 저장해두지 않으면 삭제를 할 때 주소를 모르게 된다
	Node * rpos = plist->cur; 
	LData rdata = rpos->data;

	plist->before->next = plist->cur->next; // 소멸 대상을 리스트에서 제거
	plist->cur = plist->before; // cur이 가리키는 위치를 재조정

	free(rpos);
	(plist->numOfData)--;
	return rdata;
}
```

cur과 before이 동일한 위치를 가리키게 되어 before 또한 왼쪽으로 이동시켜야 하는 게 아닐까 하는 의문이 있을 수 있는데 before의 위치는 재조정할 필요가 없다. LFirst나 LNext 함수가 호출되면 before는 다시 cur보다 하나 앞선 코드를 가리키게 된다.

#### 데이터  수 검색

```c
int LCount(List * plist)
{
	return plist->numOfData;
}
```



## 정렬 삽입 구현

정렬 삽입에 경우 필수 사항은 아니다 하지만 머리에 추가하게 될 경우 1, 2, 3을 순서대로 넣었다고 했을 때 조회하여 출력하면 3, 2, 1 과 같이 역순으로 출력이 되는데 넣은 순서와 출력할 때의 순서를 같게 해주기 위해 즉, 보완을 위해 정렬 기능을 삽입했다고 보면 된다. 여기서 정렬의 기준은 구현 자가 정할 수 있다.

#### SInsert 구현

```c
void FInsert(List * plist, LData data)
{
	Node * newNode = (Node*)malloc(sizeof(Node));// 새 노드 생성
	newNode->data = data;// 새 노드에 데이터 저장

	newNode->next = plist->head->next; // 새 노드가 다른 노드를 가리킨다
	plist->head->next = newNode;// 더미 노드가 새 노드를 가리킨다(머리에 추가하니깐)

	(plist->numOfData)++;//저장된 노드 수를 증가
}
```

#### 정렬 기준 등록

```c
void SetSortRule(List * plist, int (*comp)(LData d1, LData d2))
{
	plist->comp = comp;
}
```

#### 정렬 기준을 설정하는 함수 정의

```c
int WhoIsPrecede(int d1, int d2)
{
    if(d1<d2)
        return 0;
    else
        return 1;
}
```



## Reference

- 윤성우 『열혈자료구조』 , 오렌지미디어 , 2012
- 아텐츠 게임 아카데미 수업 자료

------

오류가 있으면 댓글로 알려주세요.

이 포스트는 비정기적으로 내용이 추가/수정/삭제 될 수 있습니다.