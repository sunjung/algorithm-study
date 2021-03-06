# 다이나믹 프로그래밍(동적 계획법)

## 소개
- 분할점령(Divide-and-Conquer)과 유사하게 원문제를 부분문제로 쪼개어 푸는 알고리즘 설계 기법
- 다이나믹 프로그래밍은 각 부분문제의 결과를 기억해 두었다가, 반복되는 부분문제의 결과를 다시 계산하지 않고 기억해 둔 결과를 사용하여 시간복잡도를 낮춘다.
- 주로 조합최적화 문제를 해결하는데 많이 사용된다.

## 최적의 원리
- 원문제의 최적해는 부분문제의 최적해 조합으로 얻을 수 있다.
- 원문제를 부분문제로 표현할 수 있는 점화식을 수립해야 한다.

## 구현방법

### Top-down
- 분할점령과 비슷하게, 재귀함수를 사용하여 부분문제로 나누어 풀며(분할점령), 각 부분문제의 결과를 메모리에 저장(memorization)해서 두 번 계산하지 않는다.
- 장점 : 구현이 간단하고 필요한 계산만 할 수 있다.
- 단점 : 콜스택으로 인한 오버헤드가 있다.

### Bottom-up
- 기저 케이스를 먼저 계산하고, 수립한 점화식을 바탕으로 기저 케이스를 원문제로 키워간다.
- 장점 : 콜스택으로 인한 오버헤드가 없다. 
- 단점 : 계산순서를 고려해야 하며,  원문제를 풀기 위해 필요없는 케이스까지 계산할 수 도 있다

## 동적계획법으로 푸는 대표적인 문제
### 0-1 배낭 문제(0-1 Knapsack problem)
- 입력 : 물건의 개수 n, 각 물건 무게 w_i와 가격 v_i, 배낭에 담을 수 있는 최대 무게 W (단, 물건은 최대 1개만 남을 수 있음)
- 출력 : W를 넘지 않는 선에서 총가격을 최대로하는 물건 조합 또는 총가격
- 참고 : http://hochulshin.com/01knapsack/

### 최장 공통 부분 수열 (Longest common subsequence)
- 입력 : 두 수열
- 출력 : 출력되는 수열은 두 수열에 공통으로 포함된 부분 수열 중 최장 수열 
- 참고 : http://hochulshin.com/longest-common-subsequence/

### 연쇄 행렬의 최적 곱셈 순서
- 가정 : (m by n) 행렬과 (n x l) 행렬의 곱셈에 O(mnl)의 곱셈이 필요하다.
- 입력 : 곱셈해야 되는 행렬 개수 N와 N개의 행렬
- 출력 : 곱셈을 최소로하는 행렬 곱의 순서와 최소화된 곱셈수
- 참고 : http://destiny738.tistory.com/209

### 그래프의 최단경로 문제(Dijkstra’s shortest path algorithm, Floyd-warshall algorithm)
- 참고 : https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm
         https://en.wikipedia.org/wiki/Floyd–Warshall_algorithm
