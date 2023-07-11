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

### 參數名稱縮寫

定義閉包時可以省略參數、回傳值，用縮寫 `$` 替代

`$0` 代表第一個參數，`$1` 代表第二個參數，以此類推

```swift
func combine(_ a: Int, _ b: Int, using combiner: (Int, Int) -> Int) -> Int {
  return combiner(a,b)
}

let sum = combine(2,5) { $0 + $1 }

print(sum)
```

輸出：

> 7

### @escaping

如果想讓參數有閉包的函式在宣告完還能被呼叫，要在閉包前面加上 `@escaping`

```swift
struct TextSaver {
  var saveAction: (String) -> Void = { print("Saving '\($0)' to disk") }

  mutating func setSaveAction(to newAction: @escaping (String) -> Void) {
    saveAction = newAction
  }
}

var saver = TextSaver()
saver.saveAction("Hello World!") 
saver.setSaveAction(to: { print("Saving '\($0)' to the cloud") })
saver.saveAction("Hello World!") 
```

輸出：

> Saving 'Hello World!' to disk
>
> Saving 'Hello World!' to the cloud

### 捕捉值

閉包會持續捕捉並更新外部變數的值

```swift
func makeCountingPrinter(for str: String) -> () -> Void {
  var printCount = 0
  func strPrinter() -> Void {
    printCount += 1
    print("\(str) print count: \(printCount)")
  }
  return strPrinter
}

let printHello = makeCountingPrinter(for: "Hello!")
let printGoodbye = makeCountingPrinter(for: "Goodbye!")

printHello()
printHello()
printGoodbye()
printHello()
printGoodbye()
```

輸出：

> Hello! print count: 1
>
> Hello! print count: 2
>
> Goodbye! print count: 1
>
> Hello! print count: 3
>
> Goodbye! print count: 2

***

## 常見的高階函式

Swift 常見的高階函式有：

* `filter`
* `map`
* `reduce`&#x20;
* `sorted`

```swift
let scores = [4,10,3,7,5]

let evenScores = scores.filter { $0 % 2 == 0 }
print(evenScores) 
let doubledScores = scores.map { $0 * 2 }
print(doubledScores) 
let sumOfScores = scores.reduce(0) { $0 + $1 }
print(sumOfScores)
let sortedScores = scores.sorted { $0 < $1 }
print(sortedScores)
```

輸出：

> \[4,10]
>
> \[8, 20, 6, 14, 10]
>
> 29
>
> \[3, 4, 5, 7, 10]
