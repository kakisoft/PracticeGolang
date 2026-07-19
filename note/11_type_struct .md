# ChatGPT
https://chatgpt.com/g/g-p-6a3958fd19d08191a19479103a10980e/c/6a5b040d-1238-83ee-bc58-b6dcd7bfc8b3


# メモ
 * 構造体に型定義のみ。
 * 構造体にメソッドをくっつける。Class とメソッドを分離して定義するような感じ。
 * アクセサは無い。欲しけりゃ自前で実装する。基本は public
 * クラスの概念は無いが、事実上インスタンス作成みたいな事をする事なっている。
 * レシーバ = $this （だいたいそんな感じ）

# Go
```go
package main

import "fmt"

type User struct {
	Name string
	Age  int
}

// 値を変更しないので値レシーバ
func (u User) IsAdult() bool {
	return u.Age >= 18
}

// 値を変更するのでポインタレシーバ
func (u *User) Rename(name string) {
	u.Name = name
}

func (u User) Greet() {
	fmt.Printf("こんにちは、%sです！（%d歳）\n", u.Name, u.Age)
}

func main() {
	user := User{
		Name: "Alice",
		Age:  20,
	}

	user.Greet()

	if user.IsAdult() {
		fmt.Println("成人です")
	}

	user.Rename("Bob")
	user.Greet()
}
```
