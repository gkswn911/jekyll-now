---
layout: post
title: Python & Ruby 문자열 - 01
comments: true
tags: [jekyll, github, markdown]
categories: [ python ]
---

# Python & Ruby 문자열

___

AI 공부를 시작함에 있어서 Python을 기반으로한 Tensorflow 와 Keras를 제대로 이해하기 위해

Python 과 공통점을 지닌 Ruby를 기초부터 심화단계까지 공부하려고 한다.

첫 출발선은 문자열로 정했다.





---

## 문자열이란

>String(문자열)로 표현되며, 다수의 문자들이 열을 지어 만들어진 줄을 문자열이라고 부른다. 예를 들어 '한글' 이라는 단어를 문자열로 본다면 문자열의 시작지점과 끝 지점에 따옴표(") 를 표시해 구분할 수 있다.



```python
print('Hello')
print("Hello")
print("Hello 'world'")
print('Hello "world"')
```

```
Hello
Hello
Hello 'world'
Hello "world"
```

아래는 Ruby의 실행화면이다.

```ruby
puts('Hello')
puts("Hello")
puts("Hello 'world'")
puts('Hello "world"')
```

```
Hello
Hello
Hello 'world'
Hello "world"
```

Ruby와 Python의 실행결과가 같다는 것을 확인할 수 있다.

그렇다면 다음과 같은 코드는 실행결과가 어떻게 될까?

```python
print("Hello world')
```

바로 <u>SyntaxError: EOL while scanning string literal</u> 와 같은 에러가 발생한다. 위와 같은 에러 메시지는 프로그램의 구문이 잘못 쓰였을 때 발생한다. 즉 따옴표를 제대로 여닫지 않았을 때 발생하는 에러이니, 위와 같은 에러 메시지가 출력 될 경우 괄호 여닫기 혹은 따옴표, 철자 등을 확인하면 된다.

앞서 말했듯이 문자열의 시작지점이 큰 따옴표(") 로 시작하면 마지막 지점도 큰 따옴표로 동일하게 작성해야하고, 작은 따옴표도 위 와 같은 방식으로 작성해야 에러가 발생하지 않는다.

이 외에도 문자열의 제어, 특수문자, 데이터 형 등의 심화내용이 있다. 이 내용들은 추후에 사용될 상황이 생기면 그 때 다시 다루도록 하겠다.
