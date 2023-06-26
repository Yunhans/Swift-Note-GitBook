---
description: Conditionals & Logic
---

# 條件判斷

## if條件判斷 if...else Statement

如果 `if` 之後的條件成立(true)，`if` 所包含的程式碼區塊便會被執行

反之如果 `if` 之後的條件不成立(false)，`if` 所包含的程式碼區塊便不會被執行

{% code lineNumbers="true" %}
```swift
var halloween = true

if halloween {
  print("Trick or treat!")
}
```
{% endcode %}

輸出：

> Trick or treat!

`else` 是 `if` 的好夥伴，當 `if` 不成立時，`else` 所包含的程式碼區塊便會被執行

{% code lineNumbers="true" %}
```swift
var turbulence = false 

if turbulence {
  print("Please stay seated.")
} else {
  print("You may freely move around.")
}
```
{% endcode %}

輸出：

> You may freely move around.

## 多重條件判斷 else if Statement

`else if` 提供了額外的判斷條件，`else if` 只能放在 `if` 的後面以及 `else` 之前

{% code lineNumbers="true" %}
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
{% endcode %}

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

{% code lineNumbers="true" %}
```swift
print(5 > 1)
print(6 < 10)
print(2 >= 3)
print(3 <= 5)
print("A" == "a")
print("B" != "b")
```
{% endcode %}

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

{% code lineNumbers="true" %}
```swift
var driverLicense = true

driverLicense ? print("Driver's Seat") : print("Passenger's Seat")
```
{% endcode %}

輸出：

> Driver's Seat

{% hint style="info" %}
如果 if...else 內的處理很簡單具有共同性，例如只是宣告或回傳某值，就可以使用三元運算子
{% endhint %}

## switch條件判斷 switch Statement

如果 `switch` 後面的變數的值符合其中一個 `case` 的值，那塊 `case` 所包含的程式碼區塊便會被執行

當所有 `case` 都不成立時，`default` 所包含的程式碼區塊便會被執行

定義 `case` 程式碼區塊要使用 `:`

{% code lineNumbers="true" %}
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
{% endcode %}

輸出：

> Mix of blue and yellow
