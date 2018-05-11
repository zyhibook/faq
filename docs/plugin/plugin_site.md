
### 全局说明
* 扩展有唯一请求标识autdKey, 请联系站点的管理员获取
* 站点之间交互，获取数据，全部采用的
* 如果没有修改过InnerAPI服务器地址，默认是http://127.0.0.1:8080，如果有改动，请自行更改

```
$params = file_get_contents("php://input");
```

**请求参数** 

> 请求地址: http://127.0.0.1:8080/hai/site/getConfig
> 
> 请求方法: \Library\ManageBasic::getBasicConfig
>
> 

<table>
<tr>
<th>参数</th>
<th>参数类型</th>
<th>是否必填</th>
<th>描述</th>
</tr>
<tr>
<td> params </td>
<td> string </td>
<td> 是</td>
<td> 接收到site传递过来的数据</td>
</tr>
<tr>
<td>getConfigUrl</td>
<td>string</td>
<td>是</td>
<td>默认的请求地址，或者更改后的请求地址</td>
</tr>
</table>

**响应参数**

<table >
<tr>
<th> 参数</th>
<th> 参数类型</th>
<th> 是否必填</th>
<th> 描述</th>
</tr>
<tr>
<td> site_ip </td>
<td> string </td>
<td> 是</td>
<td> 站点服务器地址</td>
</tr>
<tr>
<td> site_port </td>
<td> string </td>
<td> 是</td>
<td> 站点端口号</td>
</tr>
<tr>
<td> site_http_address </td>
<td> string </td>
<td> 是</td>
<td> 站点与http通讯的ip地址</td>
</tr>
<tr>
<td> site_http_port </td>
<td> string </td>
<td> 是</td>
<td> 站点与http通讯的端口号</td>
</tr>
<tr>
<td> site_name </td>
<td> string </td>
<td> 是</td>
<td> 站点名称</td>
</tr>
<tr>
<td> site_logo </td>
<td> string </td>
<td> 是</td>
<td> 站点logo</td>
</tr>
<tr>
<td> site_desc </td>
<td> string </td>
<td> 是</td>
<td> 站点描述</td>
</tr>
<tr>
<td> realname_status </td>
<td> string </td>
<td> 是</td>
<td> 实名状态</td>
</tr>
<tr>
<td> invite_code_status </td>
<td> string </td>
<td> 是</td>
<td> 是否开启邀请码，0关闭，1开启</td>
</tr>
<tr>
<td> pic_size</td>
<td> string </td>
<td> 是</td>
<td> 站点图片支持最大尺寸</td>
</tr>
<tr>
<td> pic_patd </td>
<td> string </td>
<td> 是</td>
<td> 站点图片存储路径</td>
</tr>
<tr>
<td> group_members_count </td>
<td> string </td>
<td> 是</td>
<td> 群成员最大数量</td>
</tr>
<tr>
<td> u2_encryption_status </td>
<td> string </td>
<td> 是</td>
<td> 是否开启二人绝密聊天</td>
</tr>
<tr>
<td> push_client_status </td>
<td> string </td>
<td> 是</td>
<td> 是否开启推送</td>
</tr>
<tr>
<td> log_level </td>
<td> string </td>
<td> 是 </td>
<td> 站点的日志级别，DEBUG, INFO, ERROR</td>
</tr>
<tr>
<td> subgenus_admin </td>
<td> string </td>
<td> 是</td>
<td> 站点子管理员，拥有除了添加字管理员的所有设置权限</td>
</tr>
</table>