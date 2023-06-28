---
description: Conditionals & Logic
---

# 條件判斷

## if條件判斷 if Statement

如果 `if` 之後的條件成立(true)，`if` 所包含的程式碼區塊便會被執行

反之如果 `if` 之後的條件不成立(false)，`if` 所包含的程式碼區塊便不會被執行

```swift
var halloween = true

if halloween {
  print("Trick or treat!")
}
```

輸出：

> Trick or treat!

### 例外條件判斷 else Statement

`else` 是 `if` 的好夥伴，當 `if` 不成立時，`else` 所包含的程式碼區塊便會被執行

```swift
var turbulence = false 

if turbulence {
  print("Please stay seated.")
} else {
  print("You may freely move around.")
}
```

輸出：

> You may freely move around.

### 多重條件判斷 else if Statement

`else if` 提供了額外的判斷條件，`else if` 只能放在 `if` 的後面以及 `else` 之前

```swift
var weather = "rainy" 

if weather == "sunny" {
  print("Grab some sunscreen")
} else if weather == "rainy" {
  print("Grab an umbrella")
} else if weather == "snowing" {
  print("Wear your snow boots")
} else {
  print("Invalid weather")
}
```

輸出：

> Grab an umbrella

## 比較運算子 Comparison Operators

Swift 可用的比較運算子有：

1. 小於 `<`
2. 大於 `>`
3. 小於或等於 `<=`
4. 大於或等於 `>=`
5. 等於 `==`
6. 不等於 `!=`

比較運算子會回傳布林值(Bool)

```swift
print(5 > 1)
print(6 < 10)
print(2 >= 3)
print(3 <= 5)
print("A" == "a")
print("B" != "b")
```

輸出：

> true
>
> true
>
> false
>
> true
>
> false
>
> true

## 三元運算子 Ternary Conditional Operator

算是一種更簡潔的 `if...else` 條件判斷

如果 `?` 之後的條件成立(true)，`?` 之後 `:` 所包含的程式碼區塊便會被執行

當 `?` 不成立時，`:` 之後的程式碼區塊便會被執行

```swift
var driverLicense = true

driverLicense ? print("Driver's Seat") : print("Passenger's Seat")
```

輸出：

> Driver's Seat

{% hint style="info" %}
如果 if...else 內的處理很簡單具有共同性，例如只是宣告或回傳某值，就可以使用三元運算子
{% endhint %}

## switch條件判斷 switch Statement

如果 `switch` 後面的變數的值符合其中一個 `case` 的值，那塊 `case` 所包含的程式碼區塊便會被執行

當所有 `case` 都不成立時，`default` 所包含的程式碼區塊便會被執行

定義 `case` 程式碼區塊要使用 `:`

```swift
var secondaryColor = "green"

switch secondaryColor {
  case "orange":
    print("Mix of red and yellow")
  case "green":
    print("Mix of blue and yellow")
  case "purple":
    print("Mix of red and blue") 
  default: 
    print("This might not be a secondary color.") 
}
```

輸出：

> Mix of blue and yellow

### 區間條件判斷 Interval Matching

`case` 的條件也可以給一個區間(range of value)

```swift
let year = 1905
var artPeriod: String

switch year {
  case 1860...1885:
    artPeriod = "Impressionism"
  case 1886...1910:
    artPeriod = "Post Impressionism"
  case 1912...1935: 
    artPeriod = "Expressionism"
  default:  
    artPeriod = "Unknown"
}
print(artPeriod)
```

輸出：

> Post Impressionism

### 複合條件判斷 Compound Cases

`case` 的條件也可以給一個以上的值

```swift
let service = "Seamless"

switch service {
  case "Uber", "Lyft":
    print("Travel")
  case "DoorDash", "Seamless", "GrubHub":
    print("Restaurant delivery")
  case "Instacart", "FreshDirect":
    print("Grocery delivery")
  default: 
    print("Unknown service")
}
```

輸出：

> Restaurant delivery

### where 查詢子句 where Clause

`case` 的條件也可以給一個 `where` 查詢子句來判斷變數的值有沒有符合描述

```swift
let num = 7

switch num {
  case let x where x % 2 == 0:
    print("\(num) is even")
  case let x where x % 2 == 1:
    print("\(num) is odd")
  default:
    print("\(num) is invalid")
}
```

輸出：

> 7 is odd

{% hint style="info" %}
where 查詢子句有點像數學中的描述法

```swift
// where 查詢子句
x where x % 2 == 0

// 描述法
{ x | x 除以 2 的餘數為 0 }
```
{% endhint %}

## 邏輯運算子 Logical Operator

Swift 可用的邏輯運算子有：

1. 邏輯NOT運算子 `!`
2. 邏輯AND運算子 `&&`
3. 邏輯OR運算子 `||`

邏輯運算子會回傳一個布林值(Bool)

```swift
!true           // false
!false          // true

true && true    // true
true && false   // false 
false && true   // false 
false && false  // false

true || true    // true
true || false   // true
false || true   // true 
false || false  // false
```

### 邏輯運算子的結合使用 Combining Logical Operators

在同一行程式碼中使用一個以上的邏輯運算子時，會從左至右依序判斷

```swift
!false && true || false  // true
false || true && false   // false
```

{% hint style="info" %}
上面的結果跟你想的有一樣嗎？
{% endhint %}

### 控制邏輯判斷的優先順序 Controlling Order of Execution <a href="#heading-controlling-order-of-execution" id="heading-controlling-order-of-execution"></a>

在結合使用邏輯運算子時，可以再想要優先判斷的邏輯表達式用 `()` 包起來

```swift
true || true && false || false      // true 
(true || true) && (false || false)  // false 
```
