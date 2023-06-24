---
description: Hello World!
---

# 基礎

## 輸出 print()

print() 功能可以輸出一行或多行文字或值

```swift
print("Hello world!")
```

輸出：

> Hello world!

## 程式碼結構 Program Structure <a href="#heading-program-structure" id="heading-program-structure"></a>

程式語言是一行一行、由上而下的編譯 (line by line)

{% code lineNumbers="true" fullWidth="false" %}
```swift
print("Hola")
print("Buenos días")
```
{% endcode %}

輸出：

> Hola
>
> Buenos días

## 單行註解 Single-line Comments <a href="#heading-single-line-comments" id="heading-single-line-comments"></a>

同一行中兩個斜線 `//` 之後的文字將不會被編譯

```swift
// 這行文字在Swift視為註解
```

## 多行註解 Multiline Comment <a href="#heading-multiline-comments" id="heading-multiline-comments"></a>

使用 `/*` 以及 `*/` 所包含的所有文字將不會被編譯，無論有沒有跨行

{% code lineNumbers="true" %}
```swift
/* 
全部都是註解
這行也是
都不會被編譯
*/
```
{% endcode %}

{% hint style="info" %}
註解是為了讓自己以及其他人了解程式碼的功能及目的，是維護程式碼很重要的一部份
{% endhint %}
