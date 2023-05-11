---
author: 马凯旋
---



### Network error
1. install YouComplete	
``` bash
# common solution to network error: set proxy, e.g., 科学上网
echo http_proxy=http://127.0.0.1
echo https_proxy=https://127.0.0.1
  
# Go 代理问题
echo GOPROXY=https://goproxy.cn
```
``` go
go env -w GOPROXY=https://goproxy.cn
```