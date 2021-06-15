# Data Structure Study
> 자료구조에 대해 공부한 내용을 정리하는 Repository입니다.

# 목차

- [Hash](#Hash)
- [Tree](#Tree)
- [Heap](#Heap)

## Hash

- 개념
  - Hashing : 임의의 길이의 값을 해시함수를 사용하여 고정된 크기의 값으로 변환하는 작업
  - Hash Table : 해시함수를 사용하여 변환한 값을 Index으로 삼아 Key와 Value를 저장하는 자료구조

- Hash Function
  - ① Division Method : 테이블 크기로 나머지 연산 ((Key % 소수) % 테이블 크기)
  - ② Digit Folding : Key가 String일때, 모든 ASCII 코드를 더한 값을 Index으로 사용
  - ③ Universal Hashing : p(f(x) == f(y)) == 1/m가 되는 hash 함수 (c/m이 되면, C-universal Hashing)
 
- Collision
  - 개념 : 해시 함수가 서로 다른 두 개의 입력값에 대해 동일한 출력값을 내는 상황

- Collision resolution method
  - ① Open Addressing : Collision시, 다른 주소도 이용할 수 있는 기법
    - ⓐ Linear Probing : 한 칸씩 이동하며 빈 칸을 찾음 (클러스터링 문제가 일어남)
    - ⓑ Quadratic Probing : n^2칸씩 이동하며 빈 칸을 찾음 (Linear보다는 낫지만, 클러스터링 문제가 일어남)
    - ⓒ Double Probing : 두가지 해시 함수를 사용하며, 첫 번째 해시 함수는 Index를 찾고, 두 번째 해시 함수는 이동폭 계산
  - ② Chaining : Collision시, 연결리스트 형태로 저장하는 방법(Bucket)

- 시간복잡도
  - Insert, Search, Delete : O(1) (다만, Load Factor(K/N, 적재량)이 50% 이하이고, C-Universal Hashing 함수를 사용할 경우)
 
## Tree

- 개념
  - 사이클이 없는 무방향 그래프
  - 계층적인 구조를 표현할 때 사용하는 자료구조

- 특징
  - 어떤 두 노드를 선택해도 둘 사이에 경로가 항상 하나만 존재
  - 트리 크기가 N일 때, 전체 간선의 수는 N-1

- 관련 용어
  - 루트 노드 (Root node) : 부모가 없는 최상위 노드
  - 단말 노드 (Leaf node) : 자식이 없는 노드
  - 크기 (Size) : 트리에 포함된 모든 노드의 개수
  - 깊이 (Depth) : 루드 노드까지의 거리
  - 높이 (Height) : 깊이 중 최댓값
  - 차수 (Degree) : 각 노드의 (자식 방향) 간선 개수

- 트리 순회
  - 전위 순회 (Pre order traversal) : 루트->왼쪽->오른쪽 방문
  - 중위 순회 (In order traversal) : 왼쪽->루트->오른쪽 방문
  - 후위 순회 (Post order traversal) : 왼쪽->오른쪽->루트 방문

### 이진 탐색 트리 (Binary Search Tree)

- 개념
  - 이진 탐색이 동작할 수 있도록 고안된 자료구조

- 특징
  - 노드의 값 : 왼쪽 자식 노드 < 부모 노드 < 오른쪽 자식 노드

### 완전 이진 트리 (Complete Binary Tree)

- 개념
  - 루트 노드부터 시작하여 왼쪽 자식 노드에서 오른쪽 자식 노드 순서대로 데이터가 차례대로 삽입되는 트리

## Heap

- 개념
  - 완전 이진 트리의 일종
  - 여러 개의 값들 중 최댓값, 최솟값을 빠르게 찾아내도록 만들어진 자료구조
  - 느슨한 정렬 상태를 유지
  - 항상 루트 노드를 제거

- 종류
  - 최소 힙(min heap)
    - 루트 노드가 가장 작은 값
  - 최대 힙(max heap)
    - 루트 노드가 가장 큰 값
 
- 삽입 원리(min heap 기준)
  - ① 부모 노드와 자신의 값을 비교
  - ② 부모 노드보다 자신이 더 작다면, 부모 노드와 스위칭
  - ③ 더 이상 스위칭할 수 없을 때까지 ①~② 반복(루트 노드가 되거나 부모 노드가 자신보다 더 작을 때까지)

- 삭제 원리(min heap 기준)
  - ① 루트 노드 제거
  - ② 자식 노드 중에 자신 보다 작은 노드와 스위칭 (만약 두 자식 모두 작다면, 더 작은 노드 선택)
  - ③ 더 이상 스위칭할 수 없을 때까지 반복

- 시간 복잡도
  - 삽입, 삭제 : O(logN) (완전 이진 트리에서 부모와의 비교가 전부이므로, 한번의 비교에 반이 줄어듬)
 
