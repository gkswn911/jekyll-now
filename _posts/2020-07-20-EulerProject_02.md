---
layout: post
title: Python EulerProject-02
comments: true
tags: [jekyll, github, markdown]
categories: [ python ]
---

# EulerProject-02

___

### 피보나치 수열에서 4백만 이하이면서 짝수인 항의 합

> 피보나치 수열의 각 항은 바로 앞의 항 두 개를 더한 것이 됩니다. 1과 2로 시작하는 경우 이 수열은 아래와 같습니다.
1, 2, 3, 5, 8, 13, 21, 34, 55, 89, ...
짝수이면서 4백만 이하인 모든 항을 더하면 얼마가 됩니까?

```python
i = 0
NUM = 4000000
list_pi = [ 1, 2]  # 최초 피보나치 배열
sum = 0  # 최종 합계
temp = 0 # 현재 i가 가리키고 있는 값
while True:
    i = i + 1
    temp = list_pi[i-1] + list_pi[i]
    if (temp > NUM ):
        break
    else:
        list_pi.append(temp)
for i in list_pi:
    if ( i % 2 == 0):
        sum = sum + i
    else:
        continue    
print(sum)
```
```
4613732
```

다음과 같이 정답이 나왔다. 최초 리스트에 1, 2를 넣어서 시작했다. 이후 NUM보다 큰 값이 나올때까지 append를 해서 첫번째 조건을 만족시킨후, 마지막에는 짝수인 값들만 변수 sum에서 더하기 연산을 실행해주며 두번째 조건을 만족시키며 결과값이 출력된 후 종료된다. 
