---
layout: post
title: Python EulerProject-05
comments: true
tags: [jekyll, github, markdown]
categories: [ python ]
---

# EulerProject-05
___

### 1 ~ 20 사이의 어떤 수로도 나누어 떨어지는 가장 작은 수

> 1 ~ 10 사이의 어떤 수로도 나누어 떨어지는 가장 작은 수는 2520입니다.
그러면 1 ~ 20 사이의 어떤 수로도 나누어 떨어지는 가장 작은 수는 얼마입니까?

처음 문제를 보고 당황했지만 생각을 조금 해보니 바로 해결되었다.

```python
MIN_num = 2 * 3 *  5 * 7 * 11 * 13 * 17 * 19    # 1~ 20 사이의 소수의 곱
breaker = False # 이중 loop 탈출하기 위한 불리안 타입의 변수
while True:
    for i in range(1,21):
        if(MIN_num % i ==0 and i == 20):  # 소수의 곱이 1 ~ 20 사이의 수로 나뉘면 실행
            print(MIN_num)
            breaker = True
            break
        elif( MIN_num % i ==0):
            continue
        else:  # 나뉘지 않을 시 소수의 곱을 더함
            MIN_num = MIN_num + 2 * 3 *  5 * 7 * 11 * 13 * 17 * 19
            break
    if (breaker == True):
        break
```

```
232792560
```

소수의 곱으로는 모든 자연수를 만들 수 있다고 생각을 했고, 최소한의 소수의 곱을 미리 MIN_num 변수에 넣어줬다.
이후 MIN_num(소수의 곱) 이 1 ~ 20사이의 모든 자연수에 나누어 떨어지지 않을 시 MIN_num x= MIN_num 을 수행해준후 다시 루프로 돌아간다.
1 ~ 20 사이의 모든 자연수에 나누어 떨어지게 되면 Boolean 타입의 breaker 변수에 True 값은 주며 이중 루프를 탈출하며 끝난다.
