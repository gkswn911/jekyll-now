---
layout: post
title: Python EulerProject-01
comments: true
tags: [jekyll, github, markdown]
categories: [ python ]
---

# EulerProject-01

___

### 1000보다 작은 자연수 중에서 3 또는 5의 배수를 모두 더하면?

> 10보다 작은 자연수 중에서 3 또는 5의 배수는 3, 5, 6, 9 이고, 이것을 모두 더하면 23입니다.
1000보다 작은 자연수 중에서 3 또는 5의 배수를 모두 더하면 얼마일까요?

```python
sum = 0
for i in range(3,1000):
    if ( i % 3 ==0 or i % 5 == 0):
        sum = sum + i
    else:
        continue
print(sum)
```

```
233168
```

다음과 같이 결과가 나왔다. 어려운 부분이 없기 때문에 설명은 생략한다.
