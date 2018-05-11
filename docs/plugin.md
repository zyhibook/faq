# 扩展开发

> demo地址:https://github.com/akaxincom/openzaly-admin


### 全局说明
* 扩展有唯一请求标识authKey, 请联系站点的管理员获取
* 站点之间交互，获取数据，全部采用的
* 下面用到的域名如果没有改过，默认是http://127.0.0.1:8080，如果有改动，请自行更改

```
$params = file_get_contents("php://input");
```
### 获取站点设置
> 请求地址: http://127.0.0.1:8080/hai/site/getConfig
> 
> 请求方法: \Library\ManageBasic::getBasicConfig
> 


| Left Aligned  | Center Aligned  | Right Aligned |
|:------------- |:---------------:| -------------:|
| col 3 is      | some wordy text |         $1600 |
| col 2 is      | centered        |           $12 |
| zebra stripes | are neat        |            $1 |

<table>
<tr>
<th>参数</th>
<th>参数类型</th>
<th>是否必填</th>
<th>描述</th>
</tr>
<tr>
<th> params </th>
<th> string </th>
<th>是</th>
<th>接收到site传递过来的数据</th>
</tr>
<tr>
<th>getConfigUrl</th>
<th>string</th>
<th>是</th>
<th>默认的请求地址，或者更改后的请求地址</th>
</tr>
</table>

