# 注意事项

<!-- toc -->

## 数据格式

所有接口返回``JSON``格式具有统一的一级结构，样例：

``` json
{
  "status":201,
  "message":"succ",
  "debug":"succ\u0020accepted\u0020repeate\u003a20110607171326165221",
  "attachment":"\u6b22\u8fce\u6ce8\u518c"
}
```

为使中文能在低版本的IE中显示，中文编码采用``UNICODE``编码。
接口中有四个字段，分别是：

| 字段名称 |  含义  | 层次 | 约束 | 备注 |
| ----- | ----- | ----- | ----- | ---- |
| ``status`` | 响应码 | 一级 | 必选 | |
| ``message`` | 响应信息 | 一级 | 必选 | |
| ``debug`` | 调试信息 |  一级 |  可选 | |
| ``attachment`` | 附件信息 | 一级 | 可选 | 复合结构，具体内容，依据不同接口而不同 |

## 编码协商

所有接口提交时，输入参数注意编码问题。服务端默认采用``UTF-8``编码。

当然服务端支持输入参数编码协商制。具体规则：

- 如果是``GET``方法提交的，可通过指定查询参数：``ClientCharset=UTF-8`` 或 ``ClientCharset=GBK`` 的形式告诉服务端；该方式主要适用于JSONP的请求。

- 如果是``POST``方法提交的，则必须通过设置HTTP头，方式有两种：
 - 标准的： ``Content-Type=text/html;charset=UTF-8``；  
 - 自定义：``ClientCharset=UTF-8`` ；   

**注意**：

``POST``方法提交的不支持查询参数中指定 ``ClientCharset=UTF-8``


## 测试环境

- 测试主机： passport.example.net
