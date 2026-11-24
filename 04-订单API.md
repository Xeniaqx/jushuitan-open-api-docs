# 聚水潭开放平台 · 订单API（线下版）

> 抓取日期：2026-11-23  
> 分类：订单API（docType=4）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=4&docId=1497

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 订单反取消 | `/open/webapi/orderapi/modifyorder/uncancels` | 1497 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=1497) |
| 修改自有商城订单收件人信息 | `/open/jushuitan/orderaddress/update` | 1435 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=1435) |
| 修改发票信息 | `/open/webapi/orderapi/orderinvoice/saveorderinvoicev2` | 1396 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=1396) |
| 修改订单快递 | `/open/webapi/orderapi/modifyorder/modifyorderlc` | 1367 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=1367) |
| 修改订单卖家备注（按线上单号） | `/open/webapi/orderapi/modifyorder/saveremark` | 944 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=944) |
| 订单指定发货仓 | `/open/orders/modifywms/upload` | 362 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=362) |
| 订单上传(商家自有商城、跨境线下) | `/open/jushuitan/orders/upload` | 18 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=18) |
| 订单转异常 | `/open/webapi/orderapi/questionorder/questions` | 263 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=263) |
| 订单拆分 | `/open/jushuitan/drporder/split` | 233 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=233) |
| 修改订单备注旗帜(会同步至平台) | `/open/order/remark/flag/update` | 214 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=214) |
| 修改订单卖家备注（按内部单号） | `/open/jushuitan/order/remark/upload` | 196 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=196) |
| 通过订单号修改 便签丨线下备注 | `/open/order/node/soid/set` | 118 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=118) |
| 订单标签（新增/移除） | `/open/jushuitan/order/label/upload` | 72 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=72) |
| 订单发货-新 | `/open/order/sent/upload` | 62 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=62) |
| 订单查询 | `/open/orders/single/query` | 22 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=22) |
| 订单取消-按内部单号取消 | `/open/jushuitan/orderbyoid/cancel` | 19 | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=19) |

## 目录

- [订单反取消](#订单反取消)
- [修改自有商城订单收件人信息](#修改自有商城订单收件人信息)
- [修改发票信息](#修改发票信息)
- [修改订单快递](#修改订单快递)
- [修改订单卖家备注（按线上单号）](#修改订单卖家备注按线上单号)
- [订单指定发货仓](#订单指定发货仓)
- [订单上传(商家自有商城、跨境线下)](#订单上传商家自有商城跨境线下)
- [订单转异常](#订单转异常)
- [订单拆分](#订单拆分)
- [修改订单备注旗帜(会同步至平台)](#修改订单备注旗帜会同步至平台)
- [修改订单卖家备注（按内部单号）](#修改订单卖家备注按内部单号)
- [通过订单号修改 便签丨线下备注](#通过订单号修改-便签丨线下备注)
- [订单标签（新增/移除）](#订单标签新增移除)
- [订单发货-新](#订单发货-新)
- [订单查询](#订单查询)
- [订单取消-按内部单号取消](#订单取消-按内部单号取消)

---

## 订单反取消

`/open/webapi/orderapi/modifyorder/uncancels`

| 项 | 内容 |
|---|---|
| 接口名称 | 订单反取消 |
| 接口路径 | `/open/webapi/orderapi/modifyorder/uncancels` |
| docType / docId | 4 / 1497 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=1497 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/orderapi/modifyorder/uncancels` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/orderapi/modifyorder/uncancels` |


### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| order_ids | array | 是 |  | 内部订单号，最大50条 |
| order_ids[] | number | 否 | 297802923 |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | array | 否 |  | 执行结果 |
| data[] | object | 否 |  |  |
| data[].order_id | number | 是 |  | 内部单号 |
| data[].success | boolean | 是 |  | 是否执行成功 |
| data[].message | string | 是 |  | 错误信息 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "order_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": [
    {
      "success": true,
      "message": "",
      "order_id": 0
    }
  ],
  "request_id": ""
}
```


### 异常示例

_无_


---

## 修改自有商城订单收件人信息

`/open/jushuitan/orderaddress/update`

| 项 | 内容 |
|---|---|
| 接口名称 | 修改自有商城订单收件人信息 |
| 接口路径 | `/open/jushuitan/orderaddress/update` |
| docType / docId | 4 / 1435 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=1435 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/orderaddress/update` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/orderaddress/update` |


### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| o_id | number | 是 |  | 内部订单号 |
| shop_id | number | 是 |  | 店铺编码 |
| receiver_state | string | 否 |  | 收件人-省 |
| receiver_city | string | 否 |  | 收件人-市 |
| receiver_district | string | 否 |  | 收件人-区 |
| receiver_address | string | 否 |  | 收件人地址 |
| receiver_name | string | 否 |  | 收件人姓名 |
| receiver_phone | string | 否 |  | 联系电话 |
| receiver_mobile | string | 否 |  | 联系手机号 |
| receiver_country | string | 否 |  | 国家 |
| receiver_zip | string | 否 |  | 邮编 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  |  |
| msg | string | 是 |  |  |
| data | object | 是 |  |  |
| data.data | boolean | 是 |  |  |
| data.code | number | 是 |  |  |
| data.issuccess | boolean | 是 |  |  |
| data.msg | string | 是 |  |  |

### 请求示例

```json
{
  "receiver_state": "",
  "shop_id": 0,
  "receiver_zip": "",
  "receiver_city": "",
  "receiver_district": "",
  "o_id": 0,
  "receiver_address": "",
  "receiver_name": "",
  "receiver_country": "",
  "receiver_phone": "",
  "receiver_mobile": ""
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "msg": "",
    "code": 0,
    "data": true,
    "issuccess": true
  }
}
```


### 异常示例

```json
{
  "code": 120,
  "msg": "错误信息",
  "request_id": "xxxxxxxxx",
  "data": "{}/[]"
}
```


---

## 修改发票信息

`/open/webapi/orderapi/orderinvoice/saveorderinvoicev2`

| 项 | 内容 |
|---|---|
| 接口名称 | 修改发票信息 |
| 接口路径 | `/open/webapi/orderapi/orderinvoice/saveorderinvoicev2` |
| docType / docId | 4 / 1396 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=1396 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/orderapi/orderinvoice/saveorderinvoicev2` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/orderapi/orderinvoice/saveorderinvoicev2` |


### 接口说明

接口每次请求最多传入2000个发票信息，如果传入的发票信息中有不正确的发票抬头（抬头为空或者长度超过50）会返回报错

### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| bu | string | 是 | oms | 业务方简称，比如：KA,OMS等等，可以自定义，建议为业务方字母缩写 |
| invoices | array | 是 |  | 发票信息 |
| invoices[] | object | 否 |  |  |
| invoices[].account | string | 否 | 397475356186 | 开户账号，最大长度50 |
| invoices[].address | string | 否 | 2浙江省杭州市滨江区长河街道滨安路650号1幢八层802室 | 地址，最大长度500 |
| invoices[].bank | string | 否 | 2中国银行杭州市星光大道支行 | 开户行，最大长度50 |
| invoices[].buyerTaxNo | string | 否 | 191330108MA2CEN4J13 | 税号，最大长度25 |
| invoices[].email | string | 否 | hesui@jushuitan.com | 邮箱，最大长度100 |
| invoices[].invoiceAmount | number | 否 | 232 | 发票金额 |
| invoices[].invoiceKind | string | 否 | 电子增值税 | 发票类型,可选值为：电子普通、纸质普通、纸质增值税、电子增值税、全电普通、全电增值税 |
| invoices[].invoiceTitle | string | 是 | 上海聚水潭网络科技有限公司杭州分公司 | 发票抬头，最大长度50 |
| invoices[].phone | string | 否 | 13918432427 | 电话，最大长度50 |
| invoices[].shopId | number | 是 | 10402009 | 店铺ID |
| invoices[].soId | string | 是 | 4049454061208293704 | 线上单号，最大长度50 |
| invoices[].titleType | string | 否 | 个人 | 抬头类型，单位，个人 |
| invoices[].userAddress | string | 否 |  | 联系人地址，最大长度500 |
| invoices[].userName | string | 否 | jack | 联系人姓名，最大长度50 |
| invoices[].userPhone | string | 否 | 343444334 | 联系人电话，最大长度50 |
| invoices[].invoiceType | string | 否 | 蓝票 | 红票、蓝票 |
| invoices[].applyTime | string | 否 |  | 申请时间，如：2025-12-10 15:02:55 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0代表成功 |
| data | object | 否 |  |  |
| data.errors_dic | null | 否 |  |  |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "bu": "oms",
  "invoices": [
    {
      "address": "2浙江省杭州市滨江区长河街道滨安路650号1幢八层802室",
      "invoice_title": "上海聚水潭网络科技有限公司杭州分公司",
      "user_name": "jack",
      "user_address": "",
      "invoice_amount": 232,
      "title_type": "个人",
      "shop_id": 10402009,
      "bank": "2中国银行杭州市星光大道支行",
      "invoice_kind": "电子",
      "buyer_tax_no": "191330108MA2CEN4J13",
      "phone": "13918432427",
      "so_id": "4049454061208293704",
      "user_phone": "343444334",
      "invoice_type": "蓝票",
      "account": "397475356186",
      "email": "hesui@jushuitan.com"
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "errors_dic": ""
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 修改订单快递

`/open/webapi/orderapi/modifyorder/modifyorderlc`

| 项 | 内容 |
|---|---|
| 接口名称 | 修改订单快递 |
| 接口路径 | `/open/webapi/orderapi/modifyorder/modifyorderlc` |
| docType / docId | 4 / 1367 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=1367 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/orderapi/modifyorder/modifyorderlc` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/orderapi/modifyorder/modifyorderlc` |


### 接口说明

一次请求最大处理50条订单

### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| order_lcs | array | 是 |  |  |
| order_lcs[] | object | 否 |  |  |
| order_lcs[].oid | number | 是 | 296828626 | 订单号 |
| order_lcs[].lc_id | string | 是 | ZTO | 快递公司 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 |  | 执行结果 |
| msg | string | 是 |  | 执行信息 |
| data | object | 是 |  |  |
| data.fail_orders | array | 是 |  | 失败的订单 |
| data.fail_orders[] | object | 否 |  |  |
| data.fail_orders[].oid | string | 是 |  | 内部订单号 |
| data.fail_orders[].msg | string | 是 |  | 失败原因 |

### 请求示例

```json
{
  "order_lcs": [
    {
      "lc_id": "ZTO",
      "oid": 296828626
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": {
    "fail_orders": [
      {
        "msg": "",
        "oid": ""
      }
    ]
  }
}
```


### 异常示例

_无_


---

## 修改订单卖家备注（按线上单号）

`/open/webapi/orderapi/modifyorder/saveremark`

| 项 | 内容 |
|---|---|
| 接口名称 | 修改订单卖家备注（按线上单号） |
| 接口路径 | `/open/webapi/orderapi/modifyorder/saveremark` |
| docType / docId | 4 / 944 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=944 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/orderapi/modifyorder/saveremark` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/orderapi/modifyorder/saveremark` |


### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| so_id | string | 是 | S240606144136663 | 线上单号 |
| remark | string | 是 | jialan | 备注 |
| is_append | boolean | 是 | true | 是否追加 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | object | 是 |  |  |

### 请求示例

```json
{
  "is_append": true,
  "so_id": "S240606144136663",
  "remark": "jialan"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": ""
}
```


### 异常示例

_无_


---

## 订单指定发货仓

`/open/orders/modifywms/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 订单指定发货仓 |
| 接口路径 | `/open/orders/modifywms/upload` |
| docType / docId | 4 / 362 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=362 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/orders/modifywms/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/orders/modifywms/upload` |


### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

_官方未提供请求字段 schema。_

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 |  | 返回码 |
| issuccess | string | 是 |  | 是否执行成功 |
| msg | string | 是 |  | 返回信息 |

### 请求示例

```json
[
  {
    "o_id": 332935,
    "wms_co_id": 11310013
  }
]
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "issuccess": ""
}
```


### 异常示例

```json
{
  "code": 120,
  "msg": "错误信息",
  "request_id": "xxxxxxxxx",
  "data": "{}/[]"
}
```


---

## 订单上传(商家自有商城、跨境线下)

`/open/jushuitan/orders/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 订单上传(商家自有商城、跨境线下) |
| 接口路径 | `/open/jushuitan/orders/upload` |
| docType / docId | 4 / 18 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=18 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/orders/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/orders/upload` |


### 接口说明

此接口只能上传商家自有商城、跨境线下、B2B的订单
 接口说明:
 此接口一次最大上传50个订单，重复上传发货前可更新订单（仅支持文档说明中发货前可更新字段），根据shop_id+so_id判断更新
 请开发者严格遵守报文结构

 关于订单及商品状态的问题：
 一、订单线上状态流转：
 [未付款订单]-->等待买家付款-->[买家付款]-->等待卖家发货-->[卖家发货]-->等待买家确认收货-->[买家确认收货，评价]-->交易成功；
 [未付款订单]-->等待买家付款-->[买家未付款]-->[买家取消订单]-->付款前交易关闭；
 [未付款订单]-->等待买家付款-->[买家付款]-->[买家取消订单]-->付款后交易关闭;
 ERP内订单状态流转：
 [未付款订单]-->待付款-->[买家付款]-->已付款待审核-->[审核确认]-->发货中-->[打单拣货]-->已发货

 二、shop_status=WAIT_BUYER_PAY 不带pay支付信息节点；其它状态必须带支付信息
 三、订单上传后订单状态为【异常（等待订单合并）】状态，同个买家在一个店铺中多有个订单就会出现这样的情况，不需要合并转正常单即可
 四、items节点的退款状态refund_status字段：如果是合并订单，退款子单中的商品，请传子单的so_id
 例：A（sku_id1）和B(sku_id2)订单合并后为B(sku_id1+sku_id2)，退款sku_id1请传A(sku_id1-->refund_status:success)

 关于订单中金额的计算：
 1.商品成交总额( item节点中sum(amount) )=单价(item节点中price)*数量 (item节点中qty) 
 2.商品成交总额(item节点中sum(amount) )-优惠金额(通过该公式计算得出，前提是商品成交总金额大于等于应付金额)+运费(freight)=应付 总金额（pay_amount） 
 3.实付金额：pay节点下sum(amount)
 4.商品单价（price）:传值以传的值为准，不传值 结果是amount/qty的结果值
 如果上传的订单部分商品是退款成功的，订单的应付实付金额不要做对应的退款扣减（原进原出）
 密文说明：(不支持传代发订单密文)
 自有商城密文订单上传示例: https://openweb.jushuitan.com/doc?docId=227
 如果订单从电商平台传过来的(淘宝，快手，抖音，拼多多,京东加密平台)，收件人信息是密文传输到聚水潭的自有商城店铺
 full_receive_en_json，receiver_name_en （varchar（200）），receiver_mobile_en（nvarchar（200）），receiver_address 必填
 full_receive_en_json :{\"ReceiverAddress\":\"v6bvpFRKOqi8kavzswq+zyJR0M5oiNWpUVRJ5Zf9EWcMTs422vxQyv7mlJ8wTzDvHvciRCWOGsyAAqs/EaHEfg==\",\"OuterSoId\":\"2216900027194701\",\"ReceiverName\":\"8a1ax1RX/dpP4JAaYfbNFIoSv2B6tD6diRJPU+60ROY=\",\"ReceiverPhone\":\"9Hf/fGGonQAfgr42xUYMXl3zWCMYvW74oSWdyr/+At0=\",\"IdCardNum\":\"f5H2pVMXuj8E+EQMr5r0NmZcIwHI/Dzfonu6BTxtXGM=\",\"MaskPhone\":\"173****5002\",\"MaskName\":\"王*\",\"MaskAddress\":\"观山洞街道湘南学院王仙校区教师公寓\"} 传平台原始密文 OuterSoId（平台的线上订单号）
 receiver_name_en ：平台编码：密文（密文如果超过字段长度 截断处理）如 快手的传 209:****************
 receiver_mobile_en：平台编码：密文（密文如果超过字段长度 截断处理）如 快手的传 209:****************
 receiver_address：平台编码：密文（密文如果超过字段长度 截断处理）如 快手的传 209:****************
 各平台的前缀编码：
 拼多多：050
 淘宝：1
 京东商城：-003
 快手：209
 抖音：147
 关于订单上传提示 {"msg":"执行失败","code":160,"datas":[{"msg":"待支付不下载","issuccess":false,"so_id":"1","o_id":0}]}
1、检查入参报文是否传了pay节点或者支付金额pay_amount与实付金额pay节点的amount不相等
2、检查ERP基础设置-订单 是否设置了第二个选项：只下载已付款订单，如果是，选择下图第一个选项后重新上传订单

 关于订单单商品部分数量退的传值：
 比如A商品数量3，申请退货1。明细入参"refund_qty":1即可，订单会自动拉入异常（线上部分退商品）。不需要传 refund_status（此字段是该条明细所有数量都售后才需要传）
 订单明细也会日志会体现（A(原始数量3)线上退货0->1）。如果同意售后，则ERP里人工把数量从3改成2，然后把订单转到已付款待审核。正常去发货剩余数量。
 如果拒绝售后
 传值"refund_qty":0 订单会取消部分退的异常，自动变成初始的已付款待审核状态。

 更多订单API相关问题请关注常见问题（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=17&currentPage=1&pageSize=20

### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

_官方未提供请求字段 schema。_

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 是 |  | 数据集合 |
| data.datas | array | 是 |  |  |
| data.datas[] | object | 否 |  |  |
| data.datas[].o_id | integer | 是 |  | ERP订单界面-内部单号（测试环境是bigint类型） |
| data.datas[].so_id | string | 是 |  | ERP订单界面-线上单号 |
| data.datas[].issuccess | boolean | 是 | true | 是否成功 |
| data.datas[].msg | string | 是 | 成功 | 返回结果描述 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 199 | "msg": "调用太频繁，请稍后再试!" |  |
| 130 | 店铺编号[11223445]对应公司与系统配置的不一致，请检查配置!    /店铺编号不存在 |  |
| 170 | 单号[20220920]物流编码[]物流公司[韵达礼品件]省市区地址，收件人名称和电话必填 |  |
| 170 | 店铺编号[11223344]的站点类型不允许上传! |  |
| 200 | 调用频次超过限制! |  |
| 100 | Token 已超时! |  |
| 140 | 参数不符合规范,请检查传入参数!报文异常提示:[Invalid type. Expected Array but got Object. Line 1, position 1 |  |
| 140 | Invalid type. Expected String but got Integer. Line 1, position 149 |  |
| 140 | 参数不符合规范,请检查传入参数!报文异常提示:[String '' is less than minimum length of 1. Line 1, position 545 |  |
| 160 | {"msg":"执行失败","code":160,"datas":[{"msg":"待支付不下载","issuccess":false,"so_id":"1","o_id":0}]} |  |


### 请求示例

```json
[
  {
    "shop_id": 12556936,
    "so_id": "2022060601",
    "order_date": "2022-03-10 15:24:13",
    "shop_status": "WAIT_SELLER_SEND_GOODS",
    "shop_buyer_id": "2022060601",
    "receiver_state": "Kuala Lumpur",
    "receiver_city": "Kuala Lumpur",
    "receiver_district": "Kuala Lumpur",
    "receiver_address": "No 170 Jalan Sepakat 2 United Garden 58200 kl",
    "receiver_name": "Dorisneoh",
    "receiver_phone": "0126692533",
    "receiver_zip": "58200",
    "pay_amount": 0,
    "freight": 0,
    "remark": "KCL",
    "buyer_message": "KCL",
    "shop_modified": "2022-03-10 15:24:13",
    "l_id": "MM210000578",
    "logistics_company": "其它",
    "labels": "B2",
    "lc_id": "OTHER",
    "items": [
      {
        "sku_id": "2021031920158541",
        "shop_sku_id": "2021031920158541",
        "amount": 0,
        "base_price": 0,
        "qty": 2,
        "name": "【1箱40包】采琪采Queen系列本色抽纸 小包纸巾",
        "outer_oi_id": "443110",
        "batch_id": "17",
        "produced_date": "2022-08-19"
      }
    ],
    "pay": {
      "outer_pay_id": "OONP2021031920213476",
      "pay_date": "2022-03-10 15:24:13",
      "payment": "memall",
      "seller_account": "memall",
      "buyer_account": "0126692533",
      "amount": 0
    },
    "order_ext": {
      "ext_datas": {
        "company_name": "公司名",
        "door_plate": "门牌号"
      },
      "tracking_no": "国际运单号，示例：YT0000000123",
      "tracking_type": "1000",
      "pdf_url": "PDF面单地址，示例：https://XXXXXXXX.pdf",
      "datas": [
        {
          "AutoId": "自增ID",
          "Iid": "款式编码，示例：SKU01",
          "SkuId": "商品编码，示例：SKU010203",
          "SkuCode": "商品Code，示例：SKU010203",
          "Name": "商品名称 ",
          "DeclareNameZN": "报关中文名称，示例：女士衬衫",
          "DeclareNameEN": "报关英文名称，示例：lady dress",
          "DeclareAmount": "报关商品单价，示例：1",
          "DeclareWeight": "报关商品重量，示例：0.1",
          "HsCode": "海关编码，示例：6103320000",
          "PostTaxNum": "行邮税号，示例：04010100",
          "IsBattery": "是否带电，示例：true",
          "IsLiquid": "是否液体，示例：false",
          "IsDisable": "是否禁用，示例：false",
          "Creator": "创建人，示例：XXX",
          "Created": "创建时间，示例：2024-01-01",
          "Modifier": "修改人，示例：XXX",
          "Modified": "修改时间，示例：false",
          "Unit": "单位，示例：个 ",
          "isSetSkubin": "是否拼接仓位，示例：false",
          "IsJoinSkuid": "是否拼接商品编码，示例：false",
          "IsPaste": false,
          "IsMagnetic": "是否带磁，示例：false",
          "IsFluid": "是否液体，示例：false",
          "IsGetPrice": "是否取实际售价，示例：false",
          "IsGetWeight": "是否取实际重量，示例：true",
          "SpecialAttr": "特殊属性",
          "Country": "通用，示例：通用",
          "TempName": "模板名称",
          "TempId": "模板ID",
          "IsDefault": "是否默认，示例：true",
          "ShopId": "店铺编码",
          "IsOAmount": "是否整单金额，示例：true",
          "Cid": "类目ID",
          "IsPowder": "是否是粉末，示例：false",
          "IsSpecialCargo": "是否特货，示例：false",
          "IsJoinSkubin": "是否拼接商品仓位，示例：false ",
          "SaveType": "保存类型",
          "DeclareType": "报关类别，示例：int  1(模板报关) 2(商品报关) 3(类目报关)"
        }
      ]
    },
    "finance_data": {
      "rebate_fee": 100,
      "product_tax": 1,
      "shipping_tax": 1,
      "other_income": 400,
      "voucher_from_seller": 102,
      "platform_commission": 2,
      "transition_fee": 6,
      "transaction_fee": 4,
      "opaque_bagging_fee": 1,
      "other_expense": 50
    }
  }
]
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {
    "datas": [
      {
        "msg": "成功",
        "issuccess": true,
        "so_id": "202206060111467695",
        "o_id": 30331030
      }
    ]
  }
}
```


### 异常示例

```json
{
  "code": 120,
  "msg": "验证失败!无效签名"
}
```


---

## 订单转异常

`/open/webapi/orderapi/questionorder/questions`

| 项 | 内容 |
|---|---|
| 接口名称 | 订单转异常 |
| 接口路径 | `/open/webapi/orderapi/questionorder/questions` |
| docType / docId | 4 / 263 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=263 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/orderapi/questionorder/questions` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/orderapi/questionorder/questions` |


### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| o_ids | array | 否 |  | 内部订单号 （与线上单号二选一必填一项），最大50个 |
| o_ids[] | number | 否 | 41031566 |  |
| so_ids | array | 否 |  | 线上单号 （与内部单号二选一必填一项），最大50个 |
| so_ids[] | string | 否 |  |  |
| channel | string | 否 | open | 操作人，记录在订单详情日志上，不填写默认open |
| question_type | string | 是 | 缺货 | 异常类型 也支持自定义 |
| question_desc | string | 否 | 接口转入 | 异常描述 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.success | number | 否 |  | 成功数量 |
| data.fail | number | 否 |  | 失败数量 |
| data.message | array | 否 |  | 转异常失败信息 |
| data.message[] | object | 否 |  |  |
| data.message[].id | number | 是 |  | 失败订单编号 |
| data.message[].msg | string | 是 |  | 失败信息 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "o_ids": [],
  "so_ids": [],
  "question_desc": "接口转入",
  "question_type": "缺货",
  "channel": "open"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "fail": 0,
    "success": 0,
    "message": [
      {
        "msg": "",
        "id": 0
      }
    ]
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 订单拆分

`/open/jushuitan/drporder/split`

| 项 | 内容 |
|---|---|
| 接口名称 | 订单拆分 |
| 接口路径 | `/open/jushuitan/drporder/split` |
| docType / docId | 4 / 233 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=233 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/drporder/split` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/drporder/split` |


### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| o_id | string | 是 |  | 内部订单号 |
| split_infos | array | 是 |  | 拆分信息 |
| split_infos[] | array | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | array | 是 |  | 拆分后的内部订单号 |
| data[] | number | 否 |  |  |
| code | string | 是 |  | 返回码0表示成功 |
| issuccess | string | 是 |  | 是否执行成功 |
| msg | string | 是 |  | 返回信息 |

### 请求示例

```json
{
  "split_infos": [
    [
      {
        "oi_id": "28967102",
        "qty": 1
      }
    ]
  ],
  "o_id": "30154994"
}
```


### 响应示例

```json
{
  "data": [
    30285828,
    30285829
  ],
  "code": 0,
  "issuccess": true,
  "msg": "执行成功"
}
```


### 异常示例

```json
{
  "code": 120,
  "msg": "错误信息",
  "request_id": "xxxxxxxxx",
  "data": "{}/[]"
}
```


---

## 修改订单备注旗帜(会同步至平台)

`/open/order/remark/flag/update`

| 项 | 内容 |
|---|---|
| 接口名称 | 修改订单备注旗帜(会同步至平台) |
| 接口路径 | `/open/order/remark/flag/update` |
| docType / docId | 4 / 214 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=214 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/order/remark/flag/update` |
| 正式环境 | `https://openapi.jushuitan.com/open/order/remark/flag/update` |


### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| o_ids | array | 是 |  |  |
| o_ids[] | number | 否 | 3328524 | array	内部单号 |
| remark | string | 是 | 123 | string	备注，传{ClearRemark}为清空 |
| seller_flag | string | 是 | 1 | 旗帜，0,清空旗帜,1,红旗帜,2,黄旗帜,3,绿旗帜,4,蓝旗帜,5,紫旗帜 |
| append_remrk | string | 否 |  | 是否追加备注，默认false |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].order_id | string | 否 |  | 内部单号 |
| data[].flag | string | 否 |  | 是否成功 |
| data[].message | string | 否 |  | 执行描述 |
| data[].exception | string | 否 |  | 无 |
| code | string | 否 |  | 错误码 |
| issuccess | string | 否 |  | 是否执行成功 |
| msg | string | 否 |  | 执行描述 |

### 请求示例

```json
{
  "o_ids": [],
  "seller_flag": "1",
  "remark": "123",
  "append_remrk": ""
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": [
    {
      "exception": "",
      "flag": "",
      "message": "",
      "order_id": ""
    }
  ],
  "issuccess": ""
}
```


### 异常示例

```json
{
  "code": 120,
  "msg": "错误信息",
  "request_id": "xxxxxxxxx",
  "data": "{}/[]"
}
```


---

## 修改订单卖家备注（按内部单号）

`/open/jushuitan/order/remark/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 修改订单卖家备注（按内部单号） |
| 接口路径 | `/open/jushuitan/order/remark/upload` |
| docType / docId | 4 / 196 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=196 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/order/remark/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/order/remark/upload` |


### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| o_id | integer | 是 |  | 内部订单号 |
| remark | string | 是 |  | 卖家备注 每次都是覆盖系统里的卖家备注，最大长度最大长度500 |
| is_append | boolean | 否 |  | 是否追加备注，true=是，false=否，非必填，默认值false |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 |  | 0 代表成功 |
| issuccess | string | 否 |  | 是否成功 |
| msg | string | 否 |  | 描述 |

### 请求示例

```json
{
  "o_id": 3205549,
  "remark": "备注cas",
  "is_append": true
}
```


### 响应示例

```json
{
  "code": 0,
  "issuccess": true,
  "msg": "执行成功"
}
```


### 异常示例

```json
{
  "code": 120,
  "msg": "错误信息",
  "request_id": "xxxxxxxxx",
  "data": "{}/[]"
}
```


---

## 通过订单号修改 便签丨线下备注

`/open/order/node/soid/set`

| 项 | 内容 |
|---|---|
| 接口名称 | 通过订单号修改 便签丨线下备注 |
| 接口路径 | `/open/order/node/soid/set` |
| docType / docId | 4 / 118 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=118 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/order/node/soid/set` |
| 正式环境 | `https://openapi.jushuitan.com/open/order/node/soid/set` |


### 接口说明

node 默认传值为 线下备注，如果要传值为 便签，则在值的后面加上英文冒号（便签需要在ERP维护好）

 举例：
 线下备注
 {
 "shop_id":16375536,
 "items":[{
 "o_id":14156490,
 "node":"123"
 }]
 }

 便签（入参123: ，在ERP里不会体现这个冒号 只会显示123）
 {
 "shop_id":16375536,
 "items":[{
 "o_id":14156490,
 "node":"123:"
 }]
 }

### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| shop_id | number | 是 |  | 店铺编号 |
| items | array | 是 |  |  |
| items[] | object | 否 |  |  |
| items[].o_id | number | 否 |  | 内部订单号 （与线上单号必填一个，最大支持10个） |
| items[].so_id | string | 否 |  | 线上单号 （如果内部单号和线下单号不是同一个订单存在都会被修改） |
| items[].node | string | 是 |  | 便签丨线下备注 （如要入参便签 需要在值后面加上英文冒号 另外需ERP里维护好便签 ） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 返回值0代表成功 |
| issuccess | boolean | 是 |  | 是否成功 |
| msg | string | 是 |  | 异常信息描述 |

### 请求示例

```json
{
  "shop_id": 11821401,
  "items": [
    {
      "o_id": 74159,
      "node": "111"
    }
  ]
}
```


### 响应示例

```json
{
  "code": 0,
  "issuccess": true,
  "msg": "执行成功"
}
```


### 异常示例

```json
{
  "code": 120,
  "msg": "错误信息",
  "request_id": "xxxxxxxxx",
  "data": "{}/[]"
}
```


---

## 订单标签（新增/移除）

`/open/jushuitan/order/label/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 订单标签（新增/移除） |
| 接口路径 | `/open/jushuitan/order/label/upload` |
| docType / docId | 4 / 72 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=72 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/order/label/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/order/label/upload` |


### 接口说明

一、商家是新版三方仓
 1.授权如果使用仓储授权(订单是货主的)，入参指定货主编码co_id传负值，wms_co_id传三方仓自己的仓储编码
 示例：
 {
 "o_id": 3459963,
 "labels": [
 "分拣机3号"
 ],
 "co_id": -10077103,
 "action_type": 1,
 "wms_co_id": 10073558
}
 2.授权如果使用货主授权(订单是货主自己的)，入参指定仓储编码wms_co_id传三方仓自己的仓储编码或者0，co_id传货主自己的编码
 示例：
 {
 "o_id": 3459963,
 "labels": [
 "分拣机3号"
 ],
 "co_id": 10077103,
 "action_type": 1,
 "wms_co_id": 10073558
}
 二、商家是改版三放仓
 1.授权如果使用仓储授权（订单是货主的），入参指定货主编码owner_co_id传货主编码,wms_co_id传三方仓自己的仓储编码，co_id传三方仓自己的仓储编码
 示例：
 {
 "o_id": 3459963,
 "labels": [
 "分拣机3号"
 ],
 "owner_co_id": 10077103,
 "action_type": 1,
 "wms_co_id": 10073558,
 "co_id": 10073558
}
 2.授权如果使用货主授权(订单是货主的)，入参指定仓储编码wms_co_id传三方仓自己的仓储编码，co_id传货主自己的编码
 {
 "o_id": 3459963,
 "labels": [
 "分拣机3号"
 ],
 "co_id": 10077103,
 "action_type": 1,
 "wms_co_id": 10073558
}

### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| o_id | integer | 是 |  | 内部订单号 o_id 和 (shop_id, so_id)组合 不能同时为空 |
| shop_id | integer | 是 |  | 店铺编号 |
| so_id | string | 是 |  | 线上单号 |
| labels | array | 是 |  | 标签列表 数量大于0且小于20，单个标签长度10，不可重复 |
| labels[] | string | 否 |  |  |
| action_type | integer | 是 |  | 操作类型，1=新增，2=移除 |
| owner_co_id | number | 否 |  | 货主编码（改版三方仓授权情况需要指定货主） |
| wms_co_id | number | 否 |  | 仓储编码（货主授权情况下需要指定三方仓） |
| co_id | number | 否 |  | 货主编码（新版三方仓授权情况需要指定货主，货主编码传负数） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 是 |  | 状态码 |
| issuccess | boolean | 是 |  | 是否成功 |
| msg | string | 是 |  | 执行结果描述 |

### 请求示例

```json
{
  "shop_id": 0,
  "action_type": 0,
  "so_id": "",
  "o_id": 0,
  "labels": [
    "11",
    "22"
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "issuccess": true
}
```


### 异常示例

```json
{
  "code": 130,
  "issuccess": false,
  "msg": "o_id 和 (shop_id, so_id)组合 不能同时为空"
}
```


---

## 订单发货-新

`/open/order/sent/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 订单发货-新 |
| 接口路径 | `/open/order/sent/upload` |
| docType / docId | 4 / 62 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=62 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/order/sent/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/order/sent/upload` |


### 接口说明

注：此接口将同步发货信息到平台
 用该接口发货之后，将不扣系统里的库存；
 不支持拆单发货，线上平台的订单状态会因为子订单发货而整个订单会变成已发货
 调用该接口发货需要先在系统【物流(快递)公司及打印模板】页面中配置对应的物流公司及编码

 执行成功和执行失败返回的参数格式有差异，详见返回示例（执行成功）和异常示例（执行失败）
 最大支持上传50条

### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| items | array | 是 |  |  |
| items[] | object | 否 |  | data |
| items[].o_id | integer | 是 |  | 内部订单号 |
| items[].shop_id | integer | 是 |  | 店铺编号 |
| items[].so_id | string | 是 |  | 线上单号 |
| items[].lc_name | string | 是 |  | 快递公司 |
| items[].l_id | string | 是 |  | 快递单号；如果选择了跨境物流表示国际运单号 |
| items[].send_by_used_lid | boolean | 否 |  | 是否允许传重复物流单号；默认false不重复 |
| items[].lc_id | string | 是 |  | 快递公司编码 【物流(快递)公司及打印模板】中的物流公司编号 |
| items[].is_un_lid | boolean | 否 |  | 是否跨境物流；选true渠道信息必填 |
| items[].tracking_code | string | 否 |  | 渠道编码 |
| items[].tracking_info | string | 否 |  | 渠道名称 |
| items[].tracking_type | number | 否 |  | 货代id（货代设置中的ID）；默认值可以传1000 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 |  | 错误码 |
| issuccess | boolean | 否 |  | 是否执行成功 |
| msg | string | 否 |  | 执行描述 |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |

### 请求示例

```json
跨境订单发货上传参考示例：
{
"items": [
{
"shop_id": 店铺编码,
"so_id": "订单号",
"lc_name": "跨境物流",
"lc_id": "OTHER.CBDR",
"tracking_code": "UPS",
"tracking_info": "UPS",
"o_id": 内部单号,
"l_id": "111111111111111111111111",
"tracking_type ":1000//这个是”其他”物流商的tracking_type值
}
]
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {
    "data": []
  }
}
```


### 异常示例

```json
{
  "data": [
    {
      "as_id": 0,
      "id": 0,
      "issuccess": false,
      "msg": "店铺订单号[424333087989926495]状态[Sent]不允许发货！",
      "o_id": 70261,
      "so_id": null,
      "outer_as_id": null,
      "oaid": null,
      "order_type": null
    }
  ],
  "code": 160,
  "issuccess": false,
  "msg": "执行失败"
}
```


---

## 订单查询

`/open/orders/single/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 订单查询 |
| 接口路径 | `/open/orders/single/query` |
| docType / docId | 4 / 22 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=22 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/orders/single/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/orders/single/query` |


### 接口说明

系统相关界面：【订单】----订单操作----【订单】
 数据流向： 外部系统 获取聚水潭ERP里的订单数据

 1.关于订单查询不到的问题：
 此接口查询不到淘系和拼多多订单信息
 淘系订单通过奇门获取 ： 奇门自定义场景 （ 淘系平台包含： 淘宝天猫，天猫供销，考拉pop，考拉供应商直发，阿里巴巴，淘工厂，天猫超市，天猫国际直营，阿里健康直营，淘宝定制，淘宝采购，淘宝买菜，银泰喵街， 饿百零售 ）
 拼多多通过方舟获取： 拼多多方舟 （拼多多平台包含：拼多多，拼多多厂家代打） 注：拼多多只能查询到近3个月的订单

 2.关于获取订单收件人信息：
 不支持获取线上平台订单收件人信息（除了“ 跨境线下平台,B2B,其它平台,聚货通,线下店铺,商家自有商城,档口”这些平台之外，其他平台都属于线上平台 ）

 3. 关于订单中金额的计算：
 1.商品成交总额( item节点中sum(amount) )=单价(item节点中price)*数量 (item节点中qty) 
 2.商品成交总额(item节点中sum(amount) )-优惠金额(free_amount)+运费(freight)=应付总金额（pay_amount） 
 3.实付金额：pay节点下sum( is_order_pay为true的 amount)

 4.请求参数中start_ts的说明 ：
 使用ts的查询条件是唯一可避免分页查询过程中因数据变动而导致的漏单问题，原因是该查询条件是数据库中的时间戳，sql server中的 行版本号 。只要当前这条数据在数据库中有变化任何字段变化ts的值都会自增，全表唯一的自增值，非业务上做的时间值更新。使用ts的查询模板
 第一次请求：{" start_ts ":1," is_get_total ":false," page_index ":1," page_size ":100} //第一次请求ts从1开始
 第二次请求：{" start_ts ":传第一次返回的最大ts值," is_get_total ":false," page_index ":1," page_size ":100} //一直请求到查不到比入参ts值本身更大的数据为止。只有start_ts值是变量，其它3个参数值不变

 更多订单API相关问题请关注常见问题（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=17&currentPage=1&pageSize=20

### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| shop_id | integer | 否 | 10208218 | 店铺编号 |
| is_offline_shop | boolean | 否 | false | shop_id为0且is_offline_shop为true查询线下店铺单据 |
| so_ids | array | 否 |  | 线上单号 与时间条件，内部单号不能同时为空，最大限制20条 |
| so_ids[] | string | 否 |  |  |
| modified_begin | string | 否 | 2021-12-02 10:26:25 | 起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与线上单号，内部单号不能同时为空;tips:用时间条件查询由于查询中数据存在变动的可能会由于排序问题引发分页查询漏单的问题，建议使用ts时间戳增量查询的方式 |
| modified_end | string | 否 | 2021-12-09 10:26:25 | 结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与线上单号，内部单号不能同时为空 |
| date_type | number | 否 |  | (0:修改时间modified，2:订单日期order_date，3:发货时间send_date；非必填，默认0) |
| status | string | 否 |  | 订单状态：待付款：WaitPay；发货中：Delivering；被合并：Merged；异常：Question；被拆分：Split；等供销商\|外仓发货：WaitOuterSent；已付款待审核：WaitConfirm；已客审待财审：WaitFConfirm；已发货：Sent；取消：Cancelled |
| page_index | integer | 否 |  | 第几页，从1开始 |
| page_size | integer | 否 |  | 最每页多少条，最大100条 |
| start_ts | integer | 否 |  | ts时间戳，sql server中的行版本号，该字段查询防止分页过程中漏单。查询条件值是大于等于的关系 |
| is_get_total | boolean | 否 |  | 是否查询总条数默认true，如果使用start_ts查询，该值需要传false不返回总条数总页数否则影响查询效率 |
| o_ids | array | 否 |  | 内部订单号 （商家维度下订单信息的唯一值），与时间条件，线上单号不能同时为空 |
| o_ids[] | number | 否 |  |  |
| order_flds | array | 否 |  | 订单自定义查询字段 |
| order_flds[] | string | 否 | volume,package,outer_drp_co_id ,cus_id，logistics_status,drp_amount | 体积,包材,货主分销,货通客户id，o2o订单配送状态（未知；待商家接单；待商家拣货；待呼叫骑手；待骑手接单；待骑手取货；骑手已取货(配送中)；已完成；配送取消；配送异常）,分销支付给供销金额（只有发货后准确） |
| order_item_flds | array | 否 |  | 订单明细自定义查询字段 |
| order_item_flds[] | string | 否 | src_combine_sku_qty,referrer_name,presale_date,drp_price,item_plan_delivery_date,activity_u_id,activity_u_name | 原组合商品数量,达人名称,预售时间,采购价,最晚发货时间,团长id,团长名称 |
| order_types | array | 否 |  | 订单类型 |
| order_types[] | string | 否 | "普通订单","普通订单,供销Plus" |  |
| archive | boolean | 否 | false | 是否查询历史订单：false 否；true是。默认fale |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  |  |
| data.page_size | integer | 否 | 2 | 每页多少条 |
| data.page_index | integer | 否 | 1 | 第几页 |
| data.data_count | integer | 否 | 2 | 总条数 |
| data.page_count | integer | 否 | 1 | 总页数 |
| data.has_next | boolean | 否 | false | 是否有下一页 |
| data.orders | array | 否 |  | 数据集合 |
| data.orders[] | object | 否 |  |  |
| data.orders[].is_cod | boolean | 否 | false | 是否货到付款 |
| data.orders[].l_id | string | 否 |  | 快递单号（发货中的订单查不到，已发货状态物流单号才会回写到订单上） |
| data.orders[].send_date | string | 否 |  | 发货日期 |
| data.orders[].pay_date | string | 否 | 2019-12-16 16:35:28 | 支付时间 |
| data.orders[].freight | string | 否 | 4.0 | 买家支付运费，保留两位小数，单位（元） |
| data.orders[].first_freight | string | 否 |  | 跨境订单-头程运费 |
| data.orders[].outerwms_freight | string | 否 |  | 跨境订单-尾程运费 |
| data.orders[].receiver_address | string | 否 |  | 收货地址 |
| data.orders[].receiver_district | string | 否 |  | 区 |
| data.orders[].wms_co_id | integer | 否 |  | 发货仓编号(当值为0表示主仓) |
| data.orders[].logistics_company | string | 否 |  | 快递公司 |
| data.orders[].as_id | number | 否 |  | 补发换货单对应的售后单号 |
| data.orders[].free_amount | number | 否 |  | 抵扣金额 |
| data.orders[].shop_name | string | 否 | 川梣铺子 | 店铺名称 |
| data.orders[].question_type | string | 否 | 等待订单合并 | 问题类型，仅当问题订单时有效 |
| data.orders[].outer_pay_id | string | 否 | 20210928 | 外部支付单号 |
| data.orders[].so_id | string | 否 | 20210928 | 线上订单号，线上同步过来的订单号，最长不超过20;平台唯一 |
| data.orders[].type | string | 否 | 普通订单 | 订单类型，普通订单；补发订单；分销Plus；供销Plus；换货订单 |
| data.orders[].order_from | string | 否 | open | 订单来源，ERP：手工下单； COPY：复制； MERGE：合并； SPLIT：拆分；拆分还原； MOBILE：京东； IMPORT:导入； drp-s：供销推送； drp-d：分销推送； KWAISHOP：快手；微商城； PINDUODUO；拼多多； TOUTIAOFXG；头条放心购 |
| data.orders[].status | string | 否 | Question | 聚水潭订单状态 待付款：WaitPay；发货中：Delivering；被合并：Merged；异常：Question；被拆分：Split；等供销商\|外仓发货：WaitOuterSent；已付款待审核：WaitConfirm；已客审待财审：WaitFConfirm；已发货：Sent；取消：Cancelled |
| data.orders[].pay_amount | number | 否 |  | 应付金额，保留两位小数，单位（元） |
| data.orders[].shop_buyer_id | string | 否 |  | 买家昵称 |
| data.orders[].open_id | string | 否 |  | 平台买家唯一值，仅限平台已经支持的才会返回 |
| data.orders[].shop_status | string | 否 | 平台订单状态： 等待买家付款=WAIT_BUYER_PAY， 等待卖家发货=WAIT_SELLER_SEND_GOODS,等待买家确认收货=WAIT_BUYER_CONFIRM_GOODS, 交易成功=TRADE_FINISHED, 付款后交易关闭=TRADE_CLOSED,付款前交易关闭=TRADE_CLOSED_BY_TAOBAO； | https://jushuitan.yuque.com/cscvxv/al2cbn/ycunxb?singleDoc#8lWt 《平台订单shop_status字段枚举》 密码：tyuy |
| data.orders[].receiver_mobile | string | 否 |  | 手机 |
| data.orders[].receiver_phone | string | 否 |  | 电话 |
| data.orders[].order_date | string | 否 | 2019-12-15 18:14:26 | 订单日期 |
| data.orders[].question_desc | string | 否 |  | 问题描述 |
| data.orders[].receiver_city | string | 否 |  | 收件信息-市 |
| data.orders[].receiver_state | string | 否 |  | 收件信息-省 |
| data.orders[].receiver_name | string | 否 |  | 收件信息-收件人 |
| data.orders[].o_id | integer | 否 | 38852 | ERP内部订单号，聚水潭生成的订单号，erp唯一 |
| data.orders[].shop_id | integer | 否 | 11690153 | 店铺编号 |
| data.orders[].co_id | integer | 否 | 11053062 | 公司编号 |
| data.orders[].remark | string | 否 |  | 订单备注；卖家备注 |
| data.orders[].package_no | string | 否 |  | 参考号 |
| data.orders[].warehouse_oid | string | 否 |  | 外部单据号 |
| data.orders[].drp_co_id_from | string | 否 |  | 分销商编号 |
| data.orders[].modified | string | 否 | 2021-09-28 16:08:13 | 最后修改时间 |
| data.orders[].labels | string | 否 | 延时发货 | 多标签 |
| data.orders[].paid_amount | number | 否 |  | pay节点的支付金额 |
| data.orders[].platform_free_amount | string | 否 |  | 营收小计：平台补贴；null值处理成了空字符串返回，实际有值的是number类型返回 |
| data.orders[].pay_free_amount | string | 否 |  | 营收小计：支付优惠；null值处理成了空字符串返回，实际有值的是number类型返回 |
| data.orders[].referrer_free_amount | string | 否 |  | 营收小计：达人优惠；null值处理成了空字符串返回，实际有值的是number类型返回 |
| data.orders[].shop_free_amount | string | 否 |  | 营收小计：店铺优惠；null值处理成了空字符串返回，实际有值的是number类型返回 |
| data.orders[].currency | string | 否 |  | 币种 |
| data.orders[].buyer_message | string | 否 |  | 买家留言 |
| data.orders[].lc_id | string | 否 |  | 物流公司编码 |
| data.orders[].cb_total_tax | string | 否 |  | 跨境平台税金 |
| data.orders[].invoice_title | string | 否 |  | 发票抬头 |
| data.orders[].invoice_type | string | 否 |  | 发票类型 |
| data.orders[].invoice_amount | number | 否 |  | 发票金额 |
| data.orders[].buyer_tax_no | string | 否 |  | 发票税号 |
| data.orders[].creator_name | string | 否 |  | 订单业务员 |
| data.orders[].plan_delivery_date | string | 否 |  | 计划发货时间 |
| data.orders[].node | string | 否 |  | 线下备注 |
| data.orders[].receiver_town | string | 否 |  | 收件信息-街道 |
| data.orders[].drp_co_id_to | string | 否 |  | 供销商编号 |
| data.orders[].shop_site | string | 否 | 商家自有商城 | 店铺站点信息 |
| data.orders[].un_lid | string | 否 |  | 国际物流单号 |
| data.orders[].end_time | string | 否 |  | 确认收货时间（仅限头条放心购、拼多多、苏宁易购、快手电商、有赞微商城，如果线上状态为取消，该时间为完结时间） |
| data.orders[].receiver_country | string | 否 |  | 国家代码;（映射关系参考https://openweb.jushuitan.com/doc?docId=225） |
| data.orders[].receiver_zip | string | 否 |  | 邮编 |
| data.orders[].seller_flag | integer | 否 |  | 旗帜(1红旗，2黄旗，3绿旗，4蓝旗，5紫旗） |
| data.orders[].receiver_email | string | 否 |  | 收货邮箱 |
| data.orders[].referrer_id | string | 否 |  | 达人id |
| data.orders[].referrer_name | string | 否 |  | 达人名称 |
| data.orders[].created | string | 否 | 2021-09-28 16:08:13 | 订单创建时间 |
| data.orders[].pays | array | 否 |  | 支付信息 |
| data.orders[].pays[] | object | 否 |  |  |
| data.orders[].pays[].is_order_pay | boolean | 否 | true | 是否支付 |
| data.orders[].pays[].buyer_account | string | 否 | 38 | 支付帐号 |
| data.orders[].pays[].amount | number | 否 | 706.0 | 支付金额 |
| data.orders[].pays[].pay_date | string | 否 | 2019-12-1616:35:28 | 支付时间 |
| data.orders[].pays[].outer_pay_id | string | 否 | 20210928 | 外部支付单号 |
| data.orders[].pays[].pay_id | string | 否 | 37163 | 支付单ID |
| data.orders[].pays[].payment | string | 否 | 微信 | 支付方式 |
| data.orders[].pays[].status | string | 否 |  | 支付状态（None：无 / 未定义；WaitConfirm：待审核；Confirmed：已确认；Finished：完成；Cancelled：作废；Deleted：删除；Lock：锁定；VirtualFinished：虚拟完成；Replace：替换；Reset：重置；Reserve：预占（保留）） |
| data.orders[].pays[].pay_type | string | 否 |  | 支付类型（1 支付，-1 退款） |
| data.orders[].pays[].o_id | number | 否 |  | 内部订单号 |
| data.orders[].items | array | 否 |  | 商品信息 |
| data.orders[].items[] | object | 否 |  |  |
| data.orders[].items[].is_gift | boolean | 否 | false | 是否赠品 |
| data.orders[].items[].sku_id | string | 否 | CY001 | 原始商品编码 |
| data.orders[].items[].name | string | 否 | CY001 | 商品名称 |
| data.orders[].items[].refund_status | string | 否 |  | 申请退款的状态,未申请：none；退款中：waiting；退款成功：success；退款关闭：closed |
| data.orders[].items[].refund_id | string | 否 |  | 退款的唯一单号 |
| data.orders[].items[].price | number | 否 |  | 单价 |
| data.orders[].items[].outer_oi_id | string | 否 | 201911 | 子订单号，商家系统订单商品明细主键，为了拆单合单时溯源，最长不超过50 |
| data.orders[].items[].item_status | string | 否 |  | 商品状态；None：无；WaitPay：待付款；WaitConfirm：等待审核；Question：异常；WaitDeliver：平台接口告知ERP订单项解锁可发货的状态； WaitFConfirm：等待财务审核；Delivering：发货中；WaitOuterSent：等待外仓发货；Sent：已发货；OuterSent：外仓发货；Merged：被合并；Cancelled：用户取消订单；Replaced：被替换（明细）；Split：被拆分； Delete：删除；Lock：锁定；SentCancelled：发货后取消。非必填字段可以为null，不表示任何含义 |
| data.orders[].items[].i_id | string | 否 | 001 | 款式编码 |
| data.orders[].items[].properties_value | string | 否 | CY001 | 属性 |
| data.orders[].items[].oi_id | integer | 否 | 39845 | 子订单号，最长不超过20 |
| data.orders[].items[].amount | number | 否 | 223.0 | 总额 |
| data.orders[].items[].shop_sku_id | string | 否 | 201911 | 店铺商品编码，对应店铺商品资料页面平台店铺商品编码 |
| data.orders[].items[].raw_so_id | string | 否 | 20210928 | 原始线上单号 |
| data.orders[].items[].qty | integer | 否 | 1 | 数量 |
| data.orders[].items[].src_combine_sku_id | string | 否 |  | 原组合装商品编码 |
| data.orders[].items[].is_presale | boolean | 否 |  | 是否预售 |
| data.orders[].items[].base_price | number | 否 | 223.0 | 基本售价（原价） |
| data.orders[].items[].pic | string | 否 |  | 商品图片 |
| data.orders[].items[].sku_type | string | 否 | normal | 商品类型；nomal：普通商品；combine：组合装商品；no_deliver：不发货 |
| data.orders[].items[].shop_i_id | string | 否 |  | 店铺款式编码 |
| data.orders[].items[].buyer_paid_amount  | number | 否 |  | 营收小计：买家实付（以订单详情营收小计区域数据为准） |
| data.orders[].items[].seller_income_amount | number | 否 |  | 营收小计：卖家实收（以订单详情营收小计区域数据为准） |
| data.orders[].items[].referrer_id | string | 否 |  | 达人ID |
| data.orders[].items[].lwh_id | string | 否 |  | 虚拟仓编号 |
| data.orders[].items[].lwh_name | string | 否 |  | 虚拟仓名称 |
| data.orders[].items[].remark | string | 否 |  | 明细备注 |
| data.orders[].items[].produced_date | string | 是 |  | 生产日期 |
| data.orders[].items[].batch_id | string | 是 |  | 批次号 |
| data.orders[].items[].item_ext_data | string | 否 |  | 订单明细扩展字段 |
| data.orders[].skus | string | 否 |  | 商品（商品总数.sku_id*qty） |
| data.orders[].f_weight | number | 否 |  | 实称重量 |
| data.orders[].weight | number | 否 |  | 重量 |
| data.orders[].ts | integer | 否 |  | 数据库行版本号：https://docs.microsoft.com/zh-cn/sql/t-sql/data-types/rowversion-transact-sql?view=sql-server-ver16 |
| data.orders[].buyer_id | string | 否 |  | 买家ID（系统根据shop_buyer_id生成的） |
| data.orders[].buyer_paid_amount  | number | 否 |  | 营收小计：买家实付（仅限ERP订单详情界面能查到的订单） |
| data.orders[].seller_income_amount | number | 否 |  | 营收小计：卖家实收（仅限ERP订单详情界面能查到的订单） |
| data.orders[].chosen_channel | string | 否 |  | 实发快递渠道 |
| data.orders[].channel_name | string | 否 |  | 发货渠道（自定义之后的名称） |
| data.orders[].cb_lc_code | string | 否 |  | 渠道编码 |
| data.orders[].cb_lc_name | string | 否 |  | 发货渠道（自定义之前的名称） |
| data.orders[].link_o_id | number | 否 |  | 被合并被拆分的订单内部单号 |
| data.orders[].merge_so_id | string | 否 |  | 合并线上订单号 |
| data.orders[].shipment | string | 否 |  | 买家指定物流 |
| data.orders[].sign_time | string | 否 |  | 预计送达时间 |
| data.orders[].cb_finances | object | 否 |  | 跨境订单财务数据---已废弃，可对接销售出库查询接口使用cb_financenew节点内容 |
| data.orders[].cb_finances.o_id | number | 否 |  | 内部订单号 |
| data.orders[].cb_finances.rebate_fee | integer | 否 |  | 回扣金额 |
| data.orders[].cb_finances.product_tax | integer | 否 |  | 收入税费 |
| data.orders[].cb_finances.shipping_tax | integer | 否 |  | 快递税 |
| data.orders[].cb_finances.other_income | integer | 否 |  | 其他收入 |
| data.orders[].cb_finances.voucher_from_seller | integer | 否 |  | 促销优惠金额 |
| data.orders[].cb_finances.platform_commission | integer | 否 |  | 平台佣金 |
| data.orders[].cb_finances.transition_fee | integer | 否 |  | 转账费 |
| data.orders[].cb_finances.transaction_fee | integer | 否 |  | 交易手续费 |
| data.orders[].cb_finances.opaque_bagging_fee | integer | 否 |  | 支出税费 |
| data.orders[].cb_finances.other_expense | integer | 否 |  | 其他费用 |
| data.orders[].is_merge | boolean | 否 |  | 是否合并后订单 |
| data.orders[].is_split | boolean | 否 |  | 是否拆分后订单 |
| data.orders[].first_freight_tariff | number | 否 |  | 跨境订单-头程关税 |
| data.orders[].f_freight_other_expense | number | 否 |  | 跨境订单-头程其他费用 |
| data.orders[].service_charge | number | 否 |  | 平台服务费 |
| data.orders[].government_free_amount | number | 否 |  | 政府补贴 |
| data.orders[].online_origin_amount | string | 否 |  | 营收小计：线上原始金额；null值处理成了空字符串返回，实际有值的是number类型返回 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 170 | 公司绑定验证失败6 |  |
|  |  |  |


### 请求示例

```json
{
  "o_ids": [
    971428
  ]
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {
    "requestId": null,
    "page_index": 1,
    "has_next": false,
    "orders": [
      {
        "plan_delivery_date": "2026-07-13 09:10:12",
        "referrer_id": null,
        "open_id": null,
        "f_weight": null,
        "drp_co_id_from": null,
        "buyer_id": 605679,
        "type": "普通订单",
        "discount_rate": 1,
        "send_date": null,
        "buyer_tax_no": null,
        "modified": "2026-07-31 09:16:12",
        "receiver_country": null,
        "tag": null,
        "buyer_paid_amount": null,
        "outer_drp_co_id": null,
        "drp_from": null,
        "shipment": null,
        "shop_status": "WAIT_SELLER_SEND_GOODS",
        "buyer_message": null,
        "outer_so_id": null,
        "shop_free_amount": "",
        "created": "2026-07-31 09:16:12",
        "drp_to": null,
        "is_split": null,
        "weight": 0,
        "shop_name": "川梣铺子",
        "labels": null,
        "shop_id": 11690153,
        "node": null,
        "f_freight": null,
        "shop_buyer_id": "孙明明",
        "wms_co_id": 11053062,
        "drp_co_id_to": null,
        "paid_amount": 12.8,
        "referrer_name": null,
        "link_o_id": null,
        "items": [
          {
            "i_id": null,
            "referrer_id": null,
            "batch_id": null,
            "remark": null,
            "pic": null,
            "item_ext_data": null,
            "shop_i_id": null,
            "expiration_date": null,
            "discount_rate": 0,
            "il_id": null,
            "produced_date": null,
            "src_combine_sku_id": null,
            "price": 12.8,
            "base_price": null,
            "o_id": 971428,
            "bu_id": null,
            "seller_income_amount": null,
            "outer_oi_id": "253421286",
            "buyer_paid_amount": null,
            "is_presale": null,
            "amount": 12.8,
            "send_warehouse": null,
            "item_pay_amount": null,
            "refund_status": null,
            "sku_type": "normal",
            "refund_qty": null,
            "sku_id": "ZH-0137",
            "item_status": null,
            "oi_id": 913356,
            "refund_id": null,
            "shop_sku_id": "ZH-0137",
            "raw_so_id": "D260731091012967331965200001",
            "properties_value": null,
            "is_gift": false,
            "qty": 1,
            "name": "植护 除菌除螨香氛洗衣液（樱花香型） 500g*3袋（组合装）",
            "referrer_name": null
          }
        ],
        "status": "WaitConfirm",
        "ext_datas": null,
        "pay_date": "2026-07-11 09:10:12",
        "platform_free_amount": "",
        "pay_free_amount": "",
        "online_origin_amount": "",
        "lc_id": null,
        "skus": "1.ZH-0137",
        "question_desc": null,
        "as_id": null,
        "receiver_city": "上海市",
        "invoice_title": null,
        "outer_as_id": null,
        "freight": 0,
        "remark": null,
        "__raw_so_ids__": [
          "11690153:D260731091012967331965200001"
        ],
        "is_cod": false,
        "invoice_amount": null,
        "receiver_state": "上海市",
        "glasses": "",
        "receiver_zip": null,
        "so_id": "D260731091012967331965200001",
        "o_id": 971428,
        "referrer_free_amount": "",
        "receiver_name": "孙明明",
        "currency": null,
        "invoice_type": null,
        "seller_income_amount": null,
        "free_amount": 0,
        "outer_pay_id": "D260731091012967331965200002",
        "amount": 12.8,
        "question_type": "",
        "receiver_district": "浦东新区",
        "receiver_town": null,
        "pay_amount": 12.8,
        "co_id": 11053062,
        "end_time": null,
        "shop_site": "商家自有商城",
        "receiver_mobile": "186******01",
        "sign_time": null,
        "seller_flag": null,
        "order_date": "2026-07-31 09:07:43",
        "merge_so_id": null,
        "order_imgs": [],
        "order_from": "open",
        "is_merge": null,
        "receiver_address": "唐镇虹三村龚家宅105号",
        "logistics_company": null,
        "creator_name": "小溪",
        "l_id": null,
        "receiver_phone": "186******01",
        "ts": 8424469407,
        "pays": [
          {
            "outer_pay_id": "D260731091012967331965200002",
            "pay_date": "2026-07-11 09:10:12",
            "amount": 12.8,
            "buyer_account": "未知",
            "o_id": 971428,
            "payment": "未知",
            "is_order_pay": true,
            "pay_type": 1,
            "seller_account": "未知",
            "pay_id": 1002950,
            "status": "Confirmed"
          }
        ]
      }
    ],
    "data_count": 1,
    "page_count": 1,
    "page_size": 1
  }
}
```


### 异常示例

```json
{
  "code": 120,
  "msg": "验证失败!无效签名"
}
```


---

## 订单取消-按内部单号取消

`/open/jushuitan/orderbyoid/cancel`

| 项 | 内容 |
|---|---|
| 接口名称 | 订单取消-按内部单号取消 |
| 接口路径 | `/open/jushuitan/orderbyoid/cancel` |
| docType / docId | 4 / 19 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=4&docId=19 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/orderbyoid/cancel` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/orderbyoid/cancel` |


### 接口说明

只有[待付款,发货中,异常,已付款待审核,已审核待配快递,等供销商|外仓发货,等供销商发货,已客审待财审]才可以取消订单

### 公共请求参数

| 参数名称 | 类型 | 必填 | 说明 |
|---|---|---|---|
| app_key | String | 是 | POP分配给应用的app_key |
| access_token | String | 是 | 通过code获取的access_token |
| timestamp | Long | 是 | UNIX时间戳，单位秒，需要与聚水潭服务器时间差值在10分钟内 |
| charset | String | 是 | 字符编码（固定值：utf-8） |
| version | String | 是 | 版本号，固定传2 |
| sign | String | 是 | 数字签名 |


### 业务请求参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| o_ids | array | 是 |  | 内部订单号 一次最大支持50条 |
| o_ids[] | integer | 否 |  | 111 |
| cancel_type | string | 是 | 不需要了 | 取消类型 |
| remark | string | 否 |  | 备注 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 是 |  |  |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 130 | 执行失败订单[112234] 该状态不允许取消 |  |


### 请求示例

```json
{
  "o_ids": [
    111,
    222
  ],
  "remark": "",
  "cancel_type": "不需要了"
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": ""
}
```


### 异常示例

```json
{
  "code": 120,
  "msg": "验证失败!无效签名"
}
```


---
