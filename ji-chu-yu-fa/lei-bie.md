# 類別

## 類別

類別通常用來表現現實中存在的物件，裡面可以儲存多個變數和函式

使用 `class` 宣告一個類別

```swift
// 使用型態:
class Student {
  var name: String
  var year: Int
  var gpa: Double
  var honors: Bool
}


// 給初始值:
class Student {
  var name = ""
  var year = 0
  var gpa = 0.0
  var honors = false
}
```

### 類別實體化

使用 `類別名稱()` 來實體化一個類別，`()` 包含了必要的參數

```swift
class Person {
  var name = ""
  var age = 0
}

var sonny = Person()
```

### 取得類別中的變數

使用 `.變數名稱` 取得變數的值

```swift
// 使用上面用過的 Student 類別
var ferris = Student()

ferris.name = "Ferris Bueller"
ferris.year = 12
ferris.gpa = 3.81
ferris.honors = false
```

### init()

`init()` 用來初始化類別裡變數的值，在 `init()` 包含的程式碼區塊中使用 `self` 指定變數的值

```swift
class Fruit {
  var hasSeeds = true 
  var color: String

  init(color: String) {
    self.color = color
  }
}

let apple = Fruit(color: "red")
```

### 繼承

類別可以繼承其他類別使用繼承類別的變數和函式

* 繼承其他類別的類別被稱為子類別 subclass
* 被繼承的類別被稱為父類別 superclass

```swift
class BankAccount {
  var balance = 0.0

  func deposit(amount: Double) {
    balance += amount
  }

  func withdraw(amount: Double) {
    balance -= amount
  }
}


// 子類別 SavingsAccount 繼承父類別 BankAccount

class SavingsAccount: BankAccount {
  var interest = 0.0

  func addInterest() {
    let interest = balance * 0.005
    self.deposit(amount: interest)
  }
}

// 子類別 SavingsAccount 此時擁有了父類別 BankAccount 的所有變數和函式
```

### 覆寫

子類別裡可以使用 `override` 覆寫繼承自父類別的變數或函式

```swift
class BankAccount {
  var balance = 0.0

  func deposit(amount: Double) {
    balance += amount
  }

  func withdraw(amount: Double) {
    balance -= amount
  }
}

class SavingsAccount: BankAccount {
  var interest = 0.0
  var numWithdraw = 0

  func addInterest() {
    let interest = balance * 0.01
    self.deposit(amount: interest)
  }

  override func withdraw(amount: Double) {
    balance -= amount
    numWithdraw += 1
  }
}
```
