# Data Structure(자료구조)

<br>

## Array vs LinkedList

### 저장방식
* Array의 element(원소)들은 **인접한 memory위치에 저장**
* LinkedList의 element(원소)들은 **memory 어딘가에 저장**

### 크기
* Array의 size는 **반드시 array 선언 시점에 지정**
* LinkedList의 size는 **다양할 수 있음**

### 메모리 할당
* Array에서, memory는 Array가 **선언되자 마자 Compile time에 할당**
* LinkedList에서, memory는 **새로운 node가 추가될 때 runtime에 할당**

### 요소 접근
* Array는 **Random Access**를 지원
  특정 element에 접근하는 시간 복잡도는 O(1)이다.
* LinkedList는 **Sequential Access**를 지원
  특정 element에 접근하는 시간 복잡도는 O(N)이다.

### 삽입 및 삭제
* Array는 인덱스로 접근 후 삽입 및 삭제O(1) + 전체 배열 요소를 하나씩 Shift O(N)
* LinkedList는 삽입하려는 위치 접근 후 삽입 및 삭제O(N)
  만약 맨 앞과 뒤에 삽입 및 삭제하려면 O(1)

### 결론
Array는 **데이터 접근**이 주 업무일 경우 사용,
LinkedList는 **데이터 수정**이 주 업무일 경우 사용


* * *
<br>

## Stack and Queue

### Stack(스택) 이란?
* 스택(Stack) 자료구조는 책을 쌓는 것처럼 차곡차곡 쌓아 올린 형태의 자료구조를 의미한다.
* LIFO(후입선출) 방식의 자료구조이다.

### Stack의 특징
* 스택 내부 데이터는 top를 통해서만 접근할 수 있다. (top는 가장 마지막(최근)에 들어온 자료)
* 스택에 데이터를 삽일할 때는, top위에 쌓는다. (`push`연산)
* 스택에 데이터를 삭제할 때는, top에 위치한 데이터를 삭제한다. (`pop`연산)
* 스택은 **시간 순서**에 따라 데이터가 쌓이게 되므로 가장 마지막에 삽입된 데이터가 가장 먼저 삭제된다.

### Stack활용 예시
* 실행 취소(undo) - 가장 마지막에 실행된 것부터 실행을 취소한다.
* 웹 브라우저(뒤로가기) - 가장 마지막에 열린 페이지부터 돌아간다.
* 역순 문자열 만들기 - 가장 마지막에 입력된 문자부터 출력한다.
* 수식의 괄호검사 - 연산자 우선순위 표현을 위한 괄호 검사
<br>

### Queue(큐) 란?
* 큐(Queue) 자료구조는 먼저 들어온게 먼저 나가는 FIFO(선입선출)방식의 자료구조를 의미한다.

### Queue의 특징
* 큐는 삽입, 삭제가 다른 방향에서 이루어진다.
* 삽입 연산만 수행되는 곳을 리어(rear)라고 하며, 삭제 연산만 수행되는 곳을 프론트(front)라고 한다.
* 리어(rear)에서 이루어지는 삽입 연산을 인큐(enQueue)라고 하며, 프론트(front)에서 이루어지는 삭제 연산을 디큐(dnQueue)라고 한다.
* 큐는 **가장 먼저 삽입된 데이터가 가장 먼저 삭제**된다.

### Queue활용 예시
* 은행 업무
* 콜센터 고객 대기시간
* 놀이동산 순서
* 프로세스 관리
* 너비 우선 탐색(BFS, Breadth-First Search) 구현
* 캐시(Cache) 구현

* * *
<br>

## Tree

### Tree(트리) 란?
* Stack(스택)이나 Queue(큐)와 같은 선형 구조가 아닌 **비선형 구조**이다.
* 트리는 계층적 관계(Hierarchical Relationshhip)를 표현한다.

### 트리 용어
* Node(노드) : 트리를 구성하고 있는 각각의 요소를 의미한다.
* Edge(간선) : 트리를 구성하고 노드와 노드 사이의 연결하는 선을 의미한다.
* Root Node(루트 노드) : 트리 구조에서 최상위에 있는 노드를 의미한다.
* Terminal Node(= leaf Node, 단말 노드) : 하위에 다른 노드가 연결되어 있지 않은 노드를 의미한다.
* Internal Node (내부노드, 비단말 노드) : 단말 노드를 제외한 모든 노드로 루트 노드를 포함한다.


<br>

### Red Black Tree

## RBT
* RBT(Red Black Tree)는 BST를 기반으로 하는 트리형식의 자료구조이다.
* Search,Insert,Delete에 0`(log n)`의 시간 복잡도가 소요된다.
* 동일한 노드의 개수일 때, hight를 최소화 하여 시간 복잡도를 줄이는 것이 핵심 아이디어이다.
* 동일한 노드의 개수일 때, hight가 최소가 되는 경우는 트리가 complete binary tree인 경우이다.

이진 트리에서 Inorder Traversal(중위순회)시에 오름차순으로 순회가 되는 구간이 존재 할경우 또는 그 구간이 상당이 길어지게 
되면 BST의 경우 일렬로 길게 오른쪽으로 한 없이 길어지게 되는 트리의 모양을 하게 된다 그렇게 되면 최악의 경우는 O(hight) 높이 
만큼의 시간복잡도를 가진다. 하지만 RBT의 경우는 `Balanced BST`이므로 균형을 이루면서 BST의 성질을 가진다.
이때 삽입 시에 삭제 시의 조건이 RBT를 Balanced 하게 유지하는 규칙이 몇가지 존재한다.
