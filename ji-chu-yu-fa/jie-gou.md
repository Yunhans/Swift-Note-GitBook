# 結構

## 結構

結構通常用來表現現實中存在的物件，裡面可以儲存多個變數和函式

使用 `struct` 宣告一個結構

```swift
struct Building {
  var address: String
  var floors: Int

  init(address: String, floors: Int, color: String) {
    self.address = address
    self.floors = floors
  }
}
```

### 結構實體化

使用 `結構名稱()` 來實體化一個結構，`()` 包含了必要的參數

```swift
struct Person {
  var name: String
  var age: Int

  init(name: String, age: Int) {
    self.name = name
    self.age = age
  }
}

var morty = Person(name: "Morty", age: 14)
```

{% hint style="info" %}
結構就像是房子的設計圖，裡面包含了房子應該要有的基本構造，例如：樓梯、窗戶、門

實體化結構則像是蓋出一間實體的房子，並給房子窗戶數量或樓梯材質等
{% endhint %}

### 預設值

結構中的變數可以有預設值，宣告一個新實體結構時沒有傳入參數便會使用預設值

```swift
struct Car {
  var numOfWheels = 4
  var topSpeed = 80
}

var reliantRobin = Car(numOfWheels: 3)

print(reliantRobin.numOfWheels)
print(reliantRobin.topSpeed) 
```

輸出：

> 3
>
> 80

### init()

`init()` 用來初始化結構裡變數的值，在 `init()` 包含的程式碼區塊中使用 `self` 指定變數的值

```swift
struct TV {
  var screenSize: Int
  var displayType: String
  
  init(screenSize: Int, displayType: String) {
    self.screenSize = screenSize
    self.displayType = displayType
  }
}

var newTV = TV(screenSize: 65, displayType: "LED")
```

### 結構函式

寫在結構中的函式只有同結構的實體才能呼叫

使用 `物件實體.函式名稱()` 呼叫結構函式

```swift
struct Dog {
  func bark() {
    print("Woof")
  }
}

let fido = Dog()
fido.bark()
```

輸出：

> Woof

### mutating

如果結構函式會修改到變數的值，要在宣告函式前面加上 `mutating`

```swift
struct Menu {
  var menuItems = ["Fries", "Burgers"]

  mutating func addToMenu(dish: String) {
    self.menuItems.append(dish)
  }
}

var dinerMenu = Menu()

dinerMenu.addToMenu(dish: "Toast")
print(dinerMenu.menuItems) 
```

輸出：

> \["Fries", "Burgers", "Toast"]

{% hint style="warning" %}
如果不加上 mutating 會發生什麼事？
{% endhint %}

***

## 確認型態

使用 `type(of:)` 確認輸入值的型態

```swift
print(type(of: "abc"))
print(type(of: 123))
```

輸出：

> String
>
> Int
