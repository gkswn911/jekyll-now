---
layout: post
title: Algorithm_BlackJack
comments: true
tags: [jekyll, github, markdown]
categories: [ Algorithm ]
---

# BaekJoon 2798 [BruteForce]
___

### 블랙잭

[BaekJoon2798](https://www.acmicpc.net/problem/2798)

블랙잭 알고리즘은 BruteForce유형의 문제중에서 가장 대표적인 문제라고 볼 수 있다.
위 링크에 문제와 입력 및 출력 예시가 있으니 참고하면 될 것 같다.
먼저 Python 코드다.

```python
#BlackJack - BaekJoon - 2798
N, M= input().split() # 3 <= n <= 100,  # 10 <= M <= 300,000
N = int(N) # 문자열 타입을 정수형으로 변환
M = int(M) # 각각 카드의 개수와 카드의 합을 입력받는다.

j_j = 0    #각 시작하는 index번호를 지정
y_y = 0
k_k = 0
list_num = []
temp = 0  # 각 카드의 합을 임시 버퍼로 저장
sum = 0   # M과 가장 가까우면서 temp보다 큰 값
list_num = [int(x) for x in input().strip().split()]
# for i in range(N):
#     list_num.append(int(input()))
for j in list_num[j_j:len(list_num)-2]:
    y_y = j_j + 1
    for y in list_num[y_y:len(list_num)-1]:
        k_k = y_y + 1
        for k in list_num[k_k+2:]:
            temp = j + y + k
            if(temp <= M and temp > sum ):
                sum = temp
    j_j = j_j + 1    
print(sum)      
```
더 간단하게 구현할 수 있었을 것 같아 생각을 계속 해봤는데 아직 더 좋은 아이디어가 생각나지 않았다...
 # for i in range(N):
 #     list_num.append(int(input()))
위와 같이 각각의 카드의 값들을 입력받으려고 했지만 백준에서 제공하는 예제와 어긋나는 바람에 다른 방식으로 입력 받았다.

C언어로는 아이디어가 바로 떠올랐는데, Python에서는 리스트에 인덱스 값에 접근하는 법을 잘 몰라서 시간이 오래 걸렸던 것 같다.

그래서 C언어로도 구현해봤다!

```c
#include <stdio.h>
#include <stdlib.h>
int main() {
	int N, M, temp, sum = 0;
	scanf("%d %d", &N, &M);

	int* list_num = malloc(sizeof(int) * N);  // 카드 개수 N 만큼 할당
	for (int i = 0; i < N; i++)
		scanf_s("%d", &list_num[i]);

	// Burte Force 시작
	for (int i = 0; i < N - 2; i++) {
		for (int j = i + 1; j < N - 1; j++) {
			for (int k = j + 1; k < N; k++) {
				temp = list_num[i] + list_num[j] + list_num[k];
				if (temp <= M && temp > sum) {
					sum = temp;
				}
			}
		}
	}
	printf("%d", sum);
	free(list_num);
	return 0;
}
```
