# ChatGPT
https://chatgpt.com/g/g-p-6a3958fd19d08191a19479103a10980e-work/c/6a5d59f5-252c-83e8-8217-cf34411e5150

# メモ
 * 「 _ 」は「この値はいらないので捨てます」
 * ブランク識別子 (blank identifier) という名称

# Go
```go
Golang

func testdataDir() string {
	wd, _ := os.Getwd()
	dir, _ := filepath.Abs(filepath.Join(filepath.Dir(filepath.Dir(wd)), "testdata"))
	return dir
}
```

