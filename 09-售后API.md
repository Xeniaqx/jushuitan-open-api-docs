# 聚水潭开放平台 · 售后API（线下版）

> 抓取日期：2026-11-23  
> 分类：售后API（docType=9）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=9&docId=1443

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 设置售后标签 | `/open/webapi/aftersaleapi/setaslabels` | 1443 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=1443) |
| 唯一码批量确认收货 | `/open/webapi/aftersaleapi/confirmgoodsbyskusns` | 743 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=743) |
| 售后单作废 | `/open/webapi/aftersaleapi/open/cancel` | 582 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=582) |
| 售后单确认 | `/open/webapi/aftersaleapi/open/confirm` | 581 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=581) |
| 售后(退货退款)查询 | `/open/refund/single/query` | 38 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=38) |
| 售后单反确认 | `/open/webapi/aftersaleapi/open/unconfirm` | 579 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=579) |
| 售后-确认收到货物（可分批确认） | `/open/webapi/aftersaleapi/confirmgoods` | 272 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=272) |
| 售后上传（无信息件) | `/open/aftersale/noinfo/upload` | 124 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=124) |
| 售后上传 | `/open/aftersale/upload` | 41 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=41) |
| 销售退仓-实际收货查询 | `/open/aftersale/received/query` | 40 | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=40) |

## 目录

- [设置售后标签](#设置售后标签)
- [唯一码批量确认收货](#唯一码批量确认收货)
- [售后单作废](#售后单作废)
- [售后单确认](#售后单确认)
- [售后(退货退款)查询](#售后退货退款查询)
- [售后单反确认](#售后单反确认)
- [售后-确认收到货物（可分批确认）](#售后-确认收到货物可分批确认)
- [售后上传（无信息件)](#售后上传无信息件)
- [售后上传](#售后上传)
- [销售退仓-实际收货查询](#销售退仓-实际收货查询)

---

## 设置售后标签

`/open/webapi/aftersaleapi/setaslabels`

| 项 | 内容 |
|---|---|
| 接口名称 | 设置售后标签 |
| 接口路径 | `/open/webapi/aftersaleapi/setaslabels` |
| docType / docId | 9 / 1443 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=1443 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/aftersaleapi/setaslabels` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/aftersaleapi/setaslabels` |


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
| as_ids | array | 是 |  | 售后单号集合 |
| as_ids[] | number | 否 | 89977 | 售后单号 |
| labels | array | 是 |  | 标签集合 |
| labels[] | string | 否 | 工单 | 标签 |
| remove | boolean | 是 | false | 是否移除 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.success | array | 是 |  | 成功集合 |
| data.success[] | object | 否 |  |  |
| data.success[].as_id | number | 是 |  | 内部单号 |
| data.success[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.success[].code | number | 是 |  |  |
| data.success[].message | null | 是 |  |  |
| data.success[].details | null | 是 |  |  |
| data.success[].is_success | boolean | 是 |  | 是否成功 |
| data.fail | array | 是 |  | 失败集合 |
| data.fail[] | object | 否 |  |  |
| data.fail[].as_id | number | 是 |  | 内部单号 |
| data.fail[].outer_as_id | null | 是 |  | 外部售后单号 |
| data.fail[].code | number | 是 |  |  |
| data.fail[].message | string | 是 |  | 失败的原因 |
| data.fail[].details | null | 是 |  |  |
| data.fail[].is_success | boolean | 是 |  | 是否成功 |
| data.success_count | number | 否 |  | 成功的总条数 |
| data.fail_count | number | 否 |  | 失败的总条数 |
| msg | null | 否 |  |  |

### 请求示例

```json
{
  "as_ids": [],
  "remove": false,
  "labels": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "fail": [
      {
        "code": 0,
        "as_id": 0,
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": true
      }
    ],
    "success": [
      {
        "code": 0,
        "as_id": 0,
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": true
      }
    ],
    "success_count": 0,
    "fail_count": 0
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

## 唯一码批量确认收货

`/open/webapi/aftersaleapi/confirmgoodsbyskusns`

| 项 | 内容 |
|---|---|
| 接口名称 | 唯一码批量确认收货 |
| 接口路径 | `/open/webapi/aftersaleapi/confirmgoodsbyskusns` |
| docType / docId | 9 / 743 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=743 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/aftersaleapi/confirmgoodsbyskusns` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/aftersaleapi/confirmgoodsbyskusns` |


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
| code | number | 否 |  | 0表示成功 |
| msg | null | 否 |  | 执行返回信息 |
| data | object | 否 |  |  |
| data.success | array | 否 |  | 成功详情 |
| data.success[] | object | 否 |  |  |
| data.success[].as_id | string | 是 |  | 内部售后单号 |
| data.success[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.success[].sku_sns | string | 是 |  | 唯一码 |
| data.success[].code | string | 是 |  | 返回码 |
| data.success[].message | string | 是 |  | 返回信息 |
| data.success[].details | string | 是 |  | 详细信息 |
| data.success[].is_success | string | 是 |  | 是否成功 |
| data.fail | array | 否 |  | 失败详情 |
| data.fail[] | object | 否 |  |  |
| data.fail[].as_id | string | 是 |  | 内部售后单号 |
| data.fail[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.fail[].sku_sns | string | 是 |  | 唯一码 |
| data.fail[].code | string | 是 |  | 返回码 |
| data.fail[].message | string | 是 |  | 返回信息 |
| data.fail[].details | string | 是 |  | 详细信息 |
| data.fail[].is_success | string | 是 |  | 是否成功 |
| data.success_count | number | 否 |  | 成功数量 |
| data.fail_count | number | 否 |  | 失败数量 |

### 请求示例

```json
[
  {
    "sku_sn": "10086",
    "remark": "sf001"
  },
  {
    "sku_sn": "10087",
    "remark": "sf010"
  },
  {
    "sku_sn": "10088",
    "remark": "sf010"
  }
]
```


### 响应示例

```json
{
  "code": 0,
  "data": {
    "success": [
      {
        "as_id": 11011132,
        "outer_as_id": "S401300720231212133540968",
        "sku_sns": "10087,10088",
        "code": 0,
        "message": null,
        "details": null,
        "is_success": true
      }
    ],
    "fail": [
      {
        "as_id": 0,
        "outer_as_id": null,
        "sku_sns": "10086",
        "code": 0,
        "message": "唯一码[10086],商品[1006],系统中已存在(未出库)",
        "details": null,
        "is_success": false
      }
    ],
    "success_count": 1,
    "fail_count": 1
  },
  "msg": null,
  "request_id": null
}
```


### 异常示例

_无_


---

## 售后单作废

`/open/webapi/aftersaleapi/open/cancel`

| 项 | 内容 |
|---|---|
| 接口名称 | 售后单作废 |
| 接口路径 | `/open/webapi/aftersaleapi/open/cancel` |
| docType / docId | 9 / 582 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=582 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/aftersaleapi/open/cancel` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/aftersaleapi/open/cancel` |


### 接口说明

售后单状态为【已确认】或者售后单货物状态为【卖家已收到退货】，无法作废，请先反确认售后单或者取消收到货物

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
| as_ids | array | 是 |  | 售后单id数组 |
| as_ids[] | number | 否 |  | 售后单id |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.success | array | 否 |  |  |
| data.success[] | object | 否 |  |  |
| data.success[].as_id | number | 是 |  | 售后单号 |
| data.success[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.success[].message | string | 是 |  | 成功消息 |
| data.success[].details | string | 是 |  | 成功详细消息 |
| data.success[].is_success | boolean | 是 |  | 是否成功 |
| data.fail | array | 否 |  |  |
| data.fail[] | object | 否 |  |  |
| data.fail[].as_id | number | 是 |  | 售后单号 |
| data.fail[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.fail[].message | string | 是 |  | 错误消息 |
| data.fail[].details | string | 是 |  | 错误详细消息 |
| data.fail[].is_success | boolean | 是 |  | 是否成功 |
| data.success_count | number | 否 |  | 成功数量 |
| data.fail_count | number | 否 |  | 失败数量 |
| msg | string | 否 |  |  |

### 请求示例

```json
{
  "as_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "fail": [
      {
        "as_id": 0,
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": true
      }
    ],
    "success": [
      {
        "as_id": 0,
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": true
      }
    ],
    "success_count": 0,
    "fail_count": 0
  }
}
```


### 异常示例

_无_


---

## 售后单确认

`/open/webapi/aftersaleapi/open/confirm`

| 项 | 内容 |
|---|---|
| 接口名称 | 售后单确认 |
| 接口路径 | `/open/webapi/aftersaleapi/open/confirm` |
| docType / docId | 9 / 581 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=581 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/aftersaleapi/open/confirm` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/aftersaleapi/open/confirm` |


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
| as_ids | array | 是 |  | 售后单id数组 |
| as_ids[] | number | 否 |  | 售后单id |
| exchange_force | boolean | 是 |  | 换货售后单是否强制确认 |
| confirm_refund | boolean | 是 |  | 是否同步确认退款单 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.success | array | 否 |  |  |
| data.success[] | object | 否 |  |  |
| data.success[].as_id | number | 是 |  | 售后单号 |
| data.success[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.success[].message | string | 是 |  | 成功消息 |
| data.success[].details | string | 是 |  | 成功详细消息 |
| data.success[].is_success | boolean | 是 |  | 是否成功 |
| data.success[].new_o_id | string | 是 |  | 新生成的补发的内部订单号 |
| data.fail | array | 否 |  |  |
| data.fail[] | object | 否 |  |  |
| data.fail[].as_id | number | 是 |  | 售后单号 |
| data.fail[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.fail[].message | string | 是 |  | 错误消息 |
| data.fail[].details | string | 是 |  | 错误详细消息 |
| data.fail[].is_success | boolean | 是 |  | 是否成功 |
| data.success_count | number | 否 |  | 成功数量 |
| data.fail_count | number | 否 |  | 失败数量 |
| msg | string | 否 |  |  |

### 请求示例

```json
{
  "exchange_force": true,
  "as_ids": [],
  "confirm_refund": true
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "fail": [
      {
        "as_id": 0,
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": true
      }
    ],
    "success": [
      {
        "as_id": 0,
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": true
      }
    ],
    "success_count": 0,
    "fail_count": 0
  }
}
```


### 异常示例

_无_


---

## 售后(退货退款)查询

`/open/refund/single/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 售后(退货退款)查询 |
| 接口路径 | `/open/refund/single/query` |
| docType / docId | 9 / 38 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=38 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/refund/single/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/refund/single/query` |


### 接口说明

系统相关界面：【订单】------【售后(退货退款)】
 此接口查询不到淘系和拼多多售后单信息，接口可以返回送仓售后单据
 淘系订单通过奇门获取： 奇门自定义场景
 拼多多订单通过方舟获取： 拼多多方舟 （注：只能查到近3个月的售后单）

 淘系平台包含： 淘宝天猫，天猫供销，考拉pop，考拉供应商直发，阿里巴巴，淘工厂，天猫超市，天猫国际直营，阿里健康直营，淘宝定制，淘宝采购，淘宝买菜，银泰喵街 ，饿百零售

 1.实退金额计算规则： 实退金额 = 商品应退金额 + 应退运费 - 优惠/差额 + 卖家应补 - 换货金额 - 买家应补
 接口字段计算：实退金额=freight+refund-payment-free_amount

 2.请求参数中start_ts的说明：使用ts的查询条件是唯一可避免分页查询过程中因数据变动而导致的漏单问题，原因是该查询条件是数据库中的时间戳，sql server中的 行版本号 。只要当前这条数据在数据库中有变化任何字段变化ts的值都会自增，全表唯一的自增值，非业务上做的时间值更新。使用ts的查询模板
 第一次请求：{" start_ts ":1," is_get_total ":false," page_index ":1," page_size ":100} //第一次请求ts从1开始
 第二次请求：{" start_ts ":传第一次返回的最大ts值," is_get_total ":false," page_index ":1," page_size ":100} //一直请求到查不到比入参ts值本身更大的数据为止。只有start_ts值是变量，其它3个参数值不变

 更多售后API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=22&currentPage=1&pageSize=20

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
| shop_id | integer | 否 | 10166040 | 店铺编号 |
| is_offline_shop | boolean | 否 | false | shop_id为0且is_offline_shop为true查询线下店铺单据 |
| date_type | number | 否 |  | 售后日期类型（0：修改时间；1：创建时间；2：确认时间；默认0修改时间） |
| modified_begin | string | 否 | 2021-12-03 12:00:00 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空；tips:用时间条件查询由于查询中数据存在变动的可能会由于排序问题引发分页查询漏单的问题，建议使用ts时间戳增量查询的方式 |
| modified_end | string | 否 | 2021-12-10 12:00:00 | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空 |
| so_ids | array | 否 |  | 指定线上订单号，和时间段不能同时为空 |
| so_ids[] | string | 否 |  |  |
| shop_buyer_ids | array | 否 |  | 指定买家账号，最多50 |
| shop_buyer_ids[] | string | 否 |  |  |
| page_index | integer | 否 | 1 | 第几页，从第一页开始，默认1 |
| page_size | integer | 否 | 30 | 每页多少条，默认30，最大50 |
| o_ids | array | 否 |  | 指定内部单号，和时间段不能同时为空 |
| o_ids[] | integer | 否 |  |  |
| as_ids | array | 否 |  | 售后单号（商家维度下售后唯一值），和时间段不能同时为空 |
| as_ids[] | integer | 否 |  |  |
| status | string | 否 |  | 售后单状态（WaitConfirm:待确认,Confirmed:已确认,Cancelled:作废,Merged:被合并，Split：被拆分） |
| start_ts | integer | 否 |  | 时间戳，sql server中的行版本号，该字段查询防止分页过程中漏单 |
| is_get_total | boolean | 否 |  | 是否查询总条数默认true，如果使用start_ts查询，该值传false否则影响查询效率 |
| good_status | string | 否 |  | 货物状态（BUYER_NOT_RECEIVED:买家未收到货,BUYER_RECEIVED:买家已收到货,BUYER_RETURNED_GOODS:买家已退货,SELLER_RECEIVED:卖家已收到退货； OuterConfirming：奇门收货中；OuterCanceling：奇门拉回中） |
| type | string | 否 |  | 售后类型，普通退货，其它，拒收退货，仅退款，投诉，补发，换货，维修 |
| owner_co_id | string | 否 |  | 货主编码 |
| archive | boolean | 否 |  | 是否查询归档数据；true查询归档；false或不传默认查未归档 |
| l_id | string | 否 |  | 物流单号，多个用逗号分隔，最多不超过100个 |
| is_get_promotion | boolean | 否 |  | 是否查询售后营收小计金额，默认false |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  |  |
| data.page_size | integer | 否 | 30 | 每页多少条 |
| data.page_index | integer | 否 | 1 | 第几页 |
| data.data_count | integer | 否 | 2 | 总条数 |
| data.page_count | integer | 否 | 1 | 总页数 |
| data.has_next | boolean | 否 | false | 是否有下一页 |
| data.datas | array | 否 |  | 数据集合 |
| data.datas[] | object | 否 |  |  |
| data.datas[].as_id | integer | 否 | 19371 | 聚水潭售后单号 |
| data.datas[].as_date | string | 否 | 2021-08-17 15:11:50 | 申请时间 |
| data.datas[].outer_as_id | string | 否 | 20210817000004 | 平台退货退款单号 |
| data.datas[].o_id | integer | 否 | 3772720 | 订单内部单号 |
| data.datas[].so_id | string | 否 | 747727584476 | 订单线上单号 |
| data.datas[].type | string | 否 | 普通退货 | 售后类型，普通退货，其它，拒收退货，仅退款，投诉，补发，换货，维修 |
| data.datas[].created | string | 否 | 2021-08-17 15:11:50 | 登记时间 |
| data.datas[].modified | string | 否 | 2021-08-17 15:17:39 | 修改时间 |
| data.datas[].status | string | 否 | WaitConfirm | 状态（WaitConfirm:待确认,Confirmed:已确认,Cancelled:作废,Merged:被合并） |
| data.datas[].shop_status | string | 否 | WAIT_SELLER_CONFIRM_GOODS | WAIT_SELLER_AGREE:等待卖家同意; WAIT_BUYER_RETURN_GOODS:等待买家退货;WAIT_SELLER_CONFIRM_GOODS:买家已经退货，等待卖家确认收货;SELLER_REFUSE_BUYER:卖家拒绝退款;EXCHANGE_SELLER_DELIVERY:售后换货商家发货;EXCHANGE_BUYER_CONFIRM_GOODS:售后换货用户收货;WAIT_SELLER_DELIVER_GOODS:等待卖家发货;REISSUE_SELLER_DELIVERY:补发卖家发货;CLOSED:退款关闭;SUCCESS:退款成功;SYNCING:同步中;SYNC_SUCCESS:同步成功;SYNC_ERROR:同步失败;待发出换货商品:待发出换货商品 |
| data.datas[].remark | string | 否 |  | 备注 |
| data.datas[].question_type | string | 否 | 卖家已收到退货 | 问题类型 |
| data.datas[].warehouse | string | 否 | wowcolour退货仓 | 仓库 |
| data.datas[].refund | number | 否 | 20.0 | 退款金额(商品应退金额+卖家应补) |
| data.datas[].payment | number | 否 | 0.0 | 补偿金额(换货金额+买家应补) |
| data.datas[].free_amount | number | 否 |  | 优惠/差额 |
| data.datas[].good_status | string | 否 | SELLER_RECEIVED | 货物状态（BUYER_NOT_RECEIVED:买家未收到货,BUYER_RECEIVED:买家已收到货,BUYER_RETURNED_GOODS:买家已退货,SELLER_RECEIVED:卖家已收到退货） |
| data.datas[].node | string | 否 | 问题类型不存在 | 售后线下备注 |
| data.datas[].order_status | string | 否 | WaitConfirm | 原订单状态(待付款：WaitPay；发货中：Delivering；被合并：Merged；异常：Question；被拆分：Split；等供销商\|外仓发货：WaitOuterSent；已付款待审核：WaitConfirm；已客审待财审：WaitFConfirm；已发货：Sent；取消：Cancelled) |
| data.datas[].shop_type | string | 否 |  | 线上类型 |
| data.datas[].shop_id | integer | 否 | 10192709 | 店铺编号 |
| data.datas[].logistics_company | string | 否 | 顺丰 | 退回物流公司 |
| data.datas[].l_id | string | 否 | 770989881482 | 退回快递单号(运单号) |
| data.datas[].sub_l_ids | string | 否 |  | 退回子物流单号（需开启as.return.express.multi，归档数据不返回） |
| data.datas[].wh_id | integer | 否 | 2 | 仓库编号 |
| data.datas[].wms_co_id | integer | 否 | 12252 | 收货仓编码 |
| data.datas[].confirm_date | string | 否 |  | 最后确认日期 |
| data.datas[].freight | number | 否 | 0.0 | 卖家应退运费 |
| data.datas[].drp_co_id_from | integer | 否 |  | 分销商编号 |
| data.datas[].receiver_mobile | string | 否 | 15260169283 | 原订单收件人电话 |
| data.datas[].receiver_name | string | 否 | 黄 | 原订单收件人名称 |
| data.datas[].shop_buyer_id | string | 否 | hht | 买家账号 |
| data.datas[].buyer_apply_refund | number | 否 |  | 线上申请金额 |
| data.datas[].receive_refund | number | 否 |  | 实际退给买家的金额(平台下载的不是全部平台都有的。ERP界面不体现该金额) |
| data.datas[].result  | string | 否 |  | 处理结果 |
| data.datas[].items | array | 否 |  | 商品集合 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].asi_id | integer | 否 | 23740 | 售后子单号 |
| data.datas[].items[].as_id | integer | 否 | 19371 | ERP售后单号 |
| data.datas[].items[].shop_amount | number | 否 |  | 线上明细金额 |
| data.datas[].items[].sku_id | string | 否 | hhtzgsku53 | 商品编码 |
| data.datas[].items[].qty | integer | 否 | 1 | 申请数量 |
| data.datas[].items[].is_gift | boolean | 否 |  | 是否赠品 |
| data.datas[].items[].price | number | 否 | 10.0 | 单价 |
| data.datas[].items[].amount | number | 否 | 10.0 | 申请金额 |
| data.datas[].items[].name | string | 否 | hht测试商品53 | 商品名称 |
| data.datas[].items[].pic | string | 否 |  | 图片地址 |
| data.datas[].items[].type | string | 否 | 退货 | 类型（退货，换货,补发，其它） |
| data.datas[].items[].properties_value | string | 否 |  | 颜色规格 |
| data.datas[].items[].outer_oi_id | string | 否 |  | 子订单号：取值订单outer_oi_id |
| data.datas[].items[].sku_type | string | 否 | normal | 商品类型 |
| data.datas[].items[].r_qty | integer | 否 | 1 | 实收退货数量 |
| data.datas[].items[].receive_date | string | 否 | 2021-08-1715:17:40 | 入仓时间 |
| data.datas[].items[].combine_sku_id | string | 否 |  | 组合商品编码 |
| data.datas[].items[].shop_sku_id | string | 否 |  | 店铺商品编码 |
| data.datas[].items[].i_id | string | 否 |  | 款式编码 |
| data.datas[].items[].defective_qty | integer | 否 |  | 次品数量 |
| data.datas[].items[].remark | string | 否 |  | 明细备注 |
| data.datas[].items[].raw_so_id | string | 否 |  | 原始线上订单号 |
| data.datas[].items[].seller_income_amount | number | 否 |  | 营收小计-明细商家实收(入参is_get_promotion=true并且ERP售后开启营收小计才会返回 ) |
| data.datas[].items[].buyer_paid_amount | number | 否 |  | 营收小计-明细买家实付(入参is_get_promotion=true并且ERP售后开启营收小计才会返回 ) |
| data.datas[].batchs | array | 否 |  | 生产批次集合 |
| data.datas[].batchs[] | object | 否 |  |  |
| data.datas[].batchs[].batch_no | string | 否 |  | 批次号 |
| data.datas[].batchs[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].batchs[].qty | integer | 否 |  | 商品数量 |
| data.datas[].batchs[].product_date | string | 否 |  | 批次日期 |
| data.datas[].batchs[].supplier_id | integer | 否 |  | 供应商编号 |
| data.datas[].batchs[].supplier_name | string | 否 |  | 供应商名称 |
| data.datas[].batchs[].expiration_date | string | 否 |  | 有效期至 |
| data.datas[].sns | array | 否 |  | 唯一码集合 |
| data.datas[].sns[] | object | 否 |  |  |
| data.datas[].sns[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].sns[].sn | string | 否 |  | SN号码 |
| data.datas[].drp_co_id_to | integer | 否 |  | 供销商编号 |
| data.datas[].labels | string | 否 |  | 标记｜多标签(线上下载:ShopDown;换货单:ExchangeOrRepair;开放平台:OpenDown;奇门仓储:QimenWms;字节仓储:ByteWms;方舟仓储:FangZhouWms;特殊退款单:SpecialRefund;价保单:价保单;异常冲抵:异常冲抵;唯品直退:VipOrderReturn;官方仓退货:官方仓退货;周期购订单:CyclePeriod;云仓:WMS;供货商:供货商;换货:Fba换货;换货退货:Fba换货退货;抖音超市:抖音超市;天猫新版换货:天猫新版换货;奇门货主:QimenOms;平台自动拦截同意退款:AutoBlockRefund;平台出资:PlatformFunded;商家出资:MerchantFunded;已放款:Loan;线上拒收退货退款:Reject;自动退款给分销商成功:AutoRefundToDisSuccess;自动退款给分销商失败:AutoRefundToDisFail;抖音供货单:抖音供货单;含商责运费:含商责运费;ERP创建:ERP创建;超级半托管:超级半托管;主动退款:主动退款;平台退运费:平台退运费;极速退款:极速退款;极速退款成功:极速退款成功) |
| data.datas[].refund_version | integer | 否 |  | 退款版本号:（1000表示送仓售后单据） |
| data.datas[].ts | string | 否 |  | 数据库行版本号：https://docs.microsoft.com/zh-cn/sql/t-sql/data-types/rowversion-transact-sql?view=sql-server-ver16 |
| data.datas[].shop_name | string | 否 |  | 店铺名称 |
| data.datas[].currency | string | 否 |  | 币种（跨境单据有值，币种映射关系参考https://openweb.jushuitan.com/doc?docId=223） |
| data.datas[].order_labels | array | 否 |  | 原订单标签（如果订单已归档，不返回） |
| data.datas[].order_labels[] | string | 否 |  |  |
| data.datas[].refund_phase | string | 否 |  | 退款阶段 |
| data.datas[].seller_real_refund  | number | 否 |  | 售后详情中商家实退字段(退给用户的钱)+平台补贴金额(退给平台的钱） |
| data.datas[].creator_name | string | 否 |  | 创建人 |
| data.datas[].drp_refund_status | string | 否 |  | 供销商退款状态（WaitConfirm:待审核,Confirmed:已确认,Finished:完成,Cancelled:作废） |
| data.datas[].shop_freight | number | 否 |  | 线上退运费 |
| data.datas[].order_type | string | 否 |  | 订单类型 |
| data.datas[].images | array | 否 |  |  |
| data.datas[].images[] | object | 否 |  | 附件图片 |
| data.datas[].images[].key | string | 否 |  | 路径 |
| data.datas[].images[].domain | string | 否 |  | 域名 |
| data.datas[].buyer_receive_refund | number | 否 |  | 等于receive refund+平台补贴（仅抖音京东）；拼多多售后为全部退款且有平台补贴的情况，业务会进行特殊处理，用线上申请金额+平台补贴算出。其它平台没有值 |
| data.datas[].platform_promotion | number | 否 |  | 平台补贴 |
| data.datas[].owner_co_id | number | 否 |  | 货主编码 |
| data.datas[].drp_from_submit | boolean | 否 |  | 是否提交给分销商 |
| data.datas[].drp_submit | boolean | 否 |  | 是否提交给供销商 |
| data.datas[].seller_income_amount | number | 否 |  | 营收小计-商家实收(入参is_get_promotion=true并且ERP售后开启营收小计才会返回 ) |
| data.datas[].buyer_paid_amount | number | 否 |  | 营收小计-买家实付(入参is_get_promotion=true并且ERP售后开启营收小计才会返回 ) |
| data.datas[].platform_free_amount | number | 否 |  | 营收小计-平台补贴(入参is_get_promotion=true并且ERP售后开启营收小计才会返回 ) |
| data.datas[].government_free_amount | number | 否 |  | 营收小计-政府补贴(入参is_get_promotion=true并且ERP售后开启营收小计才会返回 ) |
| data.datas[].outer_drp_co_id | number | 否 |  | 货主分销编码 |

### 请求示例

```json
{
  "modified_begin": "2023-08-02 00:00:00",
  "modified_end": "2023-08-02 23:59:59",
  "page_index": 1,
  "page_size": 50
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {
    "max_ts": 0,
    "datas": [
      {
        "refund_version": null,
        "order_labels": [
          "发货后售后"
        ],
        "drp_co_id_from": null,
        "type": "普通退货",
        "good_status": null,
        "buyer_apply_refund": null,
        "order_status": "Sent",
        "owner_co_id": 0,
        "modified": "2026-08-13 15:37:12",
        "payment": 0,
        "order_type": "普通订单",
        "outer_drp_co_id": 0,
        "images": null,
        "platform_promotion": null,
        "shop_status": null,
        "created": "2026-08-13 15:37:12",
        "extend_datas": "{}",
        "is_split": null,
        "buyer_receive_refund": null,
        "warehouse": "川梣测试公司销退仓",
        "drp_submit": null,
        "shop_name": "测试",
        "urefund": 0,
        "io_id": null,
        "labels": "",
        "node": "",
        "shop_id": 18947207,
        "shop_buyer_id": "",
        "wms_co_id": null,
        "drp_co_id_to": null,
        "confirm_date": null,
        "items": [
          {
            "box_id": null,
            "i_id": "jofo002",
            "as_id": 1370187053,
            "referrer_id": null,
            "item_sign": null,
            "remark": null,
            "pic": null,
            "type": "退货",
            "des": null,
            "price": 0,
            "combine_sku_id": "",
            "r_qty": 0,
            "defective_qty": null,
            "outer_oi_id": "",
            "amount": 0,
            "sku_type": "normal",
            "asi_id": 1370191317,
            "extend_datas": "{\"i\":1,\"item_source\":\"手工添加\"}",
            "total_per_unit": null,
            "sku_id": "jofo002",
            "shop_amount": null,
            "shop_sku_id": null,
            "receive_date": null,
            "raw_so_id": "18947207:jofo20260613004",
            "properties_value": null,
            "is_gift": false,
            "per_unit": null,
            "qty": 1,
            "name": "交赋测试2#",
            "referrer_name": null
          }
        ],
        "status": "WaitConfirm",
        "refund": 0,
        "modifier_name": "川梣",
        "as_id": 1370187053,
        "outer_as_id": "S956405202608131537128391270861628",
        "freight": 0,
        "remark": "",
        "receive_refund": null,
        "result": "",
        "drp_from_submit": null,
        "so_id": "jofo20260613004",
        "o_id": 956405,
        "receiver_name": "张嘿嘿",
        "currency": "",
        "free_amount": 0,
        "question_type": "7天无理由退换货",
        "co_id": 11053062,
        "shop_freight": 0,
        "drp_refund_status": null,
        "shop_site": "商家自有商城",
        "receiver_mobile": "18888888888",
        "order_date": "2026-06-13 11:33:25",
        "refund_phase": null,
        "wh_id": 2,
        "is_merge": null,
        "as_date": "2026-08-13 15:37:12",
        "shop_type": null,
        "creator_name": "川梣",
        "logistics_company": "",
        "l_id": "",
        "ts": 8530639633
      }
    ],
    "requestId": null,
    "page_index": 1,
    "has_next": false,
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

## 售后单反确认

`/open/webapi/aftersaleapi/open/unconfirm`

| 项 | 内容 |
|---|---|
| 接口名称 | 售后单反确认 |
| 接口路径 | `/open/webapi/aftersaleapi/open/unconfirm` |
| docType / docId | 9 / 579 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=579 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/aftersaleapi/open/unconfirm` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/aftersaleapi/open/unconfirm` |


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
| as_ids | array | 是 |  | 售后单id数组 |
| as_ids[] | number | 否 |  | 售后单id |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.success | array | 否 |  | 成功集合 |
| data.success[] | object | 否 |  |  |
| data.success[].as_id | number | 是 |  | 售后单号 |
| data.success[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.success[].message | string | 是 |  | 成功消息 |
| data.success[].details | string | 是 |  | 成功详细消息 |
| data.success[].is_success | boolean | 是 |  | 是否成功 |
| data.fail | array | 否 |  | 失败集合 |
| data.fail[] | object | 否 |  |  |
| data.fail[].as_id | number | 是 |  | 售后单号 |
| data.fail[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.fail[].message | string | 是 |  | 错误消息 |
| data.fail[].details | string | 是 |  | 错误详细消息 |
| data.fail[].is_success | boolean | 是 |  | 是否成功 |
| data.success_count | number | 否 |  | 成功数量 |
| data.fail_count | number | 否 |  | 失败数量 |
| msg | string | 否 |  |  |

### 请求示例

```json
{
  "as_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "fail": [
      {
        "as_id": 0,
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": true
      }
    ],
    "success": [
      {
        "as_id": 0,
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": true
      }
    ],
    "success_count": 0,
    "fail_count": 0
  }
}
```


### 异常示例

_无_


---

## 售后-确认收到货物（可分批确认）

`/open/webapi/aftersaleapi/confirmgoods`

| 项 | 内容 |
|---|---|
| 接口名称 | 售后-确认收到货物（可分批确认） |
| 接口路径 | `/open/webapi/aftersaleapi/confirmgoods` |
| docType / docId | 9 / 272 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=272 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/aftersaleapi/confirmgoods` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/aftersaleapi/confirmgoods` |


### 接口说明

多个售后单确认收货执行 。情况1： 多个售后单，如果某个售后单存在商品编码不存在报错，全部售后单执行失败。情况2 ： 多个售后单， 商品编码都存在 ，但是某条售后单因为qty数量原因报错或者其他原因报错的话， 报错的售后单上传失败 ，其他售后单上传成功。

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
| code | string | 否 |  | 返回代码 |
| msg | string | 否 |  | 失败消息 |
| data | object | 否 |  |  |
| data.success | array | 否 |  | 成功明细 |
| data.success[] | object | 否 |  |  |
| data.success[].as_id | number | 否 |  | 售后单号 |
| data.success[].outer_as_id | string | 否 |  | 平台退货退款单号 |
| data.success[].message | string | 否 |  | 消息 |
| data.success[].details | string | 否 |  | 消息明细 |
| data.success[].is_success | boolean | 否 |  | 是否成功 |
| data.fail | array | 否 |  | 失败明细 |
| data.fail[] | object | 否 |  |  |
| data.fail[].as_id | string | 否 |  | 售后单号 |
| data.fail[].outer_as_id | string | 否 |  | 平台退货退款单号 |
| data.fail[].message | string | 否 |  | 消息 |
| data.fail[].details | string | 否 |  | 消息明细 |
| data.fail[].is_success | string | 否 |  | 是否成功 |
| data.success_count | number | 否 |  | 成功数量 |
| data.fail_count | number | 否 |  | 失败数量 |

### 请求示例

```json
[
  {
    "wms_co_id": 0,
    "as_id": 0,
    "wh_id": 0,
    "return_id": "",
    "logistics_company": "",
    "remark": "",
    "l_id": "",
    "items": [
      {
        "qty_type": 0,
        "batch_id": "",
        "qty": 0,
        "sku_id": "",
        "expiration_date": "",
        "produced_date": ""
      }
    ]
  }
]
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": {
    "fail": [
      {
        "as_id": "",
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": ""
      }
    ],
    "success": [
      {
        "as_id": 0,
        "outer_as_id": "",
        "details": "",
        "message": "",
        "is_success": true
      }
    ],
    "success_count": 0,
    "fail_count": 0
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

## 售后上传（无信息件)

`/open/aftersale/noinfo/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 售后上传（无信息件) |
| 接口路径 | `/open/aftersale/noinfo/upload` |
| docType / docId | 9 / 124 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=124 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/aftersale/noinfo/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/aftersale/noinfo/upload` |


### 接口说明

更多售后API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=22&currentPage=1&pageSize=20

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
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].as_id | integer | 是 |  | 聚水潭售后单号，修改时必须大于0，新增时为0 |
| data[].as_date | string | 否 |  | 售后申请日期，如果为空，则为当前时间 |
| data[].outer_as_id | string | 否 |  | 外部售后单号，如果为空，聚水潭随机生成 |
| data[].type | string | 是 |  | 售后类型，目前仅支持“普通退货” |
| data[].logistics_company | string | 否 |  | 退货快递公司；可更新 |
| data[].l_id | string | 否 |  | 退货物流单号；可更新 |
| data[].shop_id | integer | 是 |  | 店铺编号，0代表线下，-1代表不知道店铺 |
| data[].shop_status | string | 否 |  | WAIT_SELLER_AGREE:买家已经申请退款，等待卖家同意,WAIT_BUYER_RETURN_GOODS:卖家已经同意退款，等待买家退货,WAIT_SELLER_CONFIRM_GOODS:买家已经退货，等待卖家确认收货,SELLER_REFUSE_BUYER:卖家拒绝退款,CLOSED:退款关闭(售后单未确认前填写该状态erp的售后单自动作废),SUCCESS:退款成功；可更新 |
| data[].question_type | string | 否 |  | 问题类型，最大长度100；可更新 |
| data[].question_reason | string | 否 |  | 退款原因，最大长度100；可更新 |
| data[].remark | string | 否 |  | 备注，最大长度500；可更新 |
| data[].freight | number | 否 |  | 卖家应退运费 |
| data[].wms_co_id | number | 否 |  | 收货仓编码 |
| data[].warehouse_type | number | 否 |  | 仓库；主仓 = 1, 销退仓 = 2, 进货仓 = 3, 次品仓 = 4, 自定义1仓=6，自定义2仓=7, 自定义3仓=8（只能选择已启用的仓） |
| data[]. items | array | 否 |  |  |
| data[]. items[] | object | 否 |  |  |
| data[]. items[].sku_id | string | 是 |  | 商家商品编码 |
| data[]. items[].qty | integer | 是 |  | 退货数量 |
| data[]. items[].amount | string | 否 |  | SKU退款金额 |
| data[]. items[].name | string | 否 |  | 商品名称，最大长度100 如果为空会尝试从 商家商品资料中填充 |
| data[]. items[].pic | string | 否 |  | 图片路径，最大长度300 如果为空会尝试从 商家商品资料中填充 |
| data[]. items[].properties_value | string | 否 |  | 属性规格，最大长度100 如果为空会尝试从 商家商品资料中填充 |
| data[]. items[].batch_id | string | 否 |  | 生产批次号 |
| data[]. items[].produced_date | string | 否 |  | 生产日期 |
| data[]. items[].expiration_date | string | 否 |  | 到期日 |
| data[]. items[].type | string | 是 |  | 目前仅支持“退货“ |
| data[]. items[].des | string | 否 |  | 备注 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 |  | 状态码 |
| issuccess | boolean | 否 |  | 执行结果 |
| msg | string | 否 |  | 提示信息 |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].as_id | string | 否 |  | 内部单号 |
| data[].outer_as_id | string | 否 |  | 外部单号 |
| data[].success | boolean | 否 |  | 结果： true:成功,false:失败 |
| data[].message | string | 否 |  | 提示信息 |

### 请求示例

```json
{
  "data": [
    {
      "as_id": 0,
      "as_date": "2021-12-30 14:00:00",
      "type": "普通退货",
      "l_id": "SFSD",
      "shop_id": 0,
      "freight": 0,
      "items": [
        {
          "sku_id": "#001",
          "qty": 1,
          "amount": 3,
          "type": "退货"
        }
      ]
    }
  ]
}
```


### 响应示例

```json
{
  "code": 0,
  "issuccess": true,
  "msg": "执行成功",
  "data": [
    {
      "as_id": 10158774,
      "outer_as_id": "",
      "success": true,
      "message": ""
    }
  ]
}
```


### 异常示例

```json
{
  "code": 130,
  "issuccess": false,
  "msg": "data 必填且最多100个",
  "requestId": "276077a316583726095673669e850f"
}
```


---

## 售后上传

`/open/aftersale/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 售后上传 |
| 接口路径 | `/open/aftersale/upload` |
| docType / docId | 9 / 41 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=41 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/aftersale/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/aftersale/upload` |


### 接口说明

注意：其他平台下载到ERP的售后单不可以通过接口修改。

 ERP内售后单状态流转 ：

 [买家发起普通退货]-->[生成售后单]-->待确认-->[卖家同意退款]-->[买家发货]-->[卖家收到货物]-->[处理退款事宜]-->已确定
 [买家发起仅退款]-->[生成售后单]-->待确认-->[卖家同意退款]-->[处理退款事宜]-->已确定
 [买家发起退货/退款]-->[生成售后单]-->待确认-->[买家取消申请]-->作废
 [买家发起换货申请]-->[生成售后单]-->待确认-->[卖家同意换货]-->[买家退货]-->[卖家收到退货]-->[卖家处理换货事宜]-->[买家收到换货后商品]-->已确认
 [买家发起补发申请]-->[生成售后单]-->待确认-->[卖家同意补发]-->[[卖家处理补发事宜]-->[买家收到补发商品]-->已确认

 关于售后单上传之后，订单状态未改变问题：
 售后上传不会改变订单状态：发货前的订单售后上传，订单会打上发货前售后的标签；发货后的订单售后上传，订单会打上发货后售后的标签；前后都上传，会打上两个标签
 关于自有商城上传售后单据如何拦截发货商品问题：
 1.发货前的订单有退款，可以先上传售后 仅退款 类型（ 如果对单据内所有的商品都进行仅退款订单会直接被取消，如果是部分商品售后需要搭配订单上传success退款成功状态对要退的商品拦截发货 ），确认售后单之后调用订单上传接口，items节点 refund_status传success，单据在发货的时候，即可拦截对应退款商品
 2.若有整单商品都需要退款，建议直接调用订单取消接口
 3.若发货前的单据，不想传输售后单，可以直接通过订单上传items节点 refund_status字段进行拦截发货商品
 注意：作废状态的售后单上传修改无效

 更多售后API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=22&currentPage=1&pageSize=20

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
| msg | string | 否 |  | 错误描述 |
| data | object | 否 |  | 数据集合 |
| data.datas | array | 否 |  |  |
| data.datas[] | object | 否 |  |  |
| data.datas[].msg | string | 是 |  | 执行结果描述 |
| data.datas[].as_id | integer | 是 |  | 内部售后单号 |
| data.datas[].issuccess | boolean | 是 |  | 是否成功 |
| data.datas[].so_id | string | 是 |  | 线上单号 |
| data.datas[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.datas[].o_id | integer | 是 |  | 内部单号 |
| data.datas[].id | integer | 是 |  | 0 |
| data.datas[].order_type | string | 是 |  | null |
| data.datas[].oaid | string | 是 |  | null |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 130 | "msg": "平台售后单号:12343567;线上单号1111111111111不存在退回类型的商品，请验证数据规范性！ |  |
| 0 |    "msg": "System.Exception: 找不到相应的订单[202210270944]" |  |
| 0 | "msg": "System.Exception: 平台售后单号:xxx线上单号不存在退回类型的商品，请验证数据规范性！", |  |


### 请求示例

```json
[
  {
    "shop_status": "wait",
    "question_type": "",
    "outer_as_id": "331805",
    "remark": "测试",
    "type": "其它",
    "good_status": "BUYER_RETURNED_GOODS",
    "shop_id": 10206764,
    "total_amount": 0,
    "so_id": "21120211072883513540",
    "logistics_company": "",
    "payment": 0,
    "l_id": "",
    "items": [
      {
        "amount": 34.45,
        "properties_value": "",
        "qty": 2,
        "name": "",
        "sku_id": "sn2",
        "pic": "",
        "type": "退货",
        "outer_oi_id": ""
      }
    ],
    "refund": 0
  }
]
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "datas": [
      {
        "msg": "",
        "as_id": 0,
        "issuccess": true,
        "so_id": "",
        "outer_as_id": "",
        "o_id": 0,
        "id": 0,
        "order_type": "",
        "oaid": ""
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

## 销售退仓-实际收货查询

`/open/aftersale/received/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 销售退仓-实际收货查询 |
| 接口路径 | `/open/aftersale/received/query` |
| docType / docId | 9 / 40 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=9&docId=40 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/aftersale/received/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/aftersale/received/query` |


### 接口说明

系统相关界面：【订单】------【销售退仓】

 查不到淘系和拼多多平台订单的线上单号so_id，并且拼多多的单据只返回近3个月的数据

 1.业务说明：实际售后查询查的是售后退货卖家点击确认收到货物之后产生的退仓单，实际入仓的退货数量，存在取消收到货物产生的负数的退仓单。
 2. 请求参数中start_ts的说明：使用ts的查询条件是唯一可避免分页查询过程中因数据变动而导致的漏单问题，原因是该查询条件是数据库中的时间戳，sql server中的 行版本号 。只要当前这条数据在数据库中有变化任何字段变化ts的值都会自增，全表唯一的自增值，非业务上做得时间值更新。使用ts的查询模板
 第一次请求：{" start_ts ":1." is_get_total ":false," page_index ":1." page_size ":100}
 第二次请求：{" start_ts ":传第一次返回的最大ts值." is_get_total ":false," page_index ":1." page_size ":100}

 更多售后API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=22&currentPage=1&pageSize=20

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
| page_size | integer | 否 | 50 | 默认30，最大不超过50 |
| modified_begin | string | 否 | 2021-12-03 15:37:44 | 修改开始时间,开始时间和结束时间必须同时存在，时间间隔不能超过七天 |
| modified_end | string | 否 | 2021-12-10 15:37:44 | 修改结束时间,开始时间和结束时间必须同时存在，时间间隔不能超过七天 |
| so_ids | array | 否 |  | 外部订单号列表 |
| so_ids[] | string | 否 |  |  |
| start_ts | integer | 否 |  | 时间戳 |
| o_ids | array | 否 |  | ERP内部订单号 |
| o_ids[] | string | 否 |  |  |
| page_index | integer | 否 | 1 | 第几页，从1开始 |
| shop_id | integer | 否 |  | 退货店铺 |
| owner_co_ids | string | 否 |  | 货主编码（不传值，查询所有单据；传值为0，只查询自营单据；；若查询某个特定货主单据，需传货主编码，有多个用逗号隔开） |
| date_type | integer | 否 | 0 | 日期类型，0:修改时间，1:创建日期，4:实际出/入库时间 |
| as_ids | array | 否 |  | 售后单号列表,最大20 |
| as_ids[] | integer | 否 |  |  |
| io_ids | array | 否 |  | 退仓单号列表,最大20 |
| io_ids[] | integer | 否 |  |  |
| wms_co_id | number | 否 |  | 收货仓编码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  |  |
| data.page_size | integer | 否 | 30 | 每页多少条 |
| data.page_index | integer | 否 | 1 | 第几页 |
| data.data_count | integer | 否 | 2 | 总条数 |
| data.page_count | integer | 否 | 1 | 总页数 |
| data.has_next | boolean | 否 | false | 是否有下一页 |
| data.datas | array | 否 |  | 数据集合 |
| data.datas[] | object | 否 |  |  |
| data.datas[].io_id | integer | 否 | 1396869 | 退仓单号（唯一值） |
| data.datas[].o_id | integer | 否 | 3782517 | 内部单号 |
| data.datas[].so_id | string | 否 | 2231EW | 线上单号 |
| data.datas[].as_id | integer | 否 | 21334 | 售后订单号 |
| data.datas[].owner_co_id | number | 否 |  | 货主编码 |
| data.datas[].owner_co_name | string | 否 |  | 货主名称 |
| data.datas[].l_id | string | 否 |  | 物流单号 |
| data.datas[].logistics_company | string | 否 |  | 物流公司名称 |
| data.datas[].creator | number | 否 |  | 创建人编码 |
| data.datas[].creator_name | string | 否 |  | 创建人名称 |
| data.datas[].io_date | string | 否 | 2021-09-2915:37:45 | 入库日期 |
| data.datas[].warehouse | string | 否 | 销售退货仓库 | 仓库名称 |
| data.datas[].modified | string | 否 | 2021-09-2915:37:45 | 修改时间 |
| data.datas[].lc_id | string | 否 |  | 物流公司编码 |
| data.datas[].shop_id | integer | 否 | 10156621 | 店铺编号 |
| data.datas[].aftersale_remark | string | 否 |  | 售后备注 |
| data.datas[].ts | number | 否 |  | 时间戳 |
| data.datas[].status | string | 否 |  | 单据状态(销售退仓单状态（,Confirmed:已确认,Cancelled:作废） |
| data.datas[].wh_id | integer | 否 | 2 | 仓库代码（1主仓，2销退仓，3进货仓，4次品仓） |
| data.datas[].wms_co_id | integer | 否 | 12252 | 分仓编号 |
| data.datas[].drp_co_name | string | 否 |  | 分销商名称 |
| data.datas[].drp_co_id_to | integer | 否 |  | 供销商编号 |
| data.datas[].drp_co_id_from | integer | 否 |  | 分销商编号 |
| data.datas[].type | string | 否 |  | 售后类型：普通退货，其它，拒收退货，仅退款，投诉，补发，换货，维修 |
| data.datas[].items | array | 否 |  | 商品集合 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].io_id | integer | 否 | 1396869 | 退仓单号 |
| data.datas[].items[].sku_id | string | 否 | EDENBO121200T175 | 商品编码 |
| data.datas[].items[].i_id | string | 否 |  | 款式编码 |
| data.datas[].items[].unit | string | 否 |  | 单位 |
| data.datas[].items[].qty | integer | 否 | 1 | 商品数量 |
| data.datas[].items[].name | string | 否 |  | 商品名称 |
| data.datas[].items[].properties_value | string | 否 | 通色175 | 属性值 |
| data.datas[].items[].sale_price | number | 否 | 1.0 | 销售价格 |
| data.datas[].items[].sale_amount | number | 否 | 1.0 | 销售总金额 |
| data.datas[].items[].ioi_id | integer | 否 |  | 退仓子单号，用于区分货品行的行号 |
| data.datas[].items[].raw_so_id | string | 否 |  | 原始线上单号（“shop_id:so_id”） |
| data.datas[].items[].bu_id | number | 否 |  | 运营云仓编码 |
| data.datas[].batchs | array | 否 |  | 批次信息集合 |
| data.datas[].batchs[] | object | 否 |  |  |
| data.datas[].batchs[].batch_no | string | 否 |  | 批次号 |
| data.datas[].batchs[].ioi_id | number | 否 |  | 退仓子单号，用于区分货品行的行号 |
| data.datas[].batchs[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].batchs[].qty | integer | 否 |  | 商品数量 |
| data.datas[].batchs[].product_date | string | 否 |  | 批次日期 |
| data.datas[].batchs[].supplier_id | string | 否 |  | 供应商编号 |
| data.datas[].batchs[].supplier_name | string | 否 |  | 供应商名称 |
| data.datas[].batchs[].expiration_date | string | 否 |  | 有效期至 |
| data.datas[].sns | array | 否 |  |  |
| data.datas[].sns[] | object | 否 |  |  |
| data.datas[].sns[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].sns[].sn | string | 否 |  | SN码 |

### 请求示例

```json
{
  "o_ids": [],
  "shop_id": "15847827",
  "date_type": 0,
  "so_ids": [],
  "page_index": 1,
  "modified_begin": "2024-10-29 10:33:33",
  "modified_end": "2024-10-29 10:35:33",
  "page_size": 50
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {
    "datas": [
      {
        "lc_id": null,
        "as_id": 1370005179,
        "drp_co_name": null,
        "drp_co_id_from": null,
        "type": "换货",
        "drp_co_id": null,
        "so_id": "305040350015655",
        "o_id": 387855,
        "modified": "2024-10-29 10:34:33",
        "currency": null,
        "creator": 12854967,
        "aftersale_remark": "",
        "io_date": "2024-10-29 10:34:33",
        "warehouse": "川梣测试公司销退仓",
        "io_id": 35758,
        "labels": null,
        "shop_id": 15847827,
        "batchs": [],
        "wms_co_id": 11053062,
        "wh_id": 2,
        "drp_co_id_to": null,
        "sns": [],
        "creator_name": "川梣",
        "logistics_company": "",
        "l_id": "",
        "items": [
          {
            "i_id": "0000000000210",
            "unit": "盒",
            "properties_value": "10g*10袋",
            "qty": 1,
            "combine_sku_id": null,
            "name": "肺宁冲剂",
            "sku_id": "0000000000210",
            "ioi_id": 2698529,
            "sale_price": 0,
            "io_id": 35758,
            "sale_amount": 0
          }
        ],
        "status": "Confirmed",
        "ts": 4046894641
      }
    ],
    "requestId": null,
    "page_index": 1,
    "has_next": false,
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
