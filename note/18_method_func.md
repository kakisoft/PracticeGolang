# ChatGPT
https://chatgpt.com/g/g-p-6a3958fd19d08191a19479103a10980e-work/c/6a5e2dbc-0248-83ee-a3e7-ef618bebe927


# メソッド
ある型（構造体など）に属する処理
```go
func (h *Handler) Add() {}
```

# 関数
単独で存在する処理
```go
func TestAddHandler(t *testing.T) {}
```



#
```go
package main

import "fmt"

// 構造体
type Handler struct {
	Name string
}

// Handler のメソッド
func (h *Handler) Add() {
	fmt.Println("Hello,", h.Name)
}

func main() {
	handler := &Handler{
		Name: "Taro",
	}

	handler.Add()
}
```
