# Optional

## Optional

Optional 型態的變數值可以為 `nil`

在型態後面加上 `?` 宣告 Optional 型態

```swift
var email: String? = nil
email = "codey@codecademy.com"
```

{% hint style="info" %}
nil 是沒有值的意思
{% endhint %}

### 強制拆包

使用 `!` 強制拆包，取得 Optional 型態變數的值，如果 Optional 型態變數的值是 `nil` 程式碼會崩潰

```swift
var name: String? = "Codey"
print("The user's name is \(userName!)")
```

輸出：

> The user's name is Codey

```swift
var email: String? = nil
print("The user's email is \(userEmail!)") 

// 程式碼崩潰，沒有輸出
```

{% hint style="info" %}
取得 Optional 型態變數的值叫做拆包，就像拆禮物一樣不知道裡面有沒有值
{% endhint %}

### 綁定

一個安全的拆包方法是使用 `if let` 將 Optional 型態變數綁定到一個新變數上，如果 Optional 是 `nil` 則執行 `else` 程式碼區塊

```swift
var name: String? = "Codey"
var email: String? = nil

if let name = name {
  print("The user's name is \(name)")
} else {
  print("No name available")
}

if let unwrappedEmail = email {
  print("The user's email is \(unwrappedEmail)")
} else {
  print("No email available")
}
```

輸出：

> The user's name is Codey
>
> No email available

### 多重綁定

`if let` 可以綁定多個 Optional 型態變數

```swift
var name: String? = "Codey"
var email: String? = "codey@codecademy.com"

if let name = name, let email = email, email.contains("@") {
  print("Welcome to Codecademy \(name)!  Your email address is \(email)")
} else {
  print("Name is nil, email is nil, or the email is invalid")
}
```

輸出：

> Welcome to Codecademy Codey! Your email address is codey@codecademy.com

### guard 條件判斷

如果 `guard` 之後的條件不成立(true)， `else` 所包含的程式碼區塊便會被執行

`guard` 的後面必須要有 `else` 程式碼區塊

```swift
var name: String? = "Codey"
var email: String? = "codey@codecademy.com"

func displayMessageIfValid() {
  guard let name = name, let email = email, email.contains("@") else {
    return
  }
  print("Welcome \(name)!  Your email is \(email)")
}

displayMessageIfValid()
```

輸出：

> Welcome Codey! Your email is codey@codecademy.com

### 空值聚合運算子

如果 `??` 前面的 Optional 型態變數不是 `nil` 就回傳 Optional 型態變數的值

反之如果 `??` 前面的 Optional 型態變數是 `nil` 就回傳 `??` 後面的程式碼

```swift
var email: String? = nil
print("Welcome!  Your email is \(email ?? "unknown").")
```

輸出：

> Welcome! Your email is unknown.

### 結合函數

函數傳入的參數和回傳值可以是 Optional 型態

```swift
func getFirstInitial(from name: String?) -> String? {
  return name?.first
}
```
