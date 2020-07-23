---
layout: post
title: Python EulerProject-03
comments: true
tags: [jekyll, github, markdown]
categories: [ python ]
---

# EulerProject-04
___

### 세자리 수를 곱해 만들 수 있는 가장 큰 대칭수

> 앞에서부터 읽을 때나 뒤에서부터 읽을 때나 모양이 같은 수를 대칭수(palindrome)라고 부릅니다.
두 자리 수를 곱해 만들 수 있는 대칭수 중 가장 큰 수는 9009 (= 91 × 99) 입니다.
세 자리 수를 곱해 만들 수 있는 가장 큰 대칭수는 얼마입니까?

회문(palindrome)인지 판별할 수 있는지를 물어보는 문제였다. 추가적으로 세자리 수를 곱해 만들 수 있는 가장 큰 대칭수를 구한다는 조건이 있다.
코드는 다음과 같다.

```python
MAX = 1
for i in range(999,100,-1):
    for j in range(999,100,-1):
        list_pal = str(i * j)
        if(list_pal == list_pal[::-1] and int(list_pal) > MAX ):
            MAX = int(list_pal)
            print(MAX)
            continue
        else:
            continue
```
```
906609
```

조건에 세 자리 수를 곱하라는 요구에 따라 100~ 999 사이의 숫자를 이중for문으로 돌렸다. 이후에 곱해서 나온 값들을 str 타입으로 형변환을 해준뒤 python에서 제공하는 슬라이싱(Slicing) 활용하여 회문을 판별 후 크기의 대소를 확인 후 변수 MAX에 가장 큰 값을 넣어줬다. 그렇게 결과값이 출력된 후 종료된다.

회문판별 문제를 파이썬으로 접한건 처음인데, 좋은 메서드들을 활용했더니 쉽게 풀렸다. 다시 한번 C언어로 구현해봐야겠다고 느꼈다.
