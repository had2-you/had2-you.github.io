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

Type of Hash table

<br>

```swift
//Declaration
@frozen struct Dictionary<Key, Value> where Key : Hashable

//Usege
var responseMessages = [200: "OK",
                        403: "Access forbidden",
                        404: "File not found",
                        500: "Internal server error"]
// [Int(Key type): String(Value Type)]


//Empty Dictionary
var emptyDict: [String: String] = [:]

```

key-value pairs seperated with **a comma** <Br>
**a colon** separates each key from its associated value<br>
surrounded by **square brackets**. <br>

<br>

```Swift
let httpResponseCodes = [200, 403, 301]
for code in httpResponseCodes {
    if let message = responseMessages[code] {
        print("Response \(code): \(message)")
    } else {
        print("Unknown response \(code)")
    }
}
// Prints "Response 200: OK"
// Prints "Response 403: Access forbidden"
// Prints "Unknown response 301"
```

**Bind the wrapped value of an Optional** which are guard let, if let so on, because It's subscripting

<br>

```swift
responseMessages[404] = "Not found"
responseMessages[500] = nil
```

You can modifiy, update, or remove keys and values.<br>
If assign nil to an existing key, the key and its associated value **are removed.**(Didn't print it.) <br>

<br>

```swift
let glyphIndex = imagePaths.firstIndex(where: { $0.value.hasPrefix("/glyphs") })
if let index = glyphIndex {
    print("The '\(imagePaths[index].key)' image is a glyph.")
} else {
    print("No glyphs found!")
}
// Prints "The 'star' image is a glyph.")

print(imagePaths[glyphIndex!])
// Prints "(key: "star", value: "/glyphs/star.png")"
```

You **can search a dictionary’s contents for a particular value** <br>
using the <u>contains(where:) or firstIndex(where:)</u> methods supplied by default implementation. <br>

The reason why I need a force unwrapping is its return type whichi is

```Swift
// Declaration
func firstIndex(where predicate: (Self.Element) throws -> Bool) rethrows -> Self.Index?
```

<br>

## 백준 1157번

<img src="/assets/img/boj1157.png"/>

<br>

#### Problem Summary : Find the most frequently used alphabet case-insensitively and display it in <u>uppercase</u>.

<br>

```swift
import Foundation

let word = readLine()!.uppercased()
var dict: [String:Int] = [:]
var result: [String] = []

for i in word {
    if dict[String(i)] == nil {
        dict[String(i)] = 1
    } else {
        dict[String(i)]! += 1
    }
}

// print(dict) → ["S": 4, "M": 1, "P": 1, "I": 4]

for key in dict.keys {
    if dict.values.max() == dict[key] {
        result.append(key)
    }
}

print(result.count > 1 ? "?":"\(result[0])")
```

⭐️ Difference between **dict.keys** and **dict[key]** in dictionary<br>
**dict.keys** gives you a collection of all keys in the dictionary,<br>
while **dict[key]** allows you to fetch the value associated with specific key.<br>

<br>

## Reference <Br>

https://developer.apple.com/documentation/swift/dictionary
