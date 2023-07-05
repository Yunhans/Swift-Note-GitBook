# 列舉

## 列舉

列舉用來自定義一系列的關聯值，實體化列舉一定要宣告關聯值

使用 `enum` 宣告一個列舉，在 `case` 後加上關聯值

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

