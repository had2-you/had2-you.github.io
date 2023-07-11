---
title: '백준 1546번 :: Array(배열)에 관하여'
layout: post
categories:
  - Swift-Study
tags:
  - Swift
comments: true
---

## 백준 1546번

<img src="/assets/img/boj1546.png"/>

<br>

#### 문제 요약 : 예제에서 제공하는 입력하는 n개의 점수들의 평균을 가지고 새로운 평균을 구하는 것

<br>

```swift
var M: Int = 0 // 최댓값
var N = Int(readLine()!)! // 과목 개수

var arrSub = readLine()!.split(separator: " ").map { Int(String($0))! }

```

변수 N에는 **과목의 개수**를, <br>
arrSub에 n개의 값을 입력 받아 **Int형 배열**로 받았다.

<br>

```swift
arrSub = arrSub.sorted(by: >)
M = arrSub[0]
```

최댓값을 지정해주기 위해 배열을 내림차순으로 정렬한 후, 0번째에 있는 배열을 가져와 변수 M에 대입했다.

<br>

```swift
var avg = Double(arrSub.reduce(0, +)) / Double(N)

var newAvg: Double = avg / Double(M) * 100
print(newAvg)
```

arrSub.reduce(0, +)은 현재 배열에 있는 값을 전부 더하라는 의미이다.<br>
이후 새로운 평균 공식을 대입해 출력해 주었다.

<br>
<hr>

## 추가로 궁금했던 것

#### <span style="color:red">고차함수 :: reduce</span>

<br>

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
