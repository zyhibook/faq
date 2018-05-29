# Akaxin 扩展体系

Akaxin 内置一套完整、易用的扩展体系，方便大家在聊天的基础上，定制、完善的自己的产品业务，为你的业务、产品注入强大的生命力。


## 开发模式

扩展的页面是广泛流行的网页，即html+css+javascript，对于绝大多数同学来说，都能直接上手。

Akaxin的扩展有两种模式：

* HTTP模式
* RESP模式


### HTTP模式

纯网页模式很好理解，你可以直接把现在已有的网站，直接嵌入站点中，便可直接使用。

> 不要随意嵌入第三方的网页，因为客户端会向扩展的Webview中设置用户的session，会被网页服务端程序获取。


### RESP模式

> 待介绍。管理平台本身就是RESP模式的扩展


## 接口大全

### 站点后端接口

站点后端提供的接口，名为InnerAPI。供扩展服务器向主服务器查询、操作各类数据。

每一个接口，都需要Request与Response。大家可以查阅 [此PHP代码案例](https://github.com/akaxincom/akaxin-plugin-sdk/blob/master/sdk-php/demo-php.php) ，来了解交互过程。

> Request的代码注释里，包含接口的用途。

[PHP接口大全](https://github.com/akaxincom/akaxin-plugin-sdk/tree/master/sdk-php/Akaxin/Proto/Plugin)

**SDK**

* PHP：[https://github.com/akaxincom/akaxin-plugin-sdk](https://github.com/akaxincom/akaxin-plugin-sdk)


### Javascript接口

> 待完善


<!--
开发教程
====

下面我们通过一个实际例子，来说明扩展的开发过程。

我们以【心有灵犀】这个社交小游戏为例，来讲解Akaxin扩展的开发过程，这个小游戏源码，大家可以来这里下载。

现在，我们希望在站点内集成这个扩展功能。

* HTTP模式教程
* RESP模式教程


HTTP模式教程
====

#### 页面加载

我们直接在后台进行配置，便可以加载页面了，非常方便。

url_page: 指的便是这个扩展的页面加载接口。对于Http模式的扩展，系统会直接以这个地址来生成webview，从而加载页面。

#### 用户识别

用户识别是扩展中非常重要的一部分，只有这样，才能使扩展与站点结合在一起，从而产生巨大的动能。

在生成Webview的同时，系统会向webview注入一个名为sessionid的cookie，而扩展后台可以拿着session与site的inner-api通讯，以得知此用户的身份。

#### 页面跳转

对于HTTP模式的页面，页面跳转就不介绍了，直接A标签。如果想跳转到外部，可以参考此文档构造URL，调用此JS来完成跳转。 -->
