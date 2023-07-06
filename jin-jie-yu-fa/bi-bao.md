# 閉包

## 閉包

閉包就像一個封閉的、有函式功能的一個變數，用 `let` 宣告一個閉包

```swift
let displayWelcome = { () -> Void in
  print("Hello World!")
}

displayWelcome()
```

輸出：

> Hello World!

### 參數與回傳值

閉包和函式一樣有可以有參數與回傳值

和函式不同的是傳入參數時不能加上參數名稱，只能傳入值

```swift
let multiply = { (a: Int, b: Int) -> Int in
  return a * b
}

print(multiply(4,3))
```

輸出：

> 12

### 將閉包傳入函式

函式傳入的參數可以是一個閉包

```swift
func combine(_ a: Int, _ b: Int, using combiner: (Int, Int) -> Int) -> Int {
  return combiner(a,b)
}

let add = { (a: Int, b: Int) -> Int in
  return a + b
}

let multiply = { (a: Int, b: Int) -> Int in
  return a * b
}

print(combine(2,5, using: add))
print(combine(2,5, using: multiply))
```

輸出：

> 7
>
> 10

### 尾隨閉包

如果函式最後一個參數是閉包，可以在呼叫函式的同時，在最後定義閉包並省略參數名稱

```swift
func combine(_ a: Int, _ b: Int, using combiner: (Int, Int) -> Int) -> Int {
  return combiner(a,b)
}

let sum = combine(2,5) { (a: Int, b: Int) -> Int in
  return a + b
}

print(sum)
```

輸出：

> 7
