### 문제
- https://www.acmicpc.net/problem/15685

### 접근
- 처음에는 굉장히 어려워보였으나 요구사항만 잘 파악하고 구현하면 간단한 문제였다.
- 입력된 드래곤 커브 정보를 통해 모든 드래곤 커브들(위치로 표현)을 만들고, 만들어진 모든 드래곤 커브들의 모든 위치를 Hashset에 담는다.
- 그리고 100 x 100 매트릭스에 있는 정사각형들에 대해, 해당 정사각형의 모든 꼭짓점이 해당 HashSet에 담겨있는지 여부를 확인하는 방식으로 구현했다.
- HashSet을 사용한 이유는 contains() 메소드 사용시 O(1) 시간을 소요시키기 위해서이다.
- 드래곤 커브는 다음과 같이 만들었다.
  - 1 ~ g세대 까지 for문 안에서 다음의 로직을 수행한다.
    - 현재 드래곤 커브의 끝점으로부터 추가될 위치들의 offset을 구한다.
    - offset은 현재 드래곤 커브의 모양을 시계방향으로 90도 회전하므로,
    - 끝점을 제외한 현재 드래곤 커브에 있는 모든 점에 대해 현재 상태의 offset을 계산하고 해당 offset에 대해 row는 새로 추가될 점의 col로 계산하고 col은 새로 추가될 점의 row * (-1)로 계산한다.

### 생각해볼 점
- 문제가 어려워보인다고 쫄지 말자.