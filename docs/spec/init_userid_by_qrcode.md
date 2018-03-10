# 扫码授权登录原理

在初始化手机身份时，大家可以放心的使用扫码授权设备功能，整个过程非常安全，原理如下：


具体过程如下：

1. 本机设备生成随机密钥Key(长度：256bit)，在本机展示一个二维码
    * **重要** 此二维码绝对不要随意泄露给任何第三方！
2. 对端设备扫描二维码，将用户身份对应公私钥使用密钥Key加密后，存放至远端临时存储（放到大街上都可以）。
    * 加密算法为AES[^1]（Advanced Encryption Standard）
    * 一次一密，随机生成。
3. 本机设备获取远端数据后的，使用密钥Key进行解密，在本机以此身份登录。

## 相关连接

[^1]: [Advanced Encryption Standard](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)
