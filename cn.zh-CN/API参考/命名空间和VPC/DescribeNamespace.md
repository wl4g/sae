# DescribeNamespace {#doc_api_sae_DescribeNamespace .reference}

查询命名空间详细信息

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=sae&api=DescribeNamespace&type=ROA&version=2019-05-06)

## 请求头 {#requestHeadList .section}

该接口使用公共请求头，无特殊请求头。请参见公共请求参数文档。

## 请求语法 {#requestGrammer .section}

```
GET /pop/v1/paas/namespace HTTP/1.1
```

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|NamespaceId|String|是|cn-beijing:test|命名空间ID

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|接口状态或 POP 错误码

 |
|Data| | |命名空间信息

 |
|NamespaceDescription|String|desc|命名空间描述

 |
|NamespaceId|String|cn-beijing:test|命名空间ID

 |
|NamespaceName|String|name|命名空间名称

 |
|RegionId|String|cn-beijing|地域

 |
|ErrorCode|String|success|错误码

 |
|Message|String|success|附加信息

 |
|RequestId|String|00000000-0000-0000-0000-000000000000|请求ID

 |
|Success|Boolean|true|是否成功

 |
|TraceId|String|000000000000000000000000000000|调用链ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
GET /pop/v1/paas/namespace HTTP/1.1
公共请求头
{
  "NamespaceId": "cn-beijing:test"
}
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeNamespaceResponse>
	  <Data>
		    <NamespaceName>test</NamespaceName>
		    <RegionId>cn-beijing</RegionId>
		    <NamespaceDescription>test</NamespaceDescription>
		    <NamespaceId>cn-beijing:test</NamespaceId>
	  </Data>
	  <Message>success</Message>
	  <RequestId>00000000-0000-0000-0000-000000000000</RequestId>
	  <TraceId>000000000000000000000000000000</TraceId>
	  <ErrorCode>success</ErrorCode>
	  <Success>true</Success>
	  <Code>200</Code>
</DescribeNamespaceResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"NamespaceName":"test",
		"RegionId":"cn-beijing",
		"NamespaceDescription":"test",
		"NamespaceId":"cn-beijing:test"
	},
	"Message":"success",
	"RequestId":"00000000-0000-0000-0000-000000000000",
	"TraceId":"000000000000000000000000000000",
	"Success":true,
	"ErrorCode":"success",
	"Code":200
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/sae)查看更多错误码。

