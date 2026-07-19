# ChatGPT
https://chatgpt.com/g/g-p-6a3958fd19d08191a19479103a10980e-work/c/6a5baa8a-2608-83ee-b4ef-95ebca38845c


# メモ
 * `&` - p := &user : この変数のアドレスを教えて
 * `*` - ポインタの指定先の実態から値を取り出す。fmt.Println((*p).Name) ・fmt.Println(p.Name)   ※こっちの書き方のがメジャー


# `*` の使われ型

| 見つけた場所       | まず考えること                | 例                             |
| ------------------ | ----------------------------- | ------------------------------ |
| 関数の引数         | 通常のポインタ（参照渡し）    | func Save(user *User)          |
| 構造体のフィールド | NULL許容                      | type User struct { Age  *int } |
| 戻り値             | 「見つからない」を表す(nil)   | func Find(id int) *User        |


厳密には、「参照渡し」とは言わないらしい。（Goの言語仕様として、「全部値渡しです」という事らしい。）  
調べたが、結局言葉遊びにしか思えん。値渡しで解決できない問題を解決したいからポインタを使ってるんじゃないのか？  
実現したいことが参照渡しの事なら、↑で理解してしまえ。  


# Go
```go
package main

import "fmt"

func main() {
	x := 10      // 普通の変数
	p := &x      // & = xのアドレス（ポインタ）を取得

	fmt.Println(x)  // 10
	fmt.Println(p)  // 0xc000... （アドレス）
	fmt.Println(*p) // 10 （ポインタの先の値）

	*p = 20         // ポインタ経由で値を書き換える

	fmt.Println(x)  // 20
	fmt.Println(*p) // 20
}
```
