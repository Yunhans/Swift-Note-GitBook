# 陣列與集合

## 陣列

陣列用來儲存多個同種資料型態

使用語法 `[型態]()` 宣告一個空的陣列

```swift
var scores = [Int]()

// 儲存 Int 型態的空陣列: []
```

### 初始化陣列

初始化陣列可以在宣告時給陣列初始值

在 `[]` 中使用 `,` 分開不同的值&#x20;

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

### .append() 與 +=  <a href="#heading-append-method-and--operator" id="heading-append-method-and--operator"></a>

`.append()` 在陣列的最後增加一個值

`+=` 用來把兩個陣列串在一起

```swift
var gymBadges = ["Boulder", "Cascade"]

gymBadges.append("Thunder")
gymBadges += ["Rainbow", "Soul"]

// ["Boulder", "Cascade", "Thunder", "Rainbow", "Soul"]
```

### .insert() 與 .remove()

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

for 迴圈中的資料集合也可以使用陣列

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

***

## 集合

集合用來儲存多個「不重複」且同種的資料型態

使用語法 `Set<型態>()` 宣告一個空的集合

```swift
var team = Set<String>()

// 儲存 String 型態的空陣列: []
```

### 初始化集合

初始化集合可以在宣告時給集合初始值

在 `[]` 中使用 `,` 分開不同的值

```swift
var vowels: Set = ["a", "e", "i", "o", "u"]
```

{% hint style="info" %}
使用集合一定要指定型態 Set
{% endhint %}

### .insert()

`.insert()` 用來在集合中新增一個值

```swift
var cookieJar: Set = ["Chocolate Chip", "Oatmeal Raisin"]

cookieJar.insert("Peanut Butter Chip")

// ["Peanut Butter Chip", "Chocolate Chip", "Oatmeal Raisin"]
```

### .remove() 與 .removeAll()

`.remove()` 用來刪除集合裡面指定的一個值

`.removeAll()` 用來刪除集合裡面所有的值

```swift
var oddNumbers: Set = [1, 2, 3, 5]

oddNumbers.remove(2)

// [1, 3, 5]

oddNumbers.removeAll()

// []
```

### .contains() <a href="#heading-contains" id="heading-contains"></a>

`.contains()` 用來判斷集合裡面指定的一個值存在與否，並回傳布林值

```swift
var names: Set = ["Rosa", "Doug", "Waldo"]

print(names.contains("Lola"))

if names.contains("Waldo"){
  print("There's Waldo!")
} else {
  print("Where's Waldo?")
}
```

輸出：

> false
>
> There's Waldo!

### 結合 for 迴圈

for 迴圈中的資料集合也可以使用集合

```swift
var recipe: Set = ["Chocolate chips", "Eggs", "Flour", "Sugar"]

for ingredient in recipe {
  print ("Include \(ingredient) in the recipe.")
}
```

輸出：

> Include Eggs in the recipe.
>
> Include Flour in the recipe.
>
> Include Sugar in the recipe.
>
> Include Chocolate chips in the recipe.

### .isEmpty()

`.isEmpty()` 用來判斷集合是否為空集合

```swift
var emptySet = Set<String>()

print(emptySet.isEmpty)

var populatedSet: Set = [1, 2, 3]

print(populatedSet.isEmpty)
```

輸出：

> true
>
> false

### .count

`.count` 會回傳集合裡有幾個值

```swift
var band: Set = ["Guitar", "Bass", "Drums", "Vocals"]

print("There are \(band.count) players in the band.")
```

輸出：

> There are 4 players in the band.

***

## 集合關係

<div align="center">

<figure><img src="../.gitbook/assets/setVennDiagram@2x.png" alt="集合關係圖" width="563"><figcaption></figcaption></figure>

</div>

### 交集 .intersection() <a href="#heading-intersection-operation" id="heading-intersection-operation"></a>

`.intersection()` 用來尋找兩個集合之間的交集

```swift
var setA: Set = ["A", "B", "C", "D"]
var setB: Set = ["C", "D", "E", "F"]

var setC = setA.intersection(setB)
print(setC)
```

輸出：

> \["D", "C"]

### 聯集 .union()

`.union()` 用來尋找兩個集合之間的聯集

```swift
var setA: Set = ["A", "B", "C", "D"]
var setB: Set = ["C", "D", "E", "F"]

var setC = setA.union(setB)
print(setC) 
```

輸出：

> \["B", "A", "D", "F", "C", "E"]

### 差集 .subtracting() <a href="#heading-subtracting-operation" id="heading-subtracting-operation"></a>

`.subtracting()` 用來尋找兩個集合之間的差集

```swift
var setA: Set = ["A", "B", "C", "D"]
var setB: Set = ["C", "D"]

var setC = setA.subtracting(setB)
print(setC) 
```

輸出：

> \["B", "A"]

### 對稱差集 .symmetricDifference()

.symmetricDifference() 用來尋找兩個集合之間的對稱差集

```swift
var setA: Set = ["A", "B", "C", "D"]
var setB: Set = ["C", "D", "E", "F"]

var setC = setA.symmetricDifference(setB)
print(setC) 
```

輸出：

> \["B", "E", "F", "A"]
