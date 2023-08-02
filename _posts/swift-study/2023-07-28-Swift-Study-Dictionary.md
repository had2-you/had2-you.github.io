---
title: '백준 1157번 :: Dictionary'
layout: post
categories:
  - Swift-Study
tags:
  - Swift
comments: true
---

## Dictionary

Type of Hashtable,

<br>

```swift
//Declaration
@frozen struct Dictionary<Key, Value> where Key : Hashable


//Usege
var responseMessages = [200: "OK",
                        403: "Access forbidden",
                        404: "File not found",
                        500: "Internal server error"]
```

## 백준 1157번

<img src="/assets/img/boj10818.png"/>

<br>

#### 문제 요약 : 가장 많이 사용된 알파벳 대소문자 구분 없이 찾아서 <u>대문자</u>로 출력하기

<br>

```swift
var n = Int(readLine()!)! // 개수
var arr = readLine()!.split(separator: " ").map { Int(String($0))! }

arr = arr.sorted()
print(arr[0], arr[n-1])
```

변수 n에는 **개수**를, arr에 n개의 값을 입력 받아 **Int형 배열**로 받았다.<br>
이후 arr을 sorted() 즉, <u>오름차순</u>으로 정렬하여<br>

#### 결과값으로 배열의 <u>첫번째</u>와 <u>마지막</u>을 출력하였다.

<br>
<hr>

## 추가로 궁금했던 것

#### sorted() 쓸 때 주의

```swift
arr = arr.sorted() → ⭕️
arr.sroted() → ❌

아랫줄의 코드를 실행하고자 할 경우 실행이 안됨.
⭐️ 배열을 다시 변수에 집어 넣어주어야 함 ⭐️
```
