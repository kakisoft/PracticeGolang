# ChatGPT
https://chatgpt.com/g/g-p-6a3958fd19d08191a19479103a10980e/c/6a5bad40-4568-83ee-b471-6e8c4543afd6


# メモ
 * var s []int          - 宣言のみ
 * var s = []int{1,2,3} - varで宣言＋初期化
 * s := []int{1,2,3}    - :=で宣言＋初期化（↑と同じ）「:=」は、ローカル変数にしか使えない。


 * array - 固定長配列
 * slice - 可変長配列。append で値を追加。


# Go
```go
// 要素数3の配列
numbers := [3]int{10, 20, 30}

// スライス（実務ではこちらをよく使う）
s := []int{1, 2, 3}
```

append
```go
var s []int
s = append(s, 10)
// s の末尾に 10 を追加
```

