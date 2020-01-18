---
title:  "[data structure]순차 리스트(Ordered List)"
comments: true
toc : true
toc_sticky : true
categories:
  - data structure
tags:
  - List
  - Linear List
  - Ordered List
  - C++
  - data structure
---

![0002](https://user-images.githubusercontent.com/54986748/71999988-b6f88180-3285-11ea-9a9a-09ce268b2e32.jpg)

# 순차 리스트

List(리스트)는 LinkedList만을 의미하는 것이 아니다. 리스트는 순차 리스트, 연결 리스트를 모두 말하게 되며 여기서 순차 리스트는 연속되는 장소에 저장되는 순차적 자료구조를 말한다. **데이터의 수가 정해져 있고 변화가 없는 상황에서 참조만 해서 사용할 경우에만 사용하는 것이 바람직하며 주로 고정 크기의 배열(Array)을 기반으로(이용하여) 순차 리스트를 구현한다.**



## Array(배열)

### 1. 배열의 개념

- 연관 된 여러 데이터를 하나의 변수에 그룹핑해서 효율적으로 관리할 수 있는 자료구조

### 2. 배열의 용어

![003](https://user-images.githubusercontent.com/54986748/72000040-c972bb00-3285-11ea-866f-e51fd578697d.gif)

- index : 전체 집단에서 데이터를 식별 해주는 역할을 하는 값
- value : 배열에 저장 된 값
- element(원소) : index와 value가 결합되어 있는 것

### 3. 배열의 한계

![004](https://user-images.githubusercontent.com/54986748/72000050-cf689c00-3285-11ea-99dc-a7311c85eb19.gif)

- 배열은 인덱스에 따라서 값을 유지하기 때문에, 원소가 삭제 되었을때 빈자리가 남게 된다.

  - 메모리의 낭비를 초래한다.
  - 배열에 데이터가 있는지 없는지를 체크하는 로직이 필요하다는 의미이기도 하다.

- 조건문을 이용하여 빈 원소를 제외해도 되지만 반복문이 많아지는만큼 조건문도 많아진다.

  

![005](https://user-images.githubusercontent.com/54986748/72000057-d42d5000-3285-11ea-997c-7be64cedb022.gif)



- 삭제한 자리(빈자리)를 뒤에 위치한 원소로 메꾼다. 이렇게 데이터가 순서에 따라서 빈틈 없이 연속적으로 위치하는 자료구조를 List(리스트)라고 한다. 
- 인덱스가 중요한 경우: 배열 사용 (null를 처리에서 제외한다면 조건문 사용)
- 인덱스가 중요하지 않은 경우 : 리스트 사용



## 순차 리스트의 특징

- 원소들 간에 순서가 유지되며 위치하여 표현이 간단하고 원소 위치를 찾기가 비교적 쉽다.

- 논리적 및 물리적 순서가 같다. ex) 사전, 전화번호부, 주소록 등

- 원소들의 추가적인 이동이 필요하여 순차 리스트 내 삽입, 삭제 연산 시에는 비효율적이다.

- 실행 전, 크기를 결정해야 하는 정적 메모리 할당 방식으로 고정 크기 이므로, 저장공간 사용이 비효율적이다.

  

## 순차 리스트의 장단점(LinkedList와 비교시)

### 1. 장점

- 데이터의 참조가 쉽다.
  - index 값을 기준으로 어디든 한 번에 참조가 가능하다.
  - 데이터를 가져오는 것이 빠르다.

### 2. 단점

- 배열의 길이가 초기에 결정되어야 하기에 배열의 길이 변경은 불가능하다.
- 삭제의 과정에서 데이터의 이동(복사)가 매우 빈번히 일어난다.
  - 데이터의 추가와 삭제가 느리다.

## 순차 리스트의 구현

### List 자료 구조의 ADT

- Void ListInit(List* plist); - 초기화
- void LInsert(List* plist, LData data); - 삽입
- int LFirst(List* plistm LData data); - 조회(첫 번째)
- int LNext(List* plist, LData data); - 조회
- LData LRemove(List* plist); - 삭제
- int LCount(List* plist); - 데이터 수 검색

## Reference

- [생활코딩-배열](https://opentutorials.org/module/1335/8677)
- [초보몽키의 개발공부로그](https://wayhome25.github.io/cs/2017/04/17/cs-18-1/)
- [정보통신기술용어해설 ](http://www.ktword.co.kr/abbr_view.php?m_temp1=3979)

- 아텐츠 게임 아카데미 수업 자료



------

오류가 있으면 댓글로 알려주세요.

이 포스트는 비정기적으로 내용이 추가/수정/삭제 될 수 있습니다.
