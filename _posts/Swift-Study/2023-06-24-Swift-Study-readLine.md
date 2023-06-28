---
title: '사용자에게 값 입력받기 :: readLine() & Unwrapping'
layout: post
categories:
  - Swift-Study
tags:
  - Swift
comments: true
---

## 사용자에게 Int 타입 입력받는 방법

<br>

#### 강제언래핑을 하지 않는다면 이렇게 한다.

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

**⚠️ 하지만 readLine을 할 때는 이렇게 쓰지 않음**

<br>

#### <span style="color:red">강제 언래핑</span>을 사용할 때

```swift
let num = Int(readLine()!)!
```

<br>
<hr>

## 공백단위로 입력받기

공백단위로 입력받기는 split()을 이용한다.

```swift
let input = input.split(separator: " ")
```

" "를 기준으로 배열(array)을 만들어준다. 하지만 결과 값은 Array<Substring>형이 된다.
<br>

만약 Substring 형이 아닌 Stirng형으로 쓰려면 split()이 아닌 components()를 쓴다.

```swift
let input = input.components(separatedBy: " ")
```

<br>

그럼 <span style="color:red">정수를 여러 개</span>입력받으려면?

```swift
let num = readLine()!.split(separator: " ").map { Int(String($0))! }
```

위 split을 사용한 것에서 map()을 추가한 것 <br>
Substring을 Int형으로 바꿔준다는 의미이다. <br>
Int($0)! 보다 Int(String($0))!의 **속도가 조금 더 빠르다.**

<br>
<hr>

## 추가로 궁금했던 것

⭐️ readLine()으로 값을 불러올 때 왜 **guard let**을 사용해야해?

    readLine()함수의 반환 타입은 '옵셔널 String'으로 반환한다.
    즉, guard let과 같은 방식을 통해 옵셔널을 벗겨주어야 한다.

<br>

⭐️ 그렇다면 왜 readLine()함수는 **옵셔널 String**으로 반환해?

    사용자가 값을 입력하지 않을 수도 있기 때문이다.
    따라서 입력의 유무를 확인하고, 입력값이 있을 경우에만 올바른 처리를 하는 것을 목표로 한다.

<br>

⭐️ split() vs compnents() 차이점?

    split은 swifts stndard library에 포함되어 있고
    compnents는 Foundation 프레임워크에 포함되어 있다.
    → import Foundation을 꼭 해줘야 한다는 의미
