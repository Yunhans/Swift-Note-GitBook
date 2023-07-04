# 迴圈

## 區間

用 `...` 宣告區間的數字起始及結束(包含)

```swift
let zeroToThree = 0...3

// zeroToThree 包含了: 0, 1, 2, 3
```

## for-in 迴圈

`for-in` 迴圈會反覆執行 `for-in` 包含的程式碼區塊，當 `in` 後面的資料集合的個別資料都被執行完畢便會結束迴圈，資料集合型態可以是區間或字串

在執行過程中資料集合會被切分成個別資料儲存在 `for` 和 `in` 中間的變數名稱中

```swift
for char in "hehe" {
  print(char)
}
```

輸出：

> h
>
> e
>
> h
>
> e

### 遞增遞減 stride()

`in` 後面的資料集合可以使用 `stride()` 讓區間宣告更加靈活

使用stride() 要輸入三個參數：

1. 區間起始數字 `from`
2. 區間結束數字(不包含) `to`
3. 區間的遞增或遞減單位 `by`

```swift
for oddNum in stride(from: 1, to: 5, by: 2) {
  print(oddNum)
}
```

輸出：

> 1
>
> 3

{% hint style="info" %}
注意這裡不會印出 5
{% endhint %}

### 底線

for-in 迴圈中的變數如果沒有被使用到，可以使用 `_` 來省略宣告變數

```swift
for _ in 1...3 {
  print("Olé")
}
```

輸出：

> Olé
>
> Olé
>
> Olé

## 繼續關鍵字 continue

`continue` 會跳過之後的程式碼區塊，強制進行下一個迴圈

```swift
for num in 0...5 {
  if num % 2 == 0 {
    continue
  }
  print(num)
}
```

輸出：

> 1
>
> 3
>
> 5

## 跳脫關鍵字 break

`break` 會終止整個迴圈即使迴圈還沒結束

```swift
for char in "supercalifragilisticexpialidocious" {
  if char == "c" {
    break
  }
  print(char)
}
```

輸出：

> s
>
> u
>
> p
>
> e
>
> r

## while迴圈

只要 `while` 後面的條件成立(true)，`while` 包含的程式碼區塊便會重複執行，直到條件不再成立(false)

```swift
var counter = 1
var stopNum = 3

while counter < stopNum {
  print(counter)
  counter += 1
}
```

輸出：

> 1
>
> 2

{% hint style="danger" %}
如果條件永遠成立便會產生無窮迴圈
{% endhint %}
