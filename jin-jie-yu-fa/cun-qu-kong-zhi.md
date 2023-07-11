# 存取控制

## 存取控制

存取控制用來設置結構、類別或列舉的存取權限，限制哪些屬性或方法可以被結構、類別或列舉以外的程式碼取用或修改

### 存取層級

Swift 可用的存取層級有：

* public / open
* internal
* fileprivate
* private

```swift
// public 層級的結構可以被其他模組取用
public struct User { 
  // 預設層級為 internal
	let name: String 
  // fileprivate 層級的方法只能在被宣告的檔案中被取用
  fileprivate func incrementVisitCount() {
    visitCount += 1
  }
  // private 層級的屬性只能在宣告結構時被取用
  private let visitCount = 0
}
```

### private 屬性與方法

宣告為 `private` 的屬性與方法避免結構、類別或列舉外部的程式碼直接取用

```swift
struct User {
  let name: String
  init(name: String) {
    self.name = name
    uploadNewUser()
  }
  private func uploadNewUser() {
    print("Uploading the new user...")
  }
}
```

### 唯獨計算屬性

唯獨計算屬性可以被取得但不能被

宣告唯獨計算屬性可以：

* 使用 `get` 但不使用 `set`
* 都省略不使用

```swift
struct Room {
  let width: Double
  let height: Double
  var squareFeet: Double {
    return width * height
  }
  var description: String {
    get {
      return "This room is \(width) x \(height)"
    }
  }
}
```

### 屬性觀察器

屬性觀察器會在屬性被修改時觸發以下兩個程式碼區塊：

1. `willSet` 會在被修改前執行並在程式碼區塊裡產生變數 `newValue`
2. `didSet` 會在被修改後執行並在程式碼區塊裡產生變數 `oldValue`

```swift
struct Employee {
  var hourlyWage = 15 {
    willSet {
      print("The hourly wage is about to be changed from \(hourlyWage) to \(newValue)")
    }
    didSet {
      print("The hourly wage has been changed from \(oldValue) to \(hourlyWage)")
    }
  }
}

var codey = Employee()
codey.hourlyWage = 20
```

輸出：

> The hourly wage is about to be changed from 15 to 20
>
> The hourly wage has been changed from 15 to 20

### private(set)

宣告為 `private(set)` 的屬性與方法可以被結構、類別或列舉外部的程式碼取得，但只能在結構、類別或列舉內部修改

```swift
struct User {
	private(set) var name: String
  mutating func updateName(to newName: String) {
  	if newName != "" {
    	name = newName
    }
  }
}

var currentUser = User(name: "codey")
currentUser.updateName(to: "Codey")
print(currentUser.name)
currentUser.name = "Bob" // 這一行編譯會出錯，不能再結構外直接修改值
```

***

## 靜態屬性與方法

靜態屬性和方法會被結構、類別或列舉本身呼叫而不是被實體呼叫

使用 `static` 宣告靜態屬性和方法

```swift
struct User {
  static var allUsers = [User]()
  let id: Int
  init(id: Int) {
    self.id = id
    User.allUsers.append(self)
  }
}

let userOne = User(id: 1)
let userTwo = User(id: 2)
let userThree = User(id: 3)

print(User.allUsers)
```

## 擴展

擴展用來定義一個現有的結構、類別或列舉，擴展裡可以有新的方法、計算屬性、結構、類別或列舉，但不能新增屬性

使用 `extension` 宣告一個擴展

```swift
struct User {
  let name: String
}

extension User {
  var description: String {
    return "This is a user named \(name)"
  }
}
```
