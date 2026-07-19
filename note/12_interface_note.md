# ChatGPT
https://chatgpt.com/g/g-p-6a3958fd19d08191a19479103a10980e-work/c/6a5bb5ac-47a8-83ee-b576-c10c4054fd36


# メモ
 * 結局、PHP や Java のインターフェースと同じ。
 * 「抽象メソッドの概念は無い」との事だが、言語設計仕様の理念まで踏み込まないと差分は無い。見た目では「抽象メソッドじゃん」としか見えん。
 * ジェネリクスもある。
 * implements が無い。コンパイラ任せのXX仕様。
 * 「明示的で読みやすい」を掲げる一方、インターフェースだけは、『実装関係をソースコードに書かず、コンパイラに推測させる』と言う謎仕様。


# PHP
```php
interface Animal
{
    public function speak(): string;
}

class Dog implements Animal
{
    public function speak(): string
    {
        return "ワン";
    }
}

class Cat implements Animal
{
    public function speak(): string
    {
        return "ニャー";
    }
}

function hello(Animal $animal): void
{
    echo $animal->speak() . PHP_EOL;
}

hello(new Dog());
hello(new Cat());
```


## Go
```go
package main

import "fmt"

type Animal interface {
	Speak() string
}

// Dogクラス（プロパティなし）
type Dog struct{}

// Dog型のメソッド Speak
func (Dog) Speak() string {
	return "ワン"
}

// Catクラス（プロパティなし）
type Cat struct{}

// Cat型のメソッド Speak
func (Cat) Speak() string {
	return "ニャー"
}

// Animal型の変数を引数とした hello メソッド
func Hello(a Animal) {
	fmt.Println(a.Speak())
}

func main() {
	Hello(Dog{})
	Hello(Cat{})
}
```

・Dog は Speak を持っている。  
・Animal はインターフェースで Speak を持っている。  
・よって、Dog は Animal インターフェースを実装している。  

コンパイラは↑のように解釈する

Speak メソッドを保持してしまうと、自動的に Animal のインターフェースになってしまうので、インターフェース扱いされない Speak メソッドは保持できない。

インターフェースのスコープは、パッケージ内。  
例： package animal  

結構な広範囲で、どこでインターフェースを定義しているかは迷子になりがち。  
IDE では厳しい場面も。AIの出番。  


