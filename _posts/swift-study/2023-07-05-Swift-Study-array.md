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

#### <span style="color:red">reduce?</span> Returns the result of combining the elements of the sequence using the given closure.

<br>

```swift
func reduce<Result>(
    _ initialResult: Result,
    _ nextPartialResult: (Result, Self.Element) throws -> Result
) rethrows -> Result
```

initialResult : 초기값으로 사용될 값을 넣으면 클로저가 처음 실행될 때, nextPartialResult에 전달 <br>
nextPartialResult : 시퀀스의 각 요소들을 계산해 누적된 값 <br>
Return Value : 마지막에 누적된 값, 시퀀스에 요소가 없다면 initialResult 값을 반환 <br>

<br>

Expression(1)

```swift
// 각 요소의 합 구하기

let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
let sum = numbers.reduce(0, +)

print(sum)
// 55
```

<br>

Expression(2)

```swift
// 각 요소의 합 구하기

let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
let sum = numbers.reduce(0) { $0 + $1 }

print(sum)
// 55
```
