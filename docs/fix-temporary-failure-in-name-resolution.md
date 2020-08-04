---
heading: "解决\"Temporary failure in name resolution\""
date: 2020-07-31 20:16
---
使用git clone代码时遇到报错

```
ssh: Could not resolve hostname github.com: Temporary failure in name resolution        
fatal: Could not read from remote repository.
```

测试ping百度依然报错

```
ping: github.com: Temporary failure in name resolution
```

解决办法

```sh
sudo vi /etc/resolv.conf
```

添加如下内容

```
nameserver 8.8.8.8
```