# 函式

## 函式

函式是一個可重複利用的程式碼區塊，用來執行指定的任務

使用語法 `func` 宣告一個函數，函數名稱、參數(可有可無)、回傳值和要執行任務的程式碼區塊

```swift
func washCar() -> Void {
  print("Soap")
  print("Scrub")
  print("Rinse")
  print("Dry")
}

// 名稱為 washCar 沒有參數和回傳值的函式
```

### 呼叫函式

宣告函式之後如果要使用，便要呼叫它出來

使用語法 `函數名稱()` 來呼叫一個函式，`()` 包含了必要的參數

```swift
func greetLearner() {
 print("Welcome to Codecademy!")
}

// 呼叫函式
greetLearner() 
```

輸出：

> Welcome to Codecademy!

### 回傳值

函式可以回傳一種型態的值，如果要有回傳值宣告函式時就要定義回傳值的值以及型態

在函式中使用 return 定義回傳值，並在 `() ->` 後面定義回傳值的型態

```swift
let birthYear = 1994
var currentYear = 2020

func findAge() -> Int {
  return currentYear - birthYear
}

print(findAge())
```

輸出：

> 26

### 參數

函式可以視情況在宣告時加上參數，參數會被傳入函式並被使用

在 () 內加上 `參數名稱: 參數型態` 宣告參數

```swift
func findSquarePerimeter(side: Int) -> Int {
  return side * 4
} 

let perimeter = findSquarePerimeter(side: 5)
print(perimeter)
```

輸出：

> 20

### 多個參數

函式可以傳入多個參數

在 `()` 內使用 `,` 分開不同參數

```swift
func convertFracToDec(numerator: Double, denominator: Double) -> Double {
  return numerator / denominator
} 

let decimal = convertFracToDec(numerator: 1.0, denominator: 2.0) 
print(decimal)
```

輸出：

> 0.5

### 回傳多個值

函式可以回傳多個值

使用元祖回傳多個值，並且在元祖中所有資料都要有名稱和型態

```swift
func smartphoneModel() -> (name: String, version: String, yearReleased: Int) {
  return ("iPhone", "8 Plus", 2017)
}

let phone = smartphoneModel()

print(phone.name)
print(phone.version)
print(phone.yearReleased)
```

輸出：

> iPhone
>
> 8 Plus
>
> 2017

{% hint style="info" %}
元祖是一個不可變的資料集合型態，使用 `()` 表示
{% endhint %}

### 省略參數名稱

在宣告函數時在參數名稱前加上 `_` 可以在呼叫函式時省略那個參數的名稱

```swift
func findDifference(_ a: Int, b: Int) -> Int {
  return a - b
}

print(findDifference(6, b: 4))
```

輸出：

> 2

### 省略 return 關鍵字

宣告函式時可以直接省略 `return` 關鍵字

```swift
func nextTotalSolarEclipse() -> String {
  "April 8th, 2024 🌎"
}

print(nextTotalSolarEclipse())
```

輸出：

> April 8th, 2024 🌎

### 預設參數值

函數宣告時可以給參數一個預設值，呼叫時沒有傳入參數便會使用預設值

```swift
// 預設參數 wordsPerMin 的值為 200
func timeToFinishBook(numWords: Double, wordsPerMin: Double = 200) -> Double {
  let totalMinutes = numWords / wordsPerMin 
  return totalMinutes / 60 
}

print("\(timeToFinishBook(numWords: 93000)) hours")
```

輸出：

> 7.75 hours

### 可變數量參數

宣告函數時在參數型態後面加上 `...` 可以在呼叫時傳入零或多個同型態的參數

```swift
func totalStudents(students: String...) -> Int {
  let numStudents = students.count
  return numStudents
}

print(totalStudents(students: "Jamie", "Michael", "Rose", "Idris"))
```

輸出：

> 4

### inout 參數

`inout` 參數是個會被回傳的參數，可以在函式裡被修改

呼叫函式時要在 `inout` 參數的值前面加上 `&`

```swift
var currentSeason = "Winter" 

func determineSeason(monthNum: Int, season: inout String) {

switch monthNum {
  case 1...2:
    season = "Winter ⛄️" 
  case 3...6:
    season = "Spring 🌱"
  case 7...9:
    season = "Summer ⛱"
  case 10...11: 
    season = "Autumn 🍂"
  default: 
    season = "Unknown"
  } 
} 

determineSeason(monthNum: 4, season: &currentSeason)

print(currentSeason)
```

輸出：

> Spring 🌱
