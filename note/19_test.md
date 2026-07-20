# ChatGPT
https://chatgpt.com/g/g-p-6a3958fd19d08191a19479103a10980e-work/c/6a5e2dbc-0248-83ee-a3e7-ef618bebe927


# テスト実行コマンド
```
go test ./...
go test -v ./...
go test -v -run TestAddHandler
```

# 実行ルール

 1.   `./...` 配下のパッケージを探す
 2.  `*_test.go` を探す
 3. その中から `TestXxx(t *testing.T)` を探す
 4. それらを実行する

