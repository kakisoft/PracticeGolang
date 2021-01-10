## gcc error
```
exec: "gcc": executable file not found in %PATH%
```

https://mebee.info/2020/03/21/post-6699/
```
choco install mingw
```

## dial tcp 127.0.0.1:3306: connect: connection refused
https://www.javaer101.com/article/5699800.html  
https://stackoverflow.com/questions/57566060/panic-dial-tcp-127-0-0-13306-connect-connection-refused  
https://qiita.com/paragaki/items/9bba24c57e468400cb2c  

コンテナ名を指定するといいらしい。  
が、ふつーに localhost でも行けたり。  
よく分からん。  
が、コンテナを複数動かしたら上手くいかず、  
コンテナを１つだけ動かしていたら上手くいったり。  

