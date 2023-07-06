# 字典

## 字典

字典用來儲存沒有順序性的多組資料，每組資料都會由鍵值和其所對應的值所組成

使用 `[鍵值型態: 對應值型態]()` 宣告一個空的陣列

```swift
var dictionaryName = [String:Int]()
```

### 初始化字典

初始化字典可以在宣告時給字典初始值，如果沒有指定型態 Swift 會自動判斷

在 `[]` 中使用 `,` 分開不同組的資料

```swift
// 不指定型態:
var employeeID = [
  "Hamlet": 1367,
  "Horatio": 8261,
  "Ophelia": 9318
]

// 指定型態:
var yearlyBirdPopulation: [Int: Int] = [
  2020: 7385467,
  2021: 8261462,
  2022: 9318523
]
```

### 鍵值

每個字典裡的鍵值都是唯一不重複的

鍵值可以用來取得、刪除、增加或修改其對應的值

```swift
// 每個鍵值都是唯一不重複的即使其所對應的值都相等

var fruitStand = [
  "Coconuts": 12,
  "Pineapples": 12,
  "Papaya": 12
]
```

### 型態固定

字典中鍵值和對應值的型態宣告後不能改變

```swift
// 字串鍵值，整數對應值

var numberOfSides = [
  "triangle": 3,
  "square": 4,
  "rectangle": 4
]
```

### 新增一組資料

使用 `字典名稱[新鍵值] = 新對應值` 在字典裡新增一組資料

```swift
var pronunciation = [
  "library": "lai·breh·ree",
  "apple": "a·pl"
]

// 新鍵值: "programming", 新對應值: "prow·gra·muhng"
pronunciation["programming"] = "prow·gra·muhng"
```

### 刪除資料

刪除字典裡的資料可以使用以下方式

* 將鍵值的對應值設為 `nil`
* `.removeValue()` 刪除鍵值的對應值
* `.removeAll()` 刪除所有鍵值的對應值，變成空字典

```swift
var bookShelf = [
  "Goodnight Moon": "Margaret Wise Brown",
  "The BFG": "Roald Dahl",
  "Falling Up": "Shel Silverstein",
  "No, David!": "David Shannon"
]

// 將鍵值的對應值設為 nil
bookShelf["The BFG"] = nil

// 刪除鍵值的對應值
bookShelf.removeValue(forKey: "Goodnight Moon")

// 刪除所有鍵值的對應值
bookShelf.removeAll()
```

### 修改資料

可以直接指定鍵值要修改的對應值或使用 `.updateValue()`

```swift
var change = [
  "Quarter": 0.29,
  "Dime": 0.15,
  "Nickel": 0.05,
  "Penny": 0.01
]

// 指定鍵值要修改的對應值
change["Quarter"] = .25

// 使用 .updateValue() 修改對應值
change.updateValue(.10, forKey: "Dime")
```

### .isEmpty()

`.isEmpty()` 用來判斷字典是否為空字典

```swift
var bakery = [String:Int]() 

print(bakery.isEmpty)

bakery["Cupcakes"] = 12  

print(bakery.isEmpty)
```

輸出：

> true
>
> false

### .count

`.count` 會回傳字典裡有幾組資料

```swift
var fruitStand = [
  "Apples": 12,
  "Bananas": 20,
  "Oranges", 17
]

print(fruitStand.count)
```

輸出：

> 3

### 指派對應值給變數

使用 `字典名稱[鍵值]` 指派其對應值給變數

```swift
var primaryHex = [
  "red": "#ff0000",
  "yellow": "#ffff00",
  "blue": "#0000ff",
]

print("The hex code for blue is \(primaryHex["blue"])")

if let redHex = primaryHex["red"] {
  print("The hex code for red is \(redHex)")
}
```

輸出：

> The hex code for blue is Optional("#0000ff")
>
> The hex code for red is #ff0000

{% hint style="info" %}
字典中對應值型態是 Optional，可以參考[進階語法](../jin-jie-yu-fa/optional.md)
{% endhint %}

### 結合 for 迴圈

for 迴圈中的資料集合也可以使用字典

```swift
var emojiMeaning = [
  "🤔": "Thinking Face",
  "😪": "Sleepy Face",
  "😵": "Dizzy Face"
]

// 使用鍵值和對應值
for (emoji, meaning) in emojiMeaning {
  print("\(emoji) is known as the '\(meaning) Emoji'")
}

// 使用鍵值
for emoji in emojiMeaning.keys {
  print(emoji)
}

// 使用對應值
for meaning in emojiMeaning.values {
  print(meaning)
}
```

輸出：

> 😪 is known as the 'Sleepy Face Emoji'
>
> 😵 is known as the 'Dizzy Face Emoji'
>
> 🤔 is known as the 'Thinking Face Emoji'
>
> 😪
>
> 😵
>
> 🤔
>
> Sleepy Face
>
> Dizzy Face
>
> Thinking Face
