# 聚水潭开放平台 · 入库API（线下版）

> 抓取日期：2026-11-23  
> 分类：入库API（docType=7）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=7&docId=270

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 生成采购入库单-支持批量 | `/open/webapi/wmsapi/purchasein/createbatch` | 270 | [打开](https://openweb.jushuitan.com/dev-doc?docType=7&docId=270) |
| 采购入库取消 | `/open/jushuitan/purchasein/cancel` | 317 | [打开](https://openweb.jushuitan.com/dev-doc?docType=7&docId=317) |
| 批量录入唯一码 | `/open/webapi/wmsapi/skusn/batchadd/simple` | 670 | [打开](https://openweb.jushuitan.com/dev-doc?docType=7&docId=670) |
| 批量录入箱唯一码 | `/open/webapi/wmsapi/packsn/batchadd` | 671 | [打开](https://openweb.jushuitan.com/dev-doc?docType=7&docId=671) |
| 采购入库查询 | `/open/webapi/wmsapi/purchasein/purchaseinquery` | 901 | [打开](https://openweb.jushuitan.com/dev-doc?docType=7&docId=901) |
| 生产批次管理创建 | `/open/webapi/wmsapi/producedbatch/createproducedbatch` | 1137 | [打开](https://openweb.jushuitan.com/dev-doc?docType=7&docId=1137) |

## 目录

- [生成采购入库单-支持批量](#生成采购入库单-支持批量)
- [采购入库取消](#采购入库取消)
- [批量录入唯一码](#批量录入唯一码)
- [批量录入箱唯一码](#批量录入箱唯一码)
- [采购入库查询](#采购入库查询)
- [生产批次管理创建](#生产批次管理创建)

---

## 生成采购入库单-支持批量

`/open/webapi/wmsapi/purchasein/createbatch`

| 项 | 内容 |
|---|---|
| 接口名称 | 生成采购入库单-支持批量 |
| 接口路径 | `/open/webapi/wmsapi/purchasein/createbatch` |
| docType / docId | 7 / 270 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=7&docId=270 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/purchasein/createbatch` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/purchasein/createbatch` |


### 接口说明

更多采购入库API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=20&currentPage=1&pageSize=20

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
| code | string | 否 |  | 编码 |
| msg | string | 否 |  | 消息 |
| request_id | string | 否 |  |  |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].msg | string | 是 |  | 返回信息 |
| data[].is_success | string | 是 |  | 是否执行成功 |
| data[].external__id | string | 是 |  | 外部单号 |
| data[].io_id | number | 是 |  | 采购入库单号 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 0 | {     "code": 0,     "act": 0,     "data": [         {             "external_id": "80648860",             "io_id": 0,             "pack_ids": null,             "is_success": false,             "message": "只允许录入整数"         }     ],     "msg": null,     "msg_type": "string",     "request_id": null,     "cookie": null } |  |
| 0 | { 	"msg": null, 	"code": 0, 	"data": [ 		{ 			"pack_ids": null, 			"external_id": "HZRKYX00003548", 			"message": "商品00001733，生产批次号240502，生产日期2024-05-11存在重复数据，请核查后重试。", 			"is_success": false, 			"io_id": 0 		} 	], 	"msg_type": "string", 	"request_id": null } |  |
| 0 | {     "code": 0,     "act": 0,     "data": [         {             "external_id": "2025-04-17-01745",             "io_id": 0,             "pack_ids": null,             "is_success": false,             "message": "公司[XXX]不存在商品编码[hgz]。\r\n请在对应公司中维护好商品资料后，再重新操作。"         }     ],     "msg": null,     "msg_type": "string",     "request_id": null,     "cookie": null } |  |
| 199 | {"code":199,"msg":"调用太频繁，请稍后再试!"} |  |
| 10015 | {"msg":"请求参数错误(Uid)!"，"code": 10015, "data": null. "msg_type": "string",'request id": null} |  |
|  |  |  |


### 请求示例

```json
[
  {
    "po_id": 13924,
    "is_confirm": true,
    "channel": "open",
    "external_id": "20230410001",
    "supplier_id": 8947478,
    "items": [
      {
        "qty": 8,
        "sku_id": "A001"
      }
    ]
  }
]
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": [
    {
      "msg": "上传成功",
      "is_success": true,
      "external__id": "20230410001",
      "io_id": 18283
    }
  ],
  "request_id": null
}
```


### 异常示例

_无_


---

## 采购入库取消

`/open/jushuitan/purchasein/cancel`

| 项 | 内容 |
|---|---|
| 接口名称 | 采购入库取消 |
| 接口路径 | `/open/jushuitan/purchasein/cancel` |
| docType / docId | 7 / 317 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=7&docId=317 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/purchasein/cancel` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/purchasein/cancel` |


### 接口说明

erp账号开启了奇门oms场景的情况下 不支持取消

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
| io_ids | array | 否 |  | 入库单号，与线上单号不能同时为空，两者都存在时取io_ids，最多20个 |
| io_ids[] | number | 否 |  |  |
| so_ids | array | 否 |  | 线上单号，与入库单号不能同时为空，两者都存在时取io_ids，最多20个 |
| so_ids[] | string | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 |  | 返回码，0表示成功 |
| issuccess | string | 是 |  | 是否执行成功 |
| msg | string | 是 |  | 执行信息 |

### 请求示例

```json
{
  "field_7": "",
  "field_6": ""
}
```


### 响应示例

```json
{
  "field_10": "",
  "field_8": "",
  "field_9": ""
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

## 批量录入唯一码

`/open/webapi/wmsapi/skusn/batchadd/simple`

| 项 | 内容 |
|---|---|
| 接口名称 | 批量录入唯一码 |
| 接口路径 | `/open/webapi/wmsapi/skusn/batchadd/simple` |
| docType / docId | 7 / 670 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=7&docId=670 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/skusn/batchadd/simple` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/skusn/batchadd/simple` |


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
| sku_sn_list | array | 是 |  | 最大500 |
| sku_sn_list[] | object | 否 |  |  |
| sku_sn_list[].sku_id | string | 是 | XWY-1 | 商品编码 |
| sku_sn_list[].sn | string | 是 | XWY-200111 | 唯一码\|序列号 |
| status | number | 否 |  | 唯一码状态，0:待入库，1：入库 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | boolean | 否 |  |  |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "sku_sn_list": [
    {
      "sku_id": "XWY-1",
      "sn": "XWY-100111"
    },
    {
      "sku_id": "XWY-1",
      "sn": "XWY-100222"
    },
    {
      "sku_id": "XWY-1",
      "sn": "XWY-100333"
    }
  ],
  "status": 1
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": true,
  "request_id": ""
}
```


### 异常示例

_无_


---

## 批量录入箱唯一码

`/open/webapi/wmsapi/packsn/batchadd`

| 项 | 内容 |
|---|---|
| 接口名称 | 批量录入箱唯一码 |
| 接口路径 | `/open/webapi/wmsapi/packsn/batchadd` |
| docType / docId | 7 / 671 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=7&docId=671 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/packsn/batchadd` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/packsn/batchadd` |


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
| pack_sn_list | array | 是 |  |  |
| pack_sn_list[] | object | 否 |  |  |
| pack_sn_list[].sku_id | string | 是 | XWY-1 | 商品编码 |
| pack_sn_list[].sn | string | 是 | XWY-100111 | 唯一码\|序列号 |
| pack_sn_list[].pack_sku_sn_list | array | 是 |  | 箱唯一码关联的普通唯一码列表 |
| pack_sn_list[].pack_sku_sn_list[] | string | 否 | ["XX-2111","XX-2121"] | 唯一码号 |
| status | number | 否 | 1 | 1:待入库 2:入库 3:出库，其它值：待入库（不传默认是查询待入库单据） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | boolean | 否 |  |  |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "status": 2,
  "pack_sn_list": [
    {
      "sku_id": "XWY-1",
      "sn": "XWY-100111",
      "pack_sku_sn_list": [
        "XX-111",
        "XX-112"
      ]
    },
    {
      "sku_id": "XWY-1",
      "sn": "XWY-100222",
      "pack_sku_sn_list": [
        "XX-211",
        "XX-212"
      ]
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": true,
  "request_id": ""
}
```


### 异常示例

_无_


---

## 采购入库查询

`/open/webapi/wmsapi/purchasein/purchaseinquery`

| 项 | 内容 |
|---|---|
| 接口名称 | 采购入库查询 |
| 接口路径 | `/open/webapi/wmsapi/purchasein/purchaseinquery` |
| docType / docId | 7 / 901 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=7&docId=901 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/purchasein/purchaseinquery` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/purchasein/purchaseinquery` |


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
| page_index | integer | 否 | 1 | 第几页，从1开始 |
| page_size | integer | 否 | 30 | 默认30，最大不超过50 |
| modified_begin | string | 否 | 2024-3-1 | 修改起始时间,起始时间和结束时间必须同时存在，时间间隔不能超过七天，与采购单号不能同时为空 |
| modified_end | string | 否 | 2024-5-16 | 修改起始时间,起始时间和结束时间必须同时存在，时间间隔不能超过七天，与采购单号不能同时为空 |
| po_ids | array | 否 |  | 采购单号 与修改时间不能同时为空.采购单号最大不能超过30条 |
| po_ids[] | integer | 否 | 1 |  |
| io_ids | array | 否 |  | 入库单号 与修改时间不能同时为空.采购入库单号最大不能超过30条 |
| io_ids[] | integer | 否 | 1 |  |
| statuss | array | 否 |  | 单据状态;不填写默认查询已入库状态(WaitConfirm待入库;Confirmed已入库;Cancelled取消；Delete作废；Archive 结算；OuterConfirming 外部确认中) |
| statuss[] | string | 否 | @string |  |
| so_ids | array | 否 |  | 线上单号 与修改时间不能同时为空 |
| so_ids[] | string | 否 | @string |  |
| start_ts | integer | 否 | 1 | 时间戳，sql server中的行版本号，该字段查询防止分页过程中漏单（使用时默认只返回已入库数据，如果需要全量 需要搭配statuss使用） |
| is_get_total | boolean | 否 | @boolean | 是否查询总条数默认true，如果使用start_ts查询，该值传false否则影响查询效率 |
| date_type | integer | 否 | 0 | 0:修改时间，modified。 2:入库时间 io_date，未传入时默认为0 |
| seller_ids | array | 否 |  | 供应商编号（需要和modifiedBegin，modifiedEnd一起查询） |
| seller_ids[] | number | 否 |  |  |
| owner_co_id | integer | 否 |  | 货主编码（三方仓商家不传货主默认查自身数据，若查所有货主需传值：2147483647） |
| wms_co_id | integer | 否 |  | 分仓编码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| msg | string | 否 |  |  |
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.datas | array | 否 |  |  |
| data.datas[] | object | 否 |  |  |
| data.datas[].po_id | number | 否 |  | 采购单号 |
| data.datas[].io_date | string | 否 |  | 入库日期 |
| data.datas[].remark | string | 否 |  | 备注 nvarchar(1000) |
| data.datas[].warehouse | string | 否 |  | 仓库名称 nvarchar(40) |
| data.datas[].type | string | 否 |  | 进仓类型 nvarchar(20) |
| data.datas[].tax_rate | number | 否 |  | 税率 decimal(14,2) |
| data.datas[].io_id | number | 否 |  | 入库单号 |
| data.datas[].labels | string | 否 |  | 标签 nvarchar(200) |
| data.datas[].archived | string | 否 |  | 财务审核日期 |
| data.datas[].merge_so_id | string | 否 |  | 预约单号 varchar(300) |
| data.datas[].items | array | 否 |  | 商品明细信息 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].ioi_id | integer | 否 |  | 入库子单号 |
| data.datas[].items[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].items[].i_id | string | 否 |  | 款式编码 nvarchar(64) |
| data.datas[].items[].unit | string | 否 |  | 单位 nvarchar(20) |
| data.datas[].items[].name | string | 否 |  | 商品名称 nvarchar(100) |
| data.datas[].items[].qty | number | 否 |  | 入库数量 |
| data.datas[].items[].io_id | integer | 否 |  | 入库单号 |
| data.datas[].items[].cost_price | number | 否 |  | 单价 numeric(12,4) |
| data.datas[].items[].cost_amount | number | 否 |  | 金额 decimal(12,2) |
| data.datas[].items[].remark | string | 否 |  | 商品明细备注 nvarchar(500) |
| data.datas[].items[].batch_no | string | 否 |  | 批次号，需开启相关业务配置 |
| data.datas[].items[].tax_rate | integer | 否 |  | 税率 |
| data.datas[].items[].properties_value | string | 否 |  | 颜色规格 |
| data.datas[].wms_co_id | number | 否 |  | 分仓编号 |
| data.datas[].owner_co_name | string | 否 |  | 货主名称 |
| data.datas[].wh_id | string | 否 |  | 仓库编号；主仓=1，销退仓=2，进货仓=3，次品仓=4，自定义1仓=6，自定义2仓=7，自定义3仓=8 |
| data.datas[].so_id | string | 否 |  | 线上单号:对应采购入库页面的线上订单号(且对应采购入库上传的external_id) varchar(300) |
| data.datas[].modified | string | 否 |  | 修改时间 |
| data.datas[].sns | array | 否 |  | 唯一码集合 获取该节点系统中相关业务项需配置（对应erp基础设置商品唯一码开关） |
| data.datas[].sns[] | object | 否 |  |  |
| data.datas[].sns[].sku_id | string | 否 |  |  |
| data.datas[].sns[].sn | string | 否 |  |  |
| data.datas[].creator_name | string | 否 |  | 制单人 nvarchar(10) |
| data.datas[].supplier_name | string | 否 |  | 供应商名称 nvarchar(200) |
| data.datas[].supplier_id | number | 否 |  | 供应商编号 |
| data.datas[].batchs | array | 否 |  | 生产批次集合 获取该节点系统中相关业务项需配置（对应erp基础设置开启生产批次管理 如果是分仓数据 分仓也需要开启） |
| data.datas[].batchs[] | object | 否 |  | 批次节点 |
| data.datas[].batchs[].batch_no | string | 否 |  | 批次号 varchar(50) |
| data.datas[].batchs[].sku_id | number | 否 |  | 商品编码 nvarchar(64) |
| data.datas[].batchs[].qty | string | 否 |  | 数量 |
| data.datas[].batchs[].product_date | string | 否 |  | 批次日期 |
| data.datas[].batchs[].supplier_id | integer | 否 |  | 供应商编号 |
| data.datas[].batchs[].supplier_name | string | 否 |  | 供应商名称 nvarchar(100) |
| data.datas[].batchs[].expiration_date | string | 否 |  | 有效期至 |
| data.datas[].batchs[].ioi_id | string | 否 |  | 子单号；需开启基础设置：单据明细批次透出 和 进出仓单据跟踪生产批次 |
| data.datas[].f_status | string | 否 |  | 财审状态，WaitConfirm=待审核;Confirmed=已审核 varchar(20) |
| data.datas[].status | string | 否 |  | 状态(WaitConfirm待入库;Confirmed已入库;Cancelled取消；Archive 归档；OuterConfirming 外部确认中) varchar(20) |
| data.datas[].out_io_id | string | 否 |  | 外部单号 varchar(150) |
| data.datas[].ts | integer | 否 |  | 数据库行版本号：https://docs.microsoft.com/zh-cn/sql/t-sql/data-types/rowversion-transact-sql?view=sql-server-ver16 |
| data.datas[].lock_wh_id | number | 否 |  | 虚拟仓编码 |
| data.datas[].extend_remark | string | 否 |  | 备注2 varchar(500) |
| data.datas[].l_id | string | 否 |  | 物流单号 varchar(200) |
| data.datas[].logistics_company | string | 否 |  | 物流公司 nvarchar(60) |
| data.page_index | number | 否 |  | 第几页 |
| data.has_next | boolean | 否 |  | 是否有下一页 |
| data.data_count | number | 否 |  | 总条数 |
| data.page_count | number | 否 |  | 总页数 |
| data.page_size | number | 否 |  | 每页多少条 |

### 请求示例

```json
{
  "start_ts": 1,
  "date_type": 0,
  "so_ids": [],
  "page_index": 1,
  "modified_begin": "2024-3-1",
  "modified_end": "2024-5-16",
  "is_get_total": "@boolean",
  "io_ids": [],
  "statuss": [],
  "page_size": 30,
  "po_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "datas": [
      {
        "po_id": 0,
        "remark": "",
        "type": "",
        "tax_rate": 0,
        "archived": "",
        "so_id": "",
        "modified": "",
        "supplier_name": "",
        "f_status": "",
        "out_io_id": "",
        "lock_wh_id": 0,
        "io_date": "",
        "warehouse": "",
        "extend_remark": "",
        "io_id": 0,
        "labels": "",
        "merge_so_id": "",
        "batchs": [
          {
            "batch_no": "",
            "qty": "",
            "sku_id": 0,
            "supplier_name": "",
            "expiration_date": "",
            "supplier_id": 0,
            "ioi_id": "",
            "product_date": ""
          }
        ],
        "wms_co_id": 0,
        "wh_id": "",
        "sns": [
          {
            "sku_id": "",
            "sn": ""
          }
        ],
        "creator_name": "",
        "logistics_company": "",
        "l_id": "",
        "items": [
          {
            "i_id": "",
            "batch_no": "",
            "sku_id": "",
            "remark": "",
            "ioi_id": 0,
            "tax_rate": 0,
            "io_id": 0,
            "unit": "",
            "cost_amount": 0,
            "properties_value": "",
            "qty": 0,
            "name": "",
            "cost_price": 0
          }
        ],
        "supplier_id": 0,
        "status": "",
        "ts": ""
      }
    ],
    "page_index": 0,
    "has_next": true,
    "data_count": 0,
    "page_count": 0,
    "page_size": 0
  }
}
```


### 异常示例

_无_


---

## 生产批次管理创建

`/open/webapi/wmsapi/producedbatch/createproducedbatch`

| 项 | 内容 |
|---|---|
| 接口名称 | 生产批次管理创建 |
| 接口路径 | `/open/webapi/wmsapi/producedbatch/createproducedbatch` |
| docType / docId | 7 / 1137 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=7&docId=1137 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/producedbatch/createproducedbatch` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/producedbatch/createproducedbatch` |


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
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | A-6 | 商品编码 |
| items[].batch_id | string | 是 | 20241226 | 生产批次号 |
| items[].produced_date | string | 是 | 2024-12-26 | 生产日期 |
| items[].expiration_date | string | 是 | 2024-12-28 | 有效期至 |
| items[].supplier_id | number | 否 |  | 供应商编码 |
| items[].udi | string | 否 |  | UDI |
| items[].remark | string | 否 |  | 备注 |
| items[].is_enable | boolean | 否 |  | 是否启用 |
| wms_co_id | number | 否 |  | 仓储方ID |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | boolean | 否 |  |  |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "wms_co_id": 0,
  "items": [
    {
      "batch_id": "20241226",
      "is_enable": true,
      "sku_id": "A-6",
      "remark": "",
      "udi": "",
      "expiration_date": "2024-12-28",
      "supplier_id": 0,
      "produced_date": "2024-12-26"
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": true,
  "request_id": ""
}
```


### 异常示例

_无_


---
