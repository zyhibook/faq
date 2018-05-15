# 扩展开发

> 完善中，暂时不建议使用
>
> 欢迎使用app访问 demo.akaxin.com 体验扩展


#### 名词解释：
* 客户端 <b>Client</b>
* 站点服务器 	<b>siteServer</b>
* 扩展服务器  <b>pluginServer</b>
* 扩展密钥 <b>authKey</b>
* 请求扩展页面接口 <b>ApiPluginPageRequest</b>
* 请求数据接口 <b>ProxyPluginPackage</b>

### <b> 扩展是什么？</b>

在app中，我们很难满足于各个行业的各种需求，所以我们开放API，让大家定制满足自己需求的功能。这类满足于自己需求并且恰到好处的展示在app上，方便用户使用的功能，我们统称为扩展。

### <b>扩展展示在哪里？</b>

在当前的系统中，有两处地方展示扩展。

* 首页，消息列表上方（地址栏下方）
	* 本区域最多展示4个扩展。如果扩展数多于4个，最后一个改为更多，点击更多后，进入一个新页面选择扩展。

* 聊天界面（私聊+群聊），+号 扩展区域。(待开发)

### <b>扩展的展示方式？</b>

目前扩展只支持打开新的webView的方式展示。

### <b>扩展的定义</b>

```
message Plugin {

  string id 		= 1;
  string name 		= 2;
  string url_page   = 3;
  string api_url 	= 4;
  string icon 		= 5;
  string auth_key 	= 6;
  string allowed_ip = 7;
  int position 		= 8;
  int order 		= 9;

  PluginDisplayMode display_mode 	 = 10;
  PermissionStatus permission_status = 11;
}
```
* <b>id</b> 针对特定的site, id是唯一的
* <b>name</b> 扩展的名字，同一个站点上扩展的名字是唯一的
* <b>url_page</b> 落地页地址
	* value= https://www.google.com 以http或https开头，客户端直接以url_page作为网址渲染webview
	* value= main，代表通过接口请求main页面
	* value=   , 空代表代表通过接口请求空页面（pluginServer自己把空返回默认主页）
* <b>api_url</b> 请求扩展服务器的地址
	* 只能以http或者https开头，如无则默认为http
	* 该值是server用于转发请求，不允许传递此值到客户端。如复用此结构必须在传递给客户端之前将此值置空。
* <b>icon</b> 扩展图标，展示在界面上
	* 如果以http(s)开头，代表这是一个http(s)协议的文件。
	* 如果不是http(s)开头，client通过给定的方法下载图片
* <b>auth_key</b> 扩展密钥
	* site生成，16个随机的字符串，用于数据的加解密
* <b> allowed_ip</b> 允许访问的ip地址
* <b> position</b>  扩展展示的位置，首页扩展，或者消息扩展
* <b>order</b> 描述顺序，数字越小，排列越靠前
* <b>display_mode</b> 展示方式  目前只支持打开新的webView,后续会加入其它的展示方式
* <b>permission_status</b> 可用范围状态


### <b>Client和pluginServer如何交互？</b>

#### 显示扩展内容

client 通过ApiPluginPageRequest请求转发到siteServer，siteServer收到这个请求之后，将加密后的数据，转发给pluginServer的api_url.

```
message ApiPluginPageRequest {
  //插件ID
  string plugin_id = 1;  
  // 页面名称，为空则为主页
  // page = /index.php 可以为一个界面
  // page = /api/getfriendlist  也可以为一个api，跳转到指定的page，根据扩展的url配置情况
  string page = 2;
  //跳转界面可能需要的其他参数
  string params = 3;
}

message ApiPluginPageResponse {
	string data = 1;
	map<string, string> cookie = 2;		//客户端需要的cookie
}

```

#### Client请求扩展API

下面两种方式，任选其一

* 直接ajax执行请求，由扩展决定
* 调用ApiPluginProxyRequest接口，由site转发。

```
message ApiPluginProxyRequest {
  string plugin_id = 1;//插件ID
  string api = 2;//插件执行的接口
  string params = 3; //调用接口所需参数
}

message ApiPluginProxyResponse {
  bytes data = 1;//返回的数据
  map<string, string> cookie = 2;//客户端需要的cookie
}

```

* params 是扩展自己拼好，由客户端转发回来的数据，格式自己定义

### <b>pluginServer和siteServer交互</b>

siteServer将Client的请求，封装PluginHeaderKey之后，整体使用authKey加密后，原封不动的传递给pluginServer。pluginServer获取数据之后，使用同样的authKey解密数据。

```
// site 与plugin之间交互传输的package包
message ProxyPluginPackage {
	map <int32, string> plugin_header = 1; //header
	string data = 2;
	core.ErrorInfo error_info = 3; //error信息
}

enum PluginHeaderKey {
	CLIENT_VERSION = 0;
	CLIENT_SITE_USER_ID = 1; //当前客户端用户ID
	CLIENT_SITE_SESSION_ID = 2; //当前用户的sessionID
	PLUGIN_REFERER = 3; //使用zaly:goto
	PLUGIN_TIMESTAMP = 4; //单位ms
	PLUGIN_ID = 5; //扩展的ID
}

```

* data  在赋值之前先base64
* authKey 扩展密钥 通过【管理后台】>【扩展管理】>【添加扩展】，可以看到authKey







