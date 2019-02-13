---
layout: post
title:  "Higher-Order Function"
date:   2018-08-03
author: Ted Kim
categories: Swift
tags:	FunctionalProgramming
cover:
---

# Higher-Order Function(HOF)

- accepts a function as an argument and/or returns a function.

  (a function is a first-class object, also known as a first-class citizen in Swift.)

<br/>

### Accepts a function as an argument

```Swift
func filter(_ isIncluded: (Element) throws -> Bool) rethrows -> [Element]
```

```Swift
let array = [1, 2, 3, 4, 5]

func isEven(_ i: Int) -> Bool {
    return i % 2 == 0
}
let evenNumbers = array.filter(isEven)
```

```Swift
let evenNUmbers = array.filter { $0 % 2 == 0 }
```

<br/>

### Retuns a Functions

```Swift
func multiply(_ a: Int) -> (Int) -> Int {
    return { b in
        return a * b
    }
}
let x5 = multiply(5)
let result = x5(20) // 100
```
