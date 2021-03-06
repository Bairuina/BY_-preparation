> https://blog.csdn.net/qq_42364543/article/details/107793441

+ HTTP是超文本传输协议，信息是明文传输，HTTPS则是具有安全性的SSL/TLS加密传输协议
+ HTTP和HTTPS使用的是完全不同的连接方式，用的端口也不一样，前者是80，后者是443
+ HTTP的连接很简单，是无状态的；HTTPS协议是由SSL/TLS+HTTP协议构建的可进行加密传输、身份认证的网络协议，比HTTP协议安全。
+ HTTPS协议需要到CA申请证书，一般免费证书较少，因而需要一定费用

## HTTPS特点
基于HTTP协议，通过SSL或TLS提供加密处理数据、验证对方身份以及数据完整性保护
+ 内容加密：采用混合加密技术，中间者无法直接查看明文内容
+ 验证身份：通过证书认证客户端访问的是自己的服务器
+ 保护数据完整性：防止传输的内容被中间人冒充或者篡改
>https://www.cnblogs.com/czsy/p/10849159.html
>https://www.jianshu.com/p/e30a8c4fa329
## HTTP加密流程
+ HTTPS是通过SSL(安全套接层)和TLS(安全传输协议)的组合使用，加密TCP载荷即HTTP报文内容，
+ 同时通过不对称密钥方式认证身份，保证传输的安全可靠
+ 即： HTTP + 加密 + 认证 + 完整性保护 = HTTPS


+ 原本HTTP先和TCP（假定传输层是TCP协议）直接通信，
+ 而加了SSL后，就变成HTTP先和SSL通信，再由SSL和TCP通信，
+ 相当于SSL被嵌在了HTTP和TCP之间
+ HTTPS 是身披 SSL 外壳的 HTTP

### 共享密钥加密 （对称密钥加密） 
采用的是使用相同密钥对报文进行加密解密
### 公开密钥加密 （非对称密钥加密）
发送密文的一方使用公开密钥进行加密处理，对方收到被加密的信息后，再使用自己的私有密钥进行解密

公开密钥比共享密钥要慢 综合一下他们两者的优缺点，使他们共同使用 这也是HTTPS采用的加密方式
在交换密钥阶段使用公开密钥加密方式，之后建立通信交换报文阶段则使用共享密钥加密方式


## HTTPS协议的缺点
+ https握手阶段比较费时，会使页面加载时间延长50%，增加10%~20%的耗电。
+ https缓存不如http高效，会增加数据开销。
+ SSL证书也需要钱，功能越强大的证书费用越高。
+ SSL证书需要绑定IP
+ 网络负载会变慢 消耗服务器和客户端的硬件资源，导致负载增强
+ 加密通信会消耗更多的 CPU 及内存资源
 
## HTTP教程：
https://www.runoob.com/http/http-tutorial.html
+ HTTP 简介
+ HTTP 消息结构
+ HTTP 方法
+ HTTP 头信息
+ HTTP 状态码