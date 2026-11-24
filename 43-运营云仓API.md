# 聚水潭开放平台 · 运营云仓API（线下版）

> 抓取日期：2026-11-23  
> 分类：运营云仓API（docType=43）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=43&docId=340

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 虚拟仓调拨单据分页接口 | `/open/webapi/itemapi/lockwarehouse/getlwhallocationlist` | 340 | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=340) |
| 虚拟仓分配归还单据分页接口 | `/open/webapi/itemapi/lockwarehouse/getlwhoperationlist` | 341 | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=341) |
| 虚拟仓调拨单创建接口 | `/open/webapi/itemapi/lockwarehouse/lwhallocationcreate` | 342 | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=342) |
| 虚拟仓分配/归还单据创建接口 | `/open/webapi/itemapi/lockwarehouse/lwhoperationcreate` | 343 | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=343) |
| 获取虚拟仓列表 | `/open/webapi/itemapi/lockwarehouse/getwarehouselist` | 490 | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=490) |
| 虚拟仓商品库存查询 | `/open/webapi/itemapi/iteminventory/getvirtualstock` | 625 | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=625) |
| 创建/更新虚拟仓采购申请 | `/open/webapi/itemapi/lockwarehouse/lockpurchase/createorupdatepurchase` | 799 | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=799) |
| 查询采购申请（包含虚拟仓和非虚拟仓） | `/open/webapi/itemapi/lockwarehouse/lockpurchase/getpagelockpurchases` | 802 | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=802) |
| 获取运营云仓出入库台账 | `/open/webapi/itemapi/lockwarehouse/getlwhinout` | 1648 | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=1648) |

## 目录

- [虚拟仓调拨单据分页接口](#虚拟仓调拨单据分页接口)
- [虚拟仓分配归还单据分页接口](#虚拟仓分配归还单据分页接口)
- [虚拟仓调拨单创建接口](#虚拟仓调拨单创建接口)
- [虚拟仓分配/归还单据创建接口](#虚拟仓分配归还单据创建接口)
- [获取虚拟仓列表](#获取虚拟仓列表)
- [虚拟仓商品库存查询](#虚拟仓商品库存查询)
- [创建/更新虚拟仓采购申请](#创建更新虚拟仓采购申请)
- [查询采购申请（包含虚拟仓和非虚拟仓）](#查询采购申请包含虚拟仓和非虚拟仓)
- [获取运营云仓出入库台账](#获取运营云仓出入库台账)

---

## 虚拟仓调拨单据分页接口

`/open/webapi/itemapi/lockwarehouse/getlwhallocationlist`

| 项 | 内容 |
|---|---|
| 接口名称 | 虚拟仓调拨单据分页接口 |
| 接口路径 | `/open/webapi/itemapi/lockwarehouse/getlwhallocationlist` |
| docType / docId | 43 / 340 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=43&docId=340 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/lockwarehouse/getlwhallocationlist` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/lockwarehouse/getlwhallocationlist` |


### 接口说明

系统相关界面：【虚拟仓库存分配】

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
| io_id | number | 否 | 9804761 | 单据编号 |
| sku_id | string | 否 | 00000035098002 | 商品编码列表,多个逗号隔开，最多50个 |
| out_lwh_id | number | 否 | 818 | 调出虚拟仓编号 |
| date_type | number | 否 | 0 | 时间类型（0,1） 0:创建时间，1：审核时间 默认：创建时间 |
| date_begin | string | 否 | 2023-02-03 10:44:35 | 开始时间，开始时间,开始时间结束时间都不传默认查询3个月内 |
| date_end | string | 否 | 2023-02-03 10:44:36 | 结束时间，开始时间,开始时间结束时间都不传默认查询3个月内 |
| so_id | string | 否 | 20230203003 | 外部单号，保持唯一 |
| status | string | 否 | Creating | 状态：Creating：草拟，WaitConfirm：待审核，Confirmed：已生效 |
| page | object | 是 |  | 分页 |
| page.page_size | integer | 是 | 50 | 页大小 |
| page.current_page | integer | 是 | 1 | 第几页 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 状态码，0代表成功 |
| data | object | 否 |  |  |
| data.page | object | 否 |  | 分页 |
| data.page.current_page | number | 否 |  | 当前页数 |
| data.page.page_size | number | 否 |  | 每页最大条数 |
| data.page.count | number | 否 |  | 总条数 |
| data.page.pages | number | 否 |  | 总页数 |
| data.page.index | number | 否 |  | 索引下标 |
| data.list | array | 否 |  |  |
| data.list[] | object | 否 |  |  |
| data.list[].io_id | number | 是 |  | 调拨编号 |
| data.list[].out_lwh_id | number | 是 |  | 调出虚拟仓编号 |
| data.list[].out_lwh_name | string | 是 |  | 调出虚拟仓名称 |
| data.list[].in_lwh_id | number | 是 |  | 调入虚拟仓编号 |
| data.list[].in_lwh_name | string | 是 |  | 调入虚拟仓名称 |
| data.list[].status | string | 是 |  | 单据状态 |
| data.list[].labels | string | 是 |  | 标签 |
| data.list[].remark | string | 是 |  | 备注 |
| data.list[].wms_co_id | number | 是 |  | 仓储方编码 |
| data.list[].wms_name | string | 是 |  | 仓储方名称 |
| data.list[].created | string | 是 |  | 创建时间 |
| data.list[].io_date | string | 是 |  | 审核时间 |
| data.list[].items | array | 是 |  | 商品明细 |
| data.list[].items[] | object | 否 |  |  |
| data.list[].items[].i_id | string | 是 |  | 款式编码 |
| data.list[].items[].sku_id | string | 是 |  | 商品编码 |
| data.list[].items[].sku_name | string | 是 |  | 商品名称 |
| data.list[].items[].properties_value | string | 是 |  | 颜色规格 |
| data.list[].items[].qty | number | 是 |  | 库存数 |
| data.list[].items[].lock_qty | number | 是 |  | 虚拟仓可用数 |
| data.list[].items[].target_lwh_lockable_qty | number | 是 |  | 调入虚拟仓可用数 |
| data.list[].items[].pick_able_qty | number | 是 |  | 虚拟仓可配数 |
| data.list[].items[].public_qty | number | 是 |  | 公有可用数 |
| data.list[].items[].cost_price | number | 是 |  | 成本价 |
| data.list[].so_id | string | 是 |  | 外部单号 |
| data.list[].type | string | 是 |  | 虚单据类型：虚拟仓调出（调拨单据） |
| msg | null | 否 |  | msg |
| request_id | null | 否 |  | request_id |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 10015 | "msg": "分页参数错误" |  |


### 请求示例

```json
{
  "date_type": 0,
  "date_begin": "2023-02-03 10:44:35",
  "so_id": "20230203003",
  "sku_id": "00000035098002",
  "date_end": "2023-02-03 10:44:36",
  "page": {
    "current_page": 1,
    "page_size": 50
  },
  "out_lwh_id": 818,
  "io_id": 9804761,
  "status": "Creating"
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": {
    "page": {
      "pages": 1,
      "count": 1,
      "index": 1,
      "current_page": 1,
      "page_size": 50
    },
    "list": [
      {
        "created": "2023-02-03 10:44:35.507",
        "io_date": "2023-02-03 10:44:35.493",
        "remark": "w3",
        "type": "虚拟仓调出",
        "in_lwh_name": "testws",
        "out_lwh_id": 818,
        "labels": "",
        "io_id": 9804761,
        "wms_name": "（本仓）",
        "wms_co_id": 12252,
        "so_id": "20230203003",
        "in_lwh_id": 798,
        "out_lwh_name": "7698911",
        "items": [
          {
            "i_id": "0723",
            "lock_qty": 0,
            "properties_value": "虾红;M",
            "qty": 1,
            "public_qty": -200,
            "sku_name": "V领t恤",
            "target_lwh_lockable_qty": 200,
            "sku_id": "00000035098002",
            "pick_able_qty": 0,
            "cost_price": 0
          }
        ],
        "status": "草拟"
      }
    ]
  },
  "request_id": "2760827116754050194582292e5aa9"
}
```


### 异常示例

```json
{
  "msg": "分页参数错误",
  "code": 10015,
  "data": null,
  "request_id": "2760827116753927848631634e5aa1"
}
```


---

## 虚拟仓分配归还单据分页接口

`/open/webapi/itemapi/lockwarehouse/getlwhoperationlist`

| 项 | 内容 |
|---|---|
| 接口名称 | 虚拟仓分配归还单据分页接口 |
| 接口路径 | `/open/webapi/itemapi/lockwarehouse/getlwhoperationlist` |
| docType / docId | 43 / 341 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=43&docId=341 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/lockwarehouse/getlwhoperationlist` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/lockwarehouse/getlwhoperationlist` |


### 接口说明

系统相关界面：【虚拟仓库存分配】

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
| io_id | number | 否 | 9801070 | 单据编号 |
| sku_id | string | 否 | 00000035098005 | 商品编码列表,多个逗号隔开，最多50个 |
| lwh_id | number | 否 | 818 | 虚拟仓编号 |
| date_type | number | 否 | 0 | 时间类型（0,1） 0:创建时间，1：审核时间 默认：创建时间 |
| date_begin | string | 否 | 2023-02-01 11:58:00 | 开始时间，开始时间,开始时间结束时间都不传默认查询3个月内 |
| date_end | string | 否 | 2023-02-01 11:59:00 | 结束时间，开始时间,开始时间结束时间都不传默认查询3个月内 |
| so_id | string | 否 | 20230201006 | 外部单号 |
| status | string | 否 | Creating | 状态：Creating：草拟，WaitConfirm：待审核，Confirmed：已生效 |
| type | string | 否 | 0 | 单据类型：虚拟仓分配，虚拟仓归还 |
| page | object | 是 |  | 分页 |
| page.page_size | integer | 是 | 50 | 每页最大条数， |
| page.current_page | integer | 是 | 1 | 当前页数 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.page | object | 否 |  |  |
| data.page.current_page | number | 否 |  | 当前页数 |
| data.page.page_size | number | 否 |  | 每页最多多少条 |
| data.page.count | number | 否 |  | 总条数 |
| data.page.pages | number | 否 |  | 总页数 |
| data.page.index | number | 否 |  | 索引下标 |
| data.list | array | 否 |  |  |
| data.list[] | object | 否 |  |  |
| data.list[].io_id | number | 是 |  | 单据号 |
| data.list[].lwh_id | number | 是 |  | 虚拟仓编号 |
| data.list[].lwh_name | string | 是 |  | 虚拟仓名称 |
| data.list[].status | string | 是 |  | 单据状态 |
| data.list[].labels | string | 是 |  | 标签 |
| data.list[].remark | string | 是 |  | 备注 |
| data.list[].wms_co_id | number | 是 |  | 仓储方编码 |
| data.list[].wms_name | string | 是 |  | 仓储方名称 |
| data.list[].created | string | 是 |  | 创建时间 |
| data.list[].io_date | string | 是 |  | 审核时间 |
| data.list[].items | array | 是 |  | 商品明细 |
| data.list[].items[] | object | 否 |  |  |
| data.list[].items[].i_id | string | 是 |  | 款式编码 |
| data.list[].items[].sku_id | string | 是 |  | 商品编码 |
| data.list[].items[].sku_name | string | 是 |  | 商品名称 |
| data.list[].items[].properties_value | string | 是 |  | 颜色规格 |
| data.list[].items[].qty | number | 是 |  | 库存数 |
| data.list[].items[].lock_qty | number | 是 |  | 虚拟仓可用数 |
| data.list[].items[].target_lwh_lockable_qty | number | 是 |  | 调入虚拟仓可用数 |
| data.list[].items[].pick_able_qty | number | 是 |  | 虚拟仓可配数 |
| data.list[].items[].public_qty | number | 是 |  | 公有可用数 |
| data.list[].items[].cost_price | number | 是 |  | 成本价 |
| data.list[].type | string | 是 |  | 单据类型：虚拟仓分配，虚拟仓归还 |
| data.list[].so_id | string | 是 |  | 外部单号 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 10015 | "msg": "分页参数错误" |  |


### 请求示例

```json
{
  "date_type": 0,
  "lwh_id": 818,
  "date_begin": "2023-02-01 11:58:00",
  "date_end": "2023-02-01 11:59:00",
  "page": {
    "current_page": 1,
    "page_size": 50
  },
  "type": "虚拟仓归还",
  "io_id": 9801070,
  "sku_id": "00000035098005",
  "status": "Creating",
  "so_id": "20230201006"
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": {
    "page": {
      "pages": 1,
      "count": 1,
      "index": 1,
      "current_page": 1,
      "page_size": 50
    },
    "list": [
      {
        "wms_name": "（本仓）",
        "wms_co_id": 12252,
        "lwh_id": 818,
        "created": "2023-02-01 11:58:00.217",
        "io_date": "2023-02-01 11:58:00.097",
        "lwh_name": "7698911",
        "remark": "去5",
        "type": "虚拟仓归还",
        "so_id": "20230201006",
        "items": [
          {
            "i_id": "0723",
            "lock_qty": 110,
            "properties_value": "虾红;2XL",
            "qty": 1,
            "public_qty": -110,
            "sku_name": "V领t恤",
            "target_lwh_lockable_qty": 0,
            "sku_id": "00000035098005",
            "pick_able_qty": 0,
            "cost_price": 0
          }
        ],
        "io_id": 9801070,
        "status": "草拟",
        "labels": ""
      }
    ]
  },
  "request_id": "2760827116753902967568024e5ab0"
}
```


### 异常示例

```json
{
  "msg": "分页参数错误",
  "code": 10015,
  "data": null,
  "request_id": "2760827116753904130093382e5ab3"
}
```


---

## 虚拟仓调拨单创建接口

`/open/webapi/itemapi/lockwarehouse/lwhallocationcreate`

| 项 | 内容 |
|---|---|
| 接口名称 | 虚拟仓调拨单创建接口 |
| 接口路径 | `/open/webapi/itemapi/lockwarehouse/lwhallocationcreate` |
| docType / docId | 43 / 342 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=43&docId=342 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/lockwarehouse/lwhallocationcreate` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/lockwarehouse/lwhallocationcreate` |


### 接口说明

系统相关界面：【虚拟仓库存分配】

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
| out_lwh_id | number | 是 | 818 | 调出虚拟仓 |
| examine | boolean | 否 | false | 是否审核生效 |
| in_lwh_id | number | 是 | 798 | 调入虚拟仓 |
| wms_co_id | number | 是 | 12252 | 实体仓编码 |
| so_id | string | 是 | 20230203003 | 外部单号,保持唯一 |
| remark | string | 是 | w3 | 备注 |
| items | array | 是 |  |  |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | 00000035098002 | 商品编码 |
| items[].qty | number | 否 | 1 |  |
| items[].sku_sns | array | 否 |  | 唯一码信息（如需传唯一码统一功能需要开启wms.buid.checkout） |
| items[].sku_sns[] | object | 否 |  |  |
| items[].sku_sns[].sku_id | string | 是 |  | 商品编码 |
| items[].sku_sns[].sku_sn | string | 是 |  | 唯一码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 接口请求是否成功，0表示成功 |
| data | object | 否 |  |  |
| data.io_id | integer | 否 |  | 单据编号 |
| data.msg | string | 否 |  |  |
| data.code | integer | 否 |  | 业务执行是否成功，0代表成功 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "out_lwh_id": 818,
  "in_lwh_id": 798,
  "wms_co_id": 12252,
  "so_id": "20230203003",
  "remark": "w3",
  "examine": false,
  "items": [
    {
      "sku_id": "00000035098002",
      "qty": 1
    }
  ]
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": {
    "msg": "操作成功",
    "code": 0,
    "io_id": 9804761
  },
  "request_id": "2760827116753922752787957e5aaa"
}
```


### 异常示例

```json
{
  "msg": "外部单号[20230203002]已存在，对应的单据编号为[9804759]",
  "code": 100,
  "data": null,
  "request_id": "2760827116753920241604509e5ab6"
}
```


---

## 虚拟仓分配/归还单据创建接口

`/open/webapi/itemapi/lockwarehouse/lwhoperationcreate`

| 项 | 内容 |
|---|---|
| 接口名称 | 虚拟仓分配/归还单据创建接口 |
| 接口路径 | `/open/webapi/itemapi/lockwarehouse/lwhoperationcreate` |
| docType / docId | 43 / 343 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=43&docId=343 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/lockwarehouse/lwhoperationcreate` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/lockwarehouse/lwhoperationcreate` |


### 接口说明

系统相关界面：【虚拟仓库存分配】

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
| lwh_id | number | 是 | 818 | 虚拟仓编码 |
| examine | boolean | 否 | false | 是否审核生效 默认false |
| wms_co_id | number | 是 | 12252 | 仓储编码 若使用虚拟仓分仓则必填 |
| so_id | string | 是 | 20230203003 | 外部单号 唯一 |
| type | string | 是 | 虚拟仓归还 | 类型 虚拟仓分配 虚拟仓归还 |
| items | array | 是 |  |  |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | 00000035098005 | 商品编码 |
| items[].qty | number | 否 | 1 | 不填 或者0 则取可用数 |
| isIgnore_check_stock  | boolean | 否 |  | 是否超锁，examine = true 的时候这个入参才有效（true：允许超锁，false：不允许超锁）不传为默认值 false |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.io_id | integer | 否 |  | 单据编号 |
| data.msg | string | 否 |  |  |
| data.code | integer | 否 |  | 0代表成功 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "lwh_id": 818,
  "wms_co_id": 12252,
  "so_id": "20230203003",
  "type": "虚拟仓归还",
  "remark": "归033",
  "examine": false,
  "items": [
    {
      "sku_id": "00000035098005",
      "qty": 1
    }
  ]
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": {
    "msg": "操作成功",
    "code": 0,
    "io_id": 9804744
  },
  "request_id": "2760827116753908711721000e5ab5"
}
```


### 异常示例

```json
{
  "msg": "外部单号[20230203003]已存在，对应的单据编号为[9804744]",
  "code": 100,
  "data": null,
  "request_id": "2760827116753910133951473e5ab4"
}
```


---

## 获取虚拟仓列表

`/open/webapi/itemapi/lockwarehouse/getwarehouselist`

| 项 | 内容 |
|---|---|
| 接口名称 | 获取虚拟仓列表 |
| 接口路径 | `/open/webapi/itemapi/lockwarehouse/getwarehouselist` |
| docType / docId | 43 / 490 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=43&docId=490 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/lockwarehouse/getwarehouselist` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/lockwarehouse/getwarehouselist` |


### 接口说明

对应ERP菜单-【运营云仓管理】

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
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | array | 是 |  |  |
| data[] | object | 否 |  |  |
| data[].lwh_id | integer | 是 |  | 虚拟仓编号 |
| data[].name | string | 是 |  | 虚拟仓名称 |
| data[].mnemonic | string | 否 |  | 类首字全拼 |
| data[].flag | string | 否 |  | 首字分类 |
| data[].bind_wms | array | 否 |  | 绑定的分仓信息 |
| data[].bind_wms[] | object | 否 |  |  |
| data[].bind_wms[].wms_co_id | number | 否 |  | 分仓编码 |
| data[].bind_wms[].wms_name | string | 否 |  | 分仓名称 |

### 请求示例

```json
null
```


### 响应示例

```json
{
  "code": 0,
  "data": [
    {
      "lwh_id": 2643,
      "name": "主仓88",
      "mnemonic": "zc88",
      "flag": "#",
      "bind_wms": [
        {
          "wms_co_id": 12501774,
          "wms_name": "3分仓"
        }
      ]
    }
  ],
  "msg": null,
  "request_id": null
}
```


### 异常示例

_无_


---

## 虚拟仓商品库存查询

`/open/webapi/itemapi/iteminventory/getvirtualstock`

| 项 | 内容 |
|---|---|
| 接口名称 | 虚拟仓商品库存查询 |
| 接口路径 | `/open/webapi/itemapi/iteminventory/getvirtualstock` |
| docType / docId | 43 / 625 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=43&docId=625 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/iteminventory/getvirtualstock` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/iteminventory/getvirtualstock` |


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
| wms_co_id | string | 否 |  | 分仓编码 |
| sku_ids | array | 否 |  | 商品编码；与修改时间查询条件不能同时为空 |
| sku_ids[] | string | 否 | #001 |  |
| modified_begin | string | 否 |  | 修改起始时间；与商品编码查询条件不能同时为空 |
| modified_end | string | 否 |  | 修改结束时间；与商品编码查询条件不能同时为空 |
| page | object | 是 |  |  |
| page.current_page | string | 是 | 1 | 当前页 |
| page.page_size | string | 是 | 500 | 页大小 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| page_index | number | 是 |  |  |
| page_size | number | 是 |  |  |
| data_count | number | 是 |  |  |
| has_next | boolean | 是 |  |  |
| data | array | 是 |  |  |
| data[] | object | 否 |  |  |
| data[].sku_id | string | 是 |  | 商品编码 |
| data[].stocks | array | 是 |  |  |
| data[].stocks[] | object | 否 |  |  |
| data[].stocks[].lwh_id | number | 是 |  | 虚拟仓编号 |
| data[].stocks[].name | string | 是 |  | 虚拟仓名称 |
| data[].stocks[].qty | number | 是 |  | 库存数 |
| data[].stocks[].order_able_qty | number | 是 |  | 可用数（库存数-订单占有）不含虚拟库存数 |
| data[].stocks[].order_lock | number | 是 |  | 订单占有数 |
| data[].stocks[].pick_lock | number | 是 |  | 仓库待发数 |
| data[].stocks[].modified | string | 是 |  | 最后修改时间 |

### 请求示例

```json
{
  "wms_co_id": "",
  "sku_ids": [],
  "modified_begin": "",
  "modified_end": "",
  "page": {
    "current_page": "1",
    "page_size": "500"
  }
}
```


### 响应示例

```json
{
  "data": [
    {
      "sku_id": "",
      "stocks": [
        {
          "pick_lock": 0,
          "lwh_id": 0,
          "qty": 0,
          "name": "",
          "modified": "",
          "order_able_qty": 0,
          "order_lock": 0
        }
      ]
    }
  ],
  "page_index": 0,
  "has_next": true,
  "data_count": 0,
  "page_size": 0
}
```


### 异常示例

_无_


---

## 创建/更新虚拟仓采购申请

`/open/webapi/itemapi/lockwarehouse/lockpurchase/createorupdatepurchase`

| 项 | 内容 |
|---|---|
| 接口名称 | 创建/更新虚拟仓采购申请 |
| 接口路径 | `/open/webapi/itemapi/lockwarehouse/lockpurchase/createorupdatepurchase` |
| docType / docId | 43 / 799 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=43&docId=799 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/lockwarehouse/lockpurchase/createorupdatepurchase` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/lockwarehouse/lockpurchase/createorupdatepurchase` |


### 接口说明

系统相关界面： 商品库存（运营云仓）-采购申请

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
| lp_id | string | 否 | 15676 | 虚拟仓采购申请单的id（如果要更新该字段必填） |
| lwh_id | string | 是 | 1226 | 虚拟仓编码 |
| wms_co_id | string | 是 | 10183791 | 分仓编码 |
| remarks | string | 否 |  | 备注 |
| items | array | 是 |  | 商品明细 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | LG001 | 商品编码 |
| items[].qty | string | 是 | 5 | 商品数量 |
| items[].remark | string | 否 |  | 明细备注 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | object | 是 |  |  |
| data.lp_id | string | 是 |  | 采购申请单id |
| data.is_success | boolean | 是 |  | 是否执行成功 |
| data.msg | string | 是 |  | 返回信息 |

### 请求示例

```json
{
  "lp_id": "15676",
  "wms_co_id": "10183791",
  "lwh_id": "1226",
  "items": [
    {
      "qty": "5",
      "sku_id": "LG001"
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
    "lp_id": "",
    "msg": "",
    "is_success": true
  }
}
```


### 异常示例

_无_


---

## 查询采购申请（包含虚拟仓和非虚拟仓）

`/open/webapi/itemapi/lockwarehouse/lockpurchase/getpagelockpurchases`

| 项 | 内容 |
|---|---|
| 接口名称 | 查询采购申请（包含虚拟仓和非虚拟仓） |
| 接口路径 | `/open/webapi/itemapi/lockwarehouse/lockpurchase/getpagelockpurchases` |
| docType / docId | 43 / 802 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=43&docId=802 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/lockwarehouse/lockpurchase/getpagelockpurchases` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/lockwarehouse/lockpurchase/getpagelockpurchases` |


### 接口说明

系统相关界面：
 1.商品库存（运营云仓）-库存操作 采购申请
 2.采购申请（新）

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
| auto_id | integer | 否 |  | 采购申请号 |
| lwh_id | integer | 否 |  | 虚拟仓编码（传null查询无运营云仓采购申请） |
| wms_co_id | integer | 否 |  | 分仓号 |
| status | string | 否 |  | 状态 |
| remark | string | 否 |  | 备注 |
| create_time_begin | string | 否 |  | 创建时间起始 |
| create_time_end | string | 否 |  | 创建时间结束 |
| modified_begin | string | 否 |  | 更新时间起始 |
| modified_end | string | 否 |  | 更新时间结束 |
| page | object | 是 |  |  |
| page.current_page | integer | 是 | 1 | 当前页 |
| page.page_size | integer | 是 | 25 | 每页多少条 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | array | 是 |  |  |
| data[] | object | 否 |  |  |
| data[].lock_purchase | object | 是 |  | 采购申请信息 |
| data[].lock_purchase.lp_id | number | 是 |  | 采购申请号 |
| data[].lock_purchase.type | string | 是 |  | 单据类型（lock 是虚拟仓，po 是实物仓 ） |
| data[].lock_purchase.lwh_id | string | 是 |  | 虚拟仓编码 |
| data[].lock_purchase.lwh_name | string | 是 |  | 虚拟仓名称 |
| data[].lock_purchase.wms_co_id | number | 是 |  | 仓储编码 |
| data[].lock_purchase.status | string | 是 |  | 状态 |
| data[].lock_purchase.remark | string | 是 |  | 备注 |
| data[].lock_purchase.creator_name | string | 是 |  | 创建人 |
| data[].lock_purchase.modified | string | 是 |  | 修改时间 |
| data[].lock_purchase.modifier_name | string | 是 |  | 修改人 |
| data[].lock_purchase.confirmed | string | 是 |  | 确认时间 |
| data[].lock_purchase.confirmer_name | string | 是 |  | 确认人 |
| data[].lock_purchase_items | array | 是 |  | 采购申请明细信息 |
| data[].lock_purchase_items[] | object | 否 |  |  |
| data[].lock_purchase_items[].lp_id | number | 是 |  | 采购申请号 |
| data[].lock_purchase_items[].sku_id | string | 是 |  | 商品编码 |
| data[].lock_purchase_items[].name | string | 是 |  | 商品名称 |
| data[].lock_purchase_items[].i_id | string | 是 |  | 款式编码 |
| data[].lock_purchase_items[].qty | number | 是 |  | 商品数量 |
| data[].lock_purchase_items[].supplier_name | string | 是 |  | 供应商名称 |
| data[].lock_purchase_items[].remark | string | 是 |  | 明细备注 |
| data[].lock_purchase_items[].status | string | 是 |  | 状态key值 |
| data[].lock_purchase_items[].status_c_n | string | 是 |  | 状态中文值 |
| data[].lock_purchase_items[].po_id | number | 是 |  | 采购单号 |
| data[].lock_purchase_items[].auto_id | string | 是 |  | 采购申请明细id |

### 请求示例

```json
{
  "create_time_begin": "2024-01-01",
  "create_time_end": "2024-02-01",
  "page": {
    "current_page": 1,
    "page_size": 1
  }
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": [
    {
      "lock_purchase": {
        "lp_id": 160,
        "modifier_name": "***",
        "confirmer_name": "***",
        "wms_co_id": 0,
        "lwh_id": 73,
        "created": "2024-01-08 14:53:44.607",
        "lwh_name": "仓",
        "modified": "2024-01-08 14:54:23.613",
        "creator_name": "***",
        "remark": null,
        "confirmed": "2024-01-08 14:54:23.613",
        "status": "Confirmed"
      },
      "lock_purchase_items": [
        {
          "i_id": "WY505-3",
          "lp_id": 160,
          "po_id": 132740,
          "qty": 100,
          "status_c_n": "已下单",
          "name": "************",
          "r_qty": 0,
          "remark": null,
          "sku_id": "WY505-3F10yg",
          "order_qty": 0,
          "supplier_name": "**********",
          "status": "Confirmed"
        },
        {
          "i_id": "WY505-3",
          "lp_id": 160,
          "po_id": 132740,
          "qty": 1300,
          "status_c_n": "已下单",
          "name": "***********",
          "r_qty": 0,
          "remark": null,
          "sku_id": "WY505-3FD10c",
          "order_qty": 0,
          "supplier_name": "有限公司",
          "status": "Confirmed"
        },
        {
          "i_id": "WY505-3",
          "lp_id": 160,
          "po_id": 132740,
          "qty": 700,
          "status_c_n": "已下单",
          "name": "*************",
          "r_qty": 0,
          "remark": null,
          "sku_id": "WY505-3FD10y",
          "order_qty": 0,
          "supplier_name": "*********",
          "status": "Confirmed"
        },
        {
          "i_id": "WY505-3",
          "lp_id": 160,
          "po_id": 132740,
          "qty": 100,
          "status_c_n": "已下单",
          "name": "*************",
          "r_qty": 0,
          "remark": null,
          "sku_id": "WY505-3L10yg",
          "order_qty": 0,
          "supplier_name": "玩具有限公司",
          "status": "Confirmed"
        },
        {
          "i_id": "WY505-3",
          "lp_id": 160,
          "po_id": 132740,
          "qty": 1100,
          "status_c_n": "已下单",
          "name": "***********",
          "r_qty": 0,
          "remark": null,
          "sku_id": "WY505-3LD10c",
          "order_qty": 0,
          "supplier_name": "汕头*****公司",
          "status": "Confirmed"
        },
        {
          "i_id": "WY505-3",
          "lp_id": 160,
          "po_id": 132740,
          "qty": 700,
          "status_c_n": "已下单",
          "name": "****",
          "r_qty": 0,
          "remark": null,
          "sku_id": "WY505-3LD10y",
          "order_qty": 0,
          "supplier_name": "公司",
          "status": "Confirmed"
        }
      ]
    }
  ],
  "page": {
    "pages": 60,
    "count": 60,
    "index": 0,
    "current_page": 1,
    "page_size": 1
  },
  "request_id": null
}
```


### 异常示例

_无_


---

## 获取运营云仓出入库台账

`/open/webapi/itemapi/lockwarehouse/getlwhinout`

| 项 | 内容 |
|---|---|
| 接口名称 | 获取运营云仓出入库台账 |
| 接口路径 | `/open/webapi/itemapi/lockwarehouse/getlwhinout` |
| docType / docId | 43 / 1648 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=43&docId=1648 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/lockwarehouse/getlwhinout` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/lockwarehouse/getlwhinout` |


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
| page | object | 是 |  |  |
| page.page_size | number | 是 | 50 |  |
| page.current_page | number | 是 | 1 |  |
| lwh_ids | array | 否 |  | 运营云仓编号 |
| lwh_ids[] | string | 否 |  |  |
| sku_ids | array | 否 |  | 商品编码 |
| sku_ids[] | string | 否 |  |  |
| io_ids | array | 否 |  | 单据编号 |
| io_ids[] | string | 否 |  |  |
| o_ids | array | 否 |  | 采购单号/内部订单号 |
| o_ids[] | string | 否 |  |  |
| types | array | 否 |  | 单据类型 |
| types[] | string | 否 |  | "销售出仓", "采购进仓", "其它进仓", "采购退货", "其它退货", "虚拟仓分配", "虚拟仓归还", "其它出库", "虚拟仓采购分配", "虚拟仓采购退货", "销售退货", "加工出仓", "加工进仓", "虚拟仓解锁", "虚拟仓调入", "虚拟仓调出", "调拨出", "调拨入", "虚拟仓盘点", "盘点", "虚拟仓自动分配" |
| wms_co_ids | array | 否 |  | 分仓号 |
| wms_co_ids[] | string | 否 |  |  |
| io_date_begin | string | 否 | @datetime | 单据生效开始时间 |
| io_date_end | string | 否 | @datetime | 单据生效结束时间 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.list | array | 否 |  |  |
| data.list[] | object | 否 |  |  |
| data.list[].io_id | number | 是 |  | 出入库单号 |
| data.list[].o_id | number | 是 |  | 内部订单号 |
| data.list[].type | string | 是 |  | 单据类型 |
| data.list[].lwh_name | string | 是 |  | 虚拟仓名称 |
| data.list[].name | string | 是 |  | 商品名称 |
| data.list[].i_id | string | 是 |  | 款式编码 |
| data.list[].sku_id | string | 是 |  | 商品编码 |
| data.list[].qty | number | 是 |  | 数量 |
| data.list[].lock_cost_price | null | 是 |  | 虚拟仓成本价 |
| data.list[].lock_settlement_amount | null | 是 |  | 虚拟仓金额 |
| data.list[].io_date | string | 是 |  | 单据时间 |
| data.list[].remark | string | 是 |  | 备注 |
| data.list[].ioi_id | number | 是 |  | 单据明细号 |
| data.list[].co_id | number | 是 |  | 公司号 |
| data.list[].wms_co_id | number | 是 |  | 分仓公司号 |
| data.list[].lwh_id | number | 是 |  | 运营云仓编号 |
| data.list[].wms_co_name | string | 是 |  | 分仓公司名称 |
| data.list[].link_o_id | string | 是 |  | 关联订单号 |
| data.list[].map_lwh_id | string | 是 |  | 运营云仓自动分配时关联运营云仓名称 |
| data.page | object | 否 |  |  |
| data.page.current_page | number | 否 |  |  |
| data.page.page_size | number | 否 |  |  |
| data.page.count | number | 否 |  |  |
| data.page.pages | number | 否 |  |  |
| data.page.index | number | 否 |  |  |
| msg | null | 否 |  |  |
| request_id | string | 否 |  |  |

### 请求示例

```json
{
  "o_ids": [],
  "wms_co_ids": [],
  "types": [],
  "sku_ids": [],
  "io_date_end": "@datetime",
  "io_ids": [],
  "page": {
    "current_page": 1,
    "page_size": 50
  },
  "lwh_ids": [],
  "io_date_begin": "@datetime"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "page": {
      "pages": 0,
      "count": 0,
      "index": 0,
      "current_page": 0,
      "page_size": 0
    },
    "list": [
      {
        "i_id": "",
        "lock_cost_price": "",
        "io_date": "",
        "lwh_name": "",
        "co_id": 0,
        "sku_id": "",
        "remark": "",
        "type": "",
        "ioi_id": 0,
        "io_id": 0,
        "map_lwh_id": "",
        "wms_co_id": 0,
        "lwh_id": 0,
        "qty": 0,
        "o_id": 0,
        "name": "",
        "link_o_id": "",
        "lock_settlement_amount": "",
        "wms_co_name": ""
      }
    ]
  },
  "request_id": ""
}
```


### 异常示例

_无_


---
