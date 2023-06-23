---
title: '사용자에게 값 입력받기 :: readLine()'
layout: post
categories:
  - Swift-Study
tags:
  - Swift
comments: true
---

> ## 사용자에게 Int 타입 입력받는 방법

<br>

```swift
func getNumber() -> Int {
    guard let numString = readLine(),
          let num = Int(numString) else {
        print("optional error")
        return -1 // guard let 실패 시 error 반환
    }
    return num // 성공 시 num 리턴
}
```

<br>

중간에 쉼표(,)를 통해 바인딩을 동시에 사용한다. guard문에서는 **','**를 이용하면 바인딩 조건 여러 개를 나열할 수 있다.

따라서<br>
<span style="color:red">**첫 번째**</span> 바인딩 조건은 numString에 readLine으로부터 입력받은 값을 할당하고, <br>
<span style="color:red">**두 번째**</span> 바인딩 조건은 numString에 담긴 값을 Int타입으로 강제형변환 하여 num에 할당한다.
<br>
모든 조건이 만족될 시 num을 반환한다.

<br><br>

> ## 추가로 궁금했던 것

⭐️ readLine()으로 값을 불러올 때 왜 **guard let**을 사용해야해?

    readLine()함수의 반환 타입은 '옵셔널 String'으로 반환한다.
    즉, guard let과 같은 방식을 통해 옵셔널을 벗겨주어야 한다.

<br>

⭐️ 그렇다면 왜 readLine()함수는 **옵셔널 String**으로 반환해?

    사용자가 값을 입력하지 않을 수도 있기 때문이다.
    따라서 입력의 유무를 확인하고, 입력값이 있을 경우에만 올바른 처리를 하는 것을 목표로 한다.
