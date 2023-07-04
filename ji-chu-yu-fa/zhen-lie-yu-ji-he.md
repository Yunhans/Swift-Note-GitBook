# 陣列與集合

## 陣列

陣列用來儲存多個同種資料型態(type)

使用語法 `[型態]()` 宣告一個空的陣列

```swift
var scores = [Int]()

// Int 型態的空陣列: []
```

### 初始化陣列

初始化陣列可以在宣告時給陣列初始值

```swift
// 不指定型態:
var snowfall = [2.4, 3.6, 3.4, 1.8, 0.0]

// 指定型態:
var temp: [Int] = [33, 31, 30, 38, 44]
```

### 索引

索引用來找出陣列裡第n個值

```swift
var vowels = ["a", "e", "i", "o", "u"]

print(vowels[0])
print(vowels[1])
print(vowels[2])
print(vowels[3])
print(vowels[4])
```

輸出：

> a
>
> e
>
> i
>
> o
>
> u

{% hint style="info" %}
Swift 的陣列索引是從 0 開始計算
{% endhint %}

### .count

`.count` 會回傳陣列裡有幾個值

```swift
var grocery = ["🥓", "🥞", "🍪", "🥛", "🍊"]

print(grocery.count)
```

輸出：

> 5

### .append() 和 +=  <a href="#heading-append-method-and--operator" id="heading-append-method-and--operator"></a>

`.append()` 在陣列的最後增加一個值

`+=` 用來把兩個陣列串在一起

```swift
var gymBadges = ["Boulder", "Cascade"]

gymBadges.append("Thunder")
gymBadges += ["Rainbow", "Soul"]

// ["Boulder", "Cascade", "Thunder", "Rainbow", "Soul"]
```

### .insert() 和 .remove()

`.insert()` 用來在陣列裡指定的索引中插入一個值

`.remove()` 用來刪除陣列裡指定的索引中一個值

```swift
var moon = ["🌖", "🌗", "🌘", "🌑"]

moon.insert("🌕", at: 0)

// ["🌕", "🌖", "🌗", "🌘", "🌑"]

moon.remove(at: 4)

// ["🌕", "🌖", "🌗", "🌘"]
```

### 結合 for 迴圈

for 迴圈中的資料集合可以使用陣列

```swift
var employees = ["Michael", "Dwight", "Jim", "Pam", "Andy"]

for person in employees {
  print(person)
}
```

輸出：

> Michael
>
> Dwight
>
> Jim
>
> Pam
>
> Andy
