# 미션 1. 재귀함수 격자 경로 탐색
다음 C언어 코드는 2차원 좌표 평면에서 특정 지점까지 최단 거리로 이동하는 경우의 수를 구하는 로직이다. path(2, 2)를 호출했을 때의 반환값을 구하시오.

```c
int path(int x, int y) {
    if (x == 0 || y == 0) return 1;
    return path(x - 1, y) + path(x, y - 1);
}

```
<br>


# 미션 2. 비대칭 트리 순회
다음 C언어 함수 traverse(5)를 실행했을 때 화면에 출력되는 결과를 순서대로 적으시오. ASCII 코드 48은 숫자 0 문자를 의미한다.

```c
#include <stdio.h>

void traverse(int n) {
    if (n <= 0) return;
    traverse(n - 2);
    traverse(n - 3);
    putchar(n + 48);
}

```
<br>

# 미션 3. 2차원 배열 방향 벡터 시뮬레이션
다음 C언어 코드는 4x4 배열에서 경계선에 닿으면 방향을 90도 전환하며 숫자를 채우는 로직이다. for문이 모두 종료된 후 grid[1][3]에 저장되어 있는 값을 구하시오.

```c
int grid[4][4] = {0};
int x = 0, y = 0;
int dx[4] = {0, 1, 0, -1};
int dy[4] = {1, 0, -1, 0};
int dir = 0;

for (int i = 1; i <= 5; i++) {
    grid[x][y] = i;
    int nx = x + dx[dir];
    int ny = y + dy[dir];

    if (nx < 0 || nx >= 4 || ny < 0 || ny >= 4) {
        dir = (dir + 1) % 4;
        nx = x + dx[dir];
        ny = y + dy[dir];
    }
    x = nx;
    y = ny;
}

```

