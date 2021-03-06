# 简介

本脚本实现了锐捷 ePortal Web 认证的登录，需要 curl 指令的支持，通过 curl 发送认证所需的 POST 数据包来实现 Web 认证。

项目中的脚本文件以 **_jmu** 结尾命名的仅适用于集美大学，其他学校请使用 **_general** 结尾命名的脚本文件。

更多详情以及用法等请参考：[https://lgiki.pw/2018/01/13/fxxk-ruijie-eportal/](https://lgiki.pw/2018/01/13/fxxk-ruijie-eportal/)

# 用法

```shell
./ruijie_general.sh username password
```

- username参数为认证用户名。
- password参数为认证密码。

# 局限性

在锐捷 ePortal Web 认证的 POST 数据包中发现了 validcode 参数，根据名字猜测这个参数应该是验证码。

我所在的学校并没有开启验证码，只有在登录尝试次数过多的时候才会出现验证码。如果你的学校在登录的时候需要验证码，那么本脚本将无法进行认证。

本脚本代码编写的很乱，工作效率不高。

# 吐槽

锐捷的 ePortal Web 认证上了之后，向 InterFace.do?method=getOnlineUserInfo 这个接口中 Post 过去 userIndex 参数会明文显示用户的密码，感觉一点安全性都没有。（集美大学在认证系统升级之后已修复该问题）

以及，我所在的学校在未认证的情况下，53端口(DNS)是可以正常通信的。如果你所在的学校也有类似的情况，也许可以尝试搭建个53端口的代理实现免认证上网。