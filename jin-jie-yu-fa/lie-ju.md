# 列舉

## 列舉

列舉用來自定義一系列的關聯值，實體化列舉一定要宣告 `case`

使用 `enum` 宣告一個列舉

```swift
enum Day {
  case monday
  case tuesday
  case wednesday
  case thursday
  case friday
  case saturday
  case sunday
}

let casualWorkday: Day = .friday
```

### CaseIterable 與 .allCases

宣告列舉時加上 `CaseIterable` 就可以使用 `.allCases` 回傳一個包含所有 `case` 的陣列

```swift
enum Season: CaseIterable {
    case winter
    case spring
    case summer
    case fall
}

for season in Season.allCases {
    print(season)
}
```

輸出：

> winter
>
> spring
>
> summer
>
> fall

### 原始值與 .rawValue

宣告列舉時加上 `:型態` 宣告 `case` 裡原始值的型態

`.rawValue` 用來取得 `case` 裡的原始值

```swift
enum Grade: Character {
  case pass = "P"
  case fail = "F"
}

let mathTest = Grade.pass
print(mathTest.rawValue)
```

輸出：

> P

### 關聯值

關聯值可以根據不同 `case` 有不同型態

宣告列舉時在 `case` 名稱後面加上 `(關聯值名稱: 關聯值)`

```swift
enum Dessert {
    case cake(flavor: String)
    case vanillaIceCream(scoops: Int)
    case brownie
}

let customerOrder: Dessert = .cake(flavor: "Red Velvet")
```

{% hint style="info" %}
枚舉的 case 只能儲存原始值或關聯值擇一，不能並存
{% endhint %}

### 列舉函式

寫在列舉中的函式只有同列舉的實體才能呼叫

如果會更改列舉的 `case` ，宣告函式時前面要加上 `mutating`

```swift
enum Traffic {
  case light
  case medium
  case heavy
  
  mutating func reportAccident() {
    self = .heavy
  }
}

var currentTraffic: Traffic = .light
currentTraffic.reportAccident() 

// currentTraffic 的 case 現在是 .heavy
```

### 計算屬性

`enum` 裡可以儲存計算屬性的變數

```swift
enum ShirtSize: String {
  case small = "S"
  case medium = "M"
  case large = "L"
  case extraLarge = "XL"
  
  var description: String {
    return "This shirt size is \(self.rawValue)"
  }
}
```

{% hint style="info" %}
計算屬性就像是一個偽裝成變數的函式，儲存的不是值而是一個「取得值的方法」
{% endhint %}

### 結合 switch 條件判斷

`switch` 裡的 `case` 也可以使用列舉的 `case`&#x20;

如果 `switch` 沒有宣告 `default` 則列舉裡面所有的 `case` 都要被列出

```swift
enum Dessert {
    case cake(flavor: String)
    case vanillaIceCream(scoops: Int)
    case brownie
}

let customerOrder: Dessert = .cake(flavor: "Red Velvet")

switch customerOrder {
  case let .cake(flavor):
  	print("You ordered a \(flavor) cake")
  case let .vanillaIceCream(scoopCount):
  	print("You ordered \(scoopCount) scoops of vanilla ice cream")
  case .brownie: 
  	print("You ordered a brownie")
}
```

輸出：

> You ordered a Red Velvet cake
