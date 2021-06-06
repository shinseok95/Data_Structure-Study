# Data Structure Study
> 자료구조에 대해 공부한 내용을 정리하는 Repository입니다.

# 목차

- [Tree](#Tree)
- [Heap](#Heap)

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
 
