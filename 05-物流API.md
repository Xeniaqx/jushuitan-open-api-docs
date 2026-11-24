# 聚水潭开放平台 · 物流API（线下版）

> 抓取日期：2026-11-23  
> 分类：物流API（docType=5）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=5&docId=23

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 批量快递登记 | `/open/express/register/upload` | 23 | [打开](https://openweb.jushuitan.com/dev-doc?docType=5&docId=23) |
| 称重并发货/快递分拣 | `/open/orders/weight/send/upload` | 24 | [打开](https://openweb.jushuitan.com/dev-doc?docType=5&docId=24) |
| 发货信息查询 | `/open/logistic/query` | 25 | [打开](https://openweb.jushuitan.com/dev-doc?docType=5&docId=25) |
| 快递登记查询 | `/open/webapi/aftersaleapi/getasexpress` | 1395 | [打开](https://openweb.jushuitan.com/dev-doc?docType=5&docId=1395) |

## 目录

- [批量快递登记](#批量快递登记)
- [称重并发货/快递分拣](#称重并发货快递分拣)
- [发货信息查询](#发货信息查询)
- [快递登记查询](#快递登记查询)

---

## 批量快递登记

`/open/express/register/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 批量快递登记 |
| 接口路径 | `/open/express/register/upload` |
| docType / docId | 5 / 23 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=5&docId=23 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/express/register/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/express/register/upload` |


### 接口说明

每次上传100条,超过失败

系统相关界面：【订单】------【售后】------快递登记

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
| data | object | 否 |  |  |

### 请求示例

```json
[
  {
    "l_name": "圆通快递",
    "warehouseRemark": "做测试使用",
    "l_id": "YT2189920445563"
  }
]
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

## 称重并发货/快递分拣

`/open/orders/weight/send/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 称重并发货/快递分拣 |
| 接口路径 | `/open/orders/weight/send/upload` |
| docType / docId | 5 / 24 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=5&docId=24 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/orders/weight/send/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/orders/weight/send/upload` |


### 接口说明

系统相关界面：【订单】------【发货+】------称重相关业务

 支持按箱称重

 需要分拣的商家（不称重）请先提交工单开通对应的设置

 【称重】界面开启重量校验的开关 称重会校验重量。根据出库单所属仓判断的，如果是分仓的出库单要在分仓账号下开启重量校验。ERP修改了开启重量校验配置之后需要保存设置后接口称重才会有效。

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
| data | object | 否 |  |  |
| data.datas | array | 否 |  | 数据集合 |
| data.datas[] | object | 否 |  |  |
| data.datas[].weight | number | 否 | 0.0 | 预估重量 |
| data.datas[].volume | number | 否 |  | 预估体积 |
| data.datas[].lc_id | string | 否 | STO | 快递公司编码 |
| data.datas[].l_id | string | 否 | 1123456 | 快递单号 |
| data.datas[].logistics_company | number | 否 | 申通E物流 | 物流公司 |
| data.datas[].receiver_state | string | 否 | 上海市 | 省 |
| data.datas[].receiver_city | string | 否 | 上海市 | 市 |
| data.datas[].receiver_district | string | 否 | 普陀区 | 区 |
| data.datas[].cb_lc_id | string | 否 |  | 国际物流编码 |
| data.datas[].cb_l_id | string | 否 |  | 国际运单号 |
| data.datas[].cb_logistics_company | string | 否 |  | 国际物流渠道 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 160 | "msg": "单号:1111111 指定快递单 12345667896的单据不存在" |  |


### 请求示例

```json
[
  {
    "l_id": "15165274-1831005-32",
    "weight": 0.527,
    "is_un_lid": true,
    "type": 5
  }
]
```


### 响应示例

```json
{
  "datas": [
    {
      "skus": "",
      "weight": 0.8,
      "lc_id": "OTHER.CBERP",
      "l_id": "15165274-1831005-32",
      "logistics_company": "无需国内快递",
      "cb_lc_id": "THPHR",
      "cb_l_id": "YT2333521272286594",
      "cb_logistics_company": "云途-云途全球专线挂号（特惠普货）",
      "receiver_state": "Tasmania",
      "receiver_city": "Smithton",
      "receiver_district": "Smithton",
      "is_success": true,
      "msg": null
    }
  ],
  "code": 0,
  "issuccess": true,
  "msg": "执行成功",
  "requestId": null
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

## 发货信息查询

`/open/logistic/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 发货信息查询 |
| 接口路径 | `/open/logistic/query` |
| docType / docId | 5 / 25 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=5&docId=25 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/logistic/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/logistic/query` |


### 接口说明

此接口不包含淘系拼多多敏感数据： 线上单号

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
| shop_id | integer | 否 | 10191811 | 店铺编号 |
| page_index | integer | 否 | 1 | 第几页，从1开始 |
| page_size | integer | 否 | 30 | 默认30，最大不超过50 |
| modified_begin | string | 否 | 2021-12-02 15:55:06 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天 |
| modified_end | string | 否 | 2021-12-09 15:55:06 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天 |
| date_type | integer | 否 |  | 日期类型，默认发货时间，0=修改时间，1=制单日期，2=订单日期，3=发货时间 |
| so_ids | array | 否 |  | 平台订单编号 最多20（如果通过线上单号查询除时间条件外不受其它查询条件限制） |
| so_ids[] | string | 否 |  |  |

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
| data.has_next | boolean | 是 | false | 是否有下一页 |
| data.orders | array | 否 |  | 数据集合 |
| data.orders[] | object | 否 |  |  |
| data.orders[].o_id | integer | 是 | 3090086 | ERP订单号;唯一 |
| data.orders[].shop_id | integer | 是 | 14588 | 店铺编号 |
| data.orders[].so_id | string | 是 | 8-m2 | 订单号，最长不超过50;唯一 |
| data.orders[].as_id | number | 否 |  | 补发换货订单对应的售后单号 |
| data.orders[].send_date | string | 否 | 2019-12-16 18:18:34 | 发货时间 |
| data.orders[].freight | number | 否 | 8.0 | 运费 |
| data.orders[].weight | number | 否 |  | 重量 |
| data.orders[].wms_co_id | number | 否 |  | 发货仓编码（0表示主仓发货） |
| data.orders[].lc_id | string | 否 | April | 快递公司代码 |
| data.orders[].l_id | string | 否 | 765433222222 | 快递单号 |
| data.orders[].logistics_company | string | 否 | 申通快递 | 快递公司 |
| data.orders[].items | array | 是 |  | 订单明细；商品信息 |
| data.orders[].items[] | object | 否 |  |  |
| data.orders[].items[].sku_id | string | 是 | s111001 | 商家SKU，对应库存管理的SKU |
| data.orders[].items[].qty | integer | 是 | 1 | 购买数量 |
| data.orders[].items[].outer_oi_id | string | 是 | 1216001 | 子订单号 |
| data.orders[].items[].raw_so_id | string | 否 | 8-m1 | 原始平台订单号，可以为空，最长不超过50 |
| data.orders[].items[].o_id | string | 否 | 3090086 | 内部单号 |
| data.orders[].items[].refund_status | string | 否 |  | 商品退款状态 |
| data.orders[].items[].sku_type | string | 否 |  | 商品类型 |

### 请求示例

```json
{
  "shop_id": 10191811,
  "date_type": 0,
  "so_ids": [],
  "page_index": 1,
  "modified_begin": "2021-12-02 15:55:06",
  "modified_end": "2021-12-09 15:55:06",
  "page_size": 30
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {
    "page_index": 1,
    "has_next": false,
    "orders": [
      {
        "shop_id": 14588,
        "lc_id": "April",
        "send_date": "2019-12-16 18:18:34",
        "so_id": "8-m2",
        "freight": 8.0,
        "o_id": 3090086,
        "weight": 0.0,
        "logistics_company": "申通快递",
        "l_id": "765433222222",
        "items": [
          {
            "raw_so_id": "8-m1",
            "refund_status": "",
            "qty": 1,
            "o_id": "3090086",
            "sku_id": "s111001",
            "outer_oi_id": "1216001"
          }
        ]
      }
    ],
    "data_count": 2,
    "page_count": 1,
    "page_size": 2
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

## 快递登记查询

`/open/webapi/aftersaleapi/getasexpress`

| 项 | 内容 |
|---|---|
| 接口名称 | 快递登记查询 |
| 接口路径 | `/open/webapi/aftersaleapi/getasexpress` |
| docType / docId | 5 / 1395 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=5&docId=1395 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/aftersaleapi/getasexpress` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/aftersaleapi/getasexpress` |


### 接口说明

入参校验
 分页
 分页必传 当前页不能小于等于0 分页大小只能为100,200或500 登记时间 没有快递单号、物流公司、时间戳时 开始和结束时间无值，则默认查近一个月的 开始和结束时间两则必填 登记时间间隔必须在1个月内 开始时间不能大于结束时间
 响应 按时间戳降序

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
| l_ids | array | 否 |  | 快递单号 |
| l_ids[] | string | 否 | 342323232433 |  |
| logistics_companys | array | 否 |  | 快递公司 |
| logistics_companys[] | string | 否 |  |  |
| is_archive | boolean | 否 |  | 是否查询归档库 |
| begin_time | string | 否 |  | 登记开始时间 |
| end_time | string | 否 |  | 登记结束时间 |
| begin_timestamp | number | 否 |  | 开始时间戳 |
| page_index | number | 是 | 1 | 当前页（大于等于1） |
| page_size | number | 是 | 100 | 每页大小（100，200，500） |
| enabled | boolean | 否 | true | 是否启用 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| page | object | 否 |  |  |
| page.current_page | number | 否 |  |  |
| page.page_size | number | 否 |  |  |
| page.count | number | 否 |  |  |
| page.pages | number | 否 |  |  |
| page.index | number | 否 |  |  |
| code | number | 否 |  |  |
| act | number | 否 |  |  |
| data | object | 否 |  |  |
| data.as_express_list | array | 否 |  |  |
| data.as_express_list[] | object | 否 |  |  |
| data.as_express_list[].l_id | string | 否 |  | 快递单号 |
| data.as_express_list[].logistics_company | string | 否 |  | 快递公司 |
| data.as_express_list[].total_qty | number | 否 |  | 商品件数 |
| data.as_express_list[].warehouse_receipt | number | 否 |  | 仓库实收 |
| data.as_express_list[].creator_name | string | 否 |  | 登记人 |
| data.as_express_list[].created | string | 否 |  | 登记时间 |
| data.as_express_list[].enabled | boolean | 否 |  | 单据状态（生效：true，作废：false） |
| data.as_express_list[].warehouse_remark | string | 否 |  | 仓库备注 |
| data.as_express_list[].remark | string | 否 |  | 退货说明 |
| data.as_express_list[].labels | string | 否 |  | 标签/多标签，逗号分隔 |
| data.as_express_list[].wms_co_name | string | 否 |  | 仓储方 |
| data.as_express_list[].receipt_date | string | 否 |  | 收货时间，可为空 |
| data.as_express_list[].timestamp | number | 否 |  | Timestamp |
| data.current_page | number | 否 |  | 当前处于第几页 |
| data.page_size | number | 否 |  | 一页几条数据 |
| data.count | number | 否 |  | 数据总条数 |
| data.pages | number | 否 |  | 总页数 |
| msg | null | 否 |  |  |
| msg_type | string | 否 |  |  |
| request_id | null | 否 |  |  |
| cookie | null | 否 |  |  |

### 请求示例

```json
{
  "logistics_companys": [],
  "begin_timestamp": 0,
  "l_ids": [],
  "page_index": 1,
  "is_archive": true,
  "end_time": "",
  "begin_time": "",
  "enabled": true,
  "page_size": 100
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "act": 0,
  "data": {
    "pages": 0,
    "count": 0,
    "as_express_list": [
      {
        "created": "",
        "total_qty": 0,
        "warehouse_remark": "",
        "remark": "",
        "enabled": true,
        "labels": "",
        "receipt_date": "",
        "logistics_company": "",
        "creator_name": "",
        "warehouse_receipt": 0,
        "l_id": "",
        "wms_co_name": "",
        "timestamp": 0
      }
    ],
    "current_page": 0,
    "page_size": 0
  },
  "cookie": "",
  "msg_type": "",
  "page": {
    "pages": 0,
    "count": 0,
    "index": 0,
    "current_page": 0,
    "page_size": 0
  },
  "request_id": ""
}
```


### 异常示例

_无_


---
