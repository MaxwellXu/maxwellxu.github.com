

未登陆docker
---
1. 在构建dockerfile的时候，提示以下错误的时候，则需要通过cli进行登陆
```console
Get https://registry-1.docker.io/v2/library/centos/manifests/7.6: unauthorized: incorrect username or password
```
2. 命令`docker login -u [dockerid]`，这里需要用到dockerid，而不能是`注册邮箱`