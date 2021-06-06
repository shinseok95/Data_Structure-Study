# Data Structure Study
> 자료구조에 대해 공부한 내용을 정리하는 Repository입니다.

# 목차

- [Tree](#Tree)
- [Heap](#Heap)

## Tree

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
 
