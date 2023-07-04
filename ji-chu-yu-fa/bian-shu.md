# 變數

## 變數

變數將被儲存在電腦記憶體中，方便之後提取使用、修改資料

使用關鍵字 `var` 宣告變數名稱和值

```swift
var score = 0
```

## 常數 <a href="#heading-constants" id="heading-constants"></a>

常數將被儲存在電腦記憶體中，方便之後提取使用，跟變數不同的是常數一旦被宣告之後便不能修改常數的值

使用關鍵字 `let` 宣告常數名稱和值

```swift
let pi = 3.14
```

## 算數運算子 <a href="#heading-arithmetic-operators" id="heading-arithmetic-operators"></a>

Swift 可用的算數運算子有：

1. 加法運算子 `+`
2. 減法運算子 `-`
3. 乘法運算子 `*`
4. 除法運算子 `/`
5. 餘數運算子 `%`

{% code fullWidth="false" %}
```swift
var x = 0

x = 4 + 2  // x現在是6
x = 4 - 2  // x現在是2
x = 4 * 2  // x現在是8
x = 4 / 2  // x現在是2
x = 4 % 2  // x現在是0
```
{% endcode %}

{% hint style="warning" %}
如果把 var 換成 let 會發生什麼事呢？&#x20;
{% endhint %}

## 型態

Swift 的基礎型態有：

1. 整數數字 `Int`
2. 浮點數(有小數的)數字 `Double`
3. 字串 `String`
4. 布林值 `Bool`

在變數(或常數)名稱之後加上 `:型態` 宣告指定的變數(或常數)型態

```swift
var age: Int = 28
var price: Double = 8.99
var message: String = "good nite"
var lateToWork: Bool = true

// 也可以不先給值
var name: String
name = "Yunhans"
```

## 字串插值

在字串中使用  `\(變數名稱)` 可以將變數代表的值插入字串中

```swift
var apples = 6
print("I have \(apples) apples!")
```

輸出：

> I have 6 apples!

## 複合指派運算子 <a href="#e8-a4-87-e5-90-88-e6-8c-87-e6-b4-be-e9-81-8b-e7-ae-97-e5-a-d-90" id="e8-a4-87-e5-90-88-e6-8c-87-e6-b4-be-e9-81-8b-e7-ae-97-e5-a-d-90"></a>

把算數運算子和 `=` 結合，簡化更新值的程式碼

Swift 可用的複合指派運算子有：

1. 加法指派運算子 `+=`
2. 減法指派運算子 `-=`
3. 乘法指派運算子 `*=`
4. 除法指派運算子 `/=`
5. 餘數指派運算子 `%=`

```swift
var numberOfDogs = 100
numberOfDogs += 1 // numberOfDogs現在是101

print("There are \(numberOfDogs) dalmations!")
```

輸出：

> There are 101 dalmations!
