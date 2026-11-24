# 聚水潭开放平台 · 调拨API（线下版）

> 抓取日期：2026-11-23  
> 分类：调拨API（docType=12）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=12&docId=47

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 调拨单查询 | `/open/allocate/query` | 47 | [打开](https://openweb.jushuitan.com/dev-doc?docType=12&docId=47) |
| 库存调拨上传（跨仓调拨） | `/open/allocate/kc/upload` | 48 | [打开](https://openweb.jushuitan.com/dev-doc?docType=12&docId=48) |
| 库存调拨上传（仓内调拨） | `/open/jushuitan/allocate/in/upload` | 49 | [打开](https://openweb.jushuitan.com/dev-doc?docType=12&docId=49) |
| 调拨单确认 | `/open/jushuitan/allocate/confirm` | 64 | [打开](https://openweb.jushuitan.com/dev-doc?docType=12&docId=64) |
| 调拨单取消 | `/open/jushuitan/allocate/cancel/v2` | 266 | [打开](https://openweb.jushuitan.com/dev-doc?docType=12&docId=266) |
| 创建调拨差异单 | `/open/jushuitan/diffallocate/create` | 357 | [打开](https://openweb.jushuitan.com/dev-doc?docType=12&docId=357) |

## 目录

- [调拨单查询](#调拨单查询)
- [库存调拨上传（跨仓调拨）](#库存调拨上传跨仓调拨)
- [库存调拨上传（仓内调拨）](#库存调拨上传仓内调拨)
- [调拨单确认](#调拨单确认)
- [调拨单取消](#调拨单取消)
- [创建调拨差异单](#创建调拨差异单)

---

## 调拨单查询

`/open/allocate/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 调拨单查询 |
| 接口路径 | `/open/allocate/query` |
| docType / docId | 12 / 47 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=12&docId=47 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/allocate/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/allocate/query` |


### 接口说明

系统相关界面：【库存】------【库存调拨】
 当erp页面中调拨出单据状态为调拨中（Confirmed）并且调拨入单据状态为待收货（WaitConfirm）则erp页面状态显示调拨中
 当erp页面中调拨出单据状态为完成（Confirmed）并且调拨入单据状态为完成（Confirmed）则erp页面状态显示完成

 更多调拨API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=24&currentPage=1&pageSize=20

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
| modified_begin | string | 否 |  | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空 |
| modified_end | string | 否 |  | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空 |
| so_ids | array | 否 |  | 指定线上订单号，和时间段不能同时为空 |
| so_ids[] | string | 否 |  |  |
| page_index | integer | 否 | 1 | 第几页，从第一页开始，默认1 |
| page_size | integer | 否 | 30 | 每页多少条，默认30，最大50 |
| io_ids | array | 否 |  | 调拨单号 |
| io_ids[] | string | 否 |  |  |
| type | string | 否 |  | 调拨类型（调拨出，调拨入） |
| date_type  | number | 否 |  | 0:修改时间，modified。 2:出入库时间 io_date，未传入时默认为0 |
| owner_co_id | integer | 否 |  | 货主编码（三方仓商家不传货主默认查自身数据，若查所有货主需传值：2147483647） |

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
| data.datas[].wms_co_id | integer | 否 | 1 | 分仓编号，调拨出为发起方，调拨入为接收方 |
| data.datas[].co_id | integer | 否 |  | 公司编号 |
| data.datas[].io_id | integer | 否 | 3417323 | 调拨单号 |
| data.datas[].io_date | string | 否 | 2021-11-1015:51:25 | 单据日期 |
| data.datas[].modified | string | 否 | 2021-11-18 15:53:03 | 修改时间 |
| data.datas[].status | string | 否 | Cancelled | Creating：待确认，Confirmed：调拨中，完成（若remark包含”红冲单据“则ERP显示红冲状态），Picking：拣货中，OuterConfirming：外部确认中，Cancelled：取消,Confirming:确认;WaitConfirm待收货 |
| data.datas[].warehouse | string | 否 | 主仓血t橙est2ly3aer | 如果单据类型调拨出，表示调拨出仓库名称；如果单据调拨入，表示调拨入仓库名称（对应ERP仓库资料设定页面） |
| data.datas[].link_warehouse | string | 否 | 戴胜分仓主仓 | 如果单据类型调拨出，表示调拨入仓库名称；如果单据调拨入，表示调拨出仓库名称（对应ERP仓库资料设定页面） |
| data.datas[].f_status | string | 否 |  | 财务状态Archive:归档,modifing:变更,WaitConfirm:待审核,Confirmed:已审核,Cancelled:取消,Delete:作废 |
| data.datas[].type | string | 否 | 调拨出 | 调拨类型 |
| data.datas[].wh_id | integer | 否 | 1 | 调拨出仓库编号；主仓=1，销退仓=2，进货仓=3，次品仓=4 |
| data.datas[].link_wh_id | integer | 否 | 1 | 调拨入仓库编号；主仓=1，销退仓=2，进货仓=3，次品仓=4 |
| data.datas[].link_wms_co_id | integer | 否 | 10048367 | 调拨入分仓编号，调拨出为接收方，调拨入为发起方 |
| data.datas[].link_io_id | integer | 否 |  | 调拨入关联单号 |
| data.datas[].so_id | string | 否 |  | 调拨建议号，跨仓调拨入单据才有值，数据来源是跨仓调拨上传的so_id |
| data.datas[].wave_id | number | 否 |  | 拣货批次号 |
| data.datas[].remark | string | 否 |  | 备注 |
| data.datas[].creator_name | string | 否 | juanbai | 创建人 |
| data.datas[].lock_wh_id | string | 否 |  | 调出虚拟仓编码 |
| data.datas[].lock_link_wh_id | string | 否 |  | 调入虚拟仓编码 |
| data.datas[].out_io_id | string | 否 |  | 外部单号 |
| data.datas[].labels | array | 否 |  | 标记｜多标签 |
| data.datas[].labels[] | string | 否 |  |  |
| data.datas[].items | array | 否 |  | 商品集合 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].io_id | integer | 否 | 3417323 | 调拨单号 |
| data.datas[].items[].ioi_id | integer | 否 | 8514866 | 子单号 |
| data.datas[].items[].sku_id | string | 否 | #0000006-2 | 商品编码 |
| data.datas[].items[].i_id | string | 否 |  | 款式编码 |
| data.datas[].items[].qty | integer | 否 | 0 | 数量 |
| data.datas[].items[].cost_price | number | 否 |  | 单价 |
| data.datas[].items[].cost_amount | number | 否 |  | 金额 |
| data.datas[].items[].name | string | 否 | haha123 | 商品名称 |
| data.datas[].items[].properties_value | string | 否 | 我是单品颜色规格 | 颜色及规格 |
| data.datas[].items[].r_qty | integer | 否 | 0 | 点数 |
| data.datas[].items[].batch_id | string | 否 |  | 批次号，需开启相关业务配置 |
| data.datas[].items[].product_date | string | 否 |  | 批次日期，需开启相关业务配置 |
| data.datas[].items[].supplier_id | integer | 否 |  | 供应商编号，需开启相关业务配置 |
| data.datas[].items[].expiration_date | string | 否 |  | 有效期至，需开启相关业务配置 |
| data.datas[].items[].unit | string | 否 |  | 单位 |
| data.datas[].batchs | array | 否 |  | 批次集合，获取该节点系统中相关业务项需配置（对应erp基础设置开启生产批次管理 如果是分仓数据 分仓也需要开启） |
| data.datas[].batchs[] | object | 否 |  |  |
| data.datas[].batchs[].batch_no | string | 否 |  | 批次号 |
| data.datas[].batchs[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].batchs[].qty | integer | 否 |  | 数量 |
| data.datas[].batchs[].product_date | string | 否 |  | 批次日期 |
| data.datas[].batchs[].supplier_id | integer | 否 |  | 供应商编号 |
| data.datas[].batchs[].supplier_name | string | 否 |  | 供应商名称 |
| data.datas[].batchs[].ioi_id | string | 是 |  | 子单号；需开启基础设置：单据明细批次透出 和 进出仓单据跟踪生产批次 |
| data.datas[].sns | array | 否 |  |  |
| data.datas[].sns[] | object | 否 |  |  |
| data.datas[].sns[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].sns[].sn | string | 否 |  | 唯一码 |
| data.datas[].receiver_name_en | string | 否 |  | 收货人 |
| data.datas[].receiver_mobile_en | string | 否 |  | 移动电话 |
| data.datas[].receiver_state | string | 否 |  | 省 |
| data.datas[].receiver_city | string | 否 |  | 市 |
| data.datas[].receiver_district | string | 否 |  | 区 |
| data.datas[].receiver_address | string | 否 |  | 详细地址 |
| data.datas[].l_id | string | 否 |  | 物流单号 |
| data.datas[].lc_id | string | 否 |  | 物流公司编码 |
| data.datas[].logistics_company | string | 否 |  | 物流公司名称 |

### 请求示例

```json
{
  "so_ids": [],
  "page_index": 1,
  "modified_begin": "",
  "modified_end": "",
  "io_ids": [],
  "page_size": 30
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
        "lc_id": "",
        "receiver_city": "",
        "remark": "",
        "type": "调拨出",
        "receiver_state": "",
        "link_warehouse": "戴胜分仓主仓",
        "so_id": "",
        "wave_id": 0,
        "modified": "2021-11-18 15:53:03",
        "f_status": "",
        "receiver_mobile_en": "",
        "out_io_id": "",
        "lock_wh_id": "",
        "receiver_name_en": "",
        "io_date": "2021-11-1015:51:25",
        "link_wh_id": 1,
        "receiver_district": "",
        "co_id": 0,
        "warehouse": "主仓血t橙est2ly3aer",
        "link_io_id": 0,
        "io_id": 3417323,
        "labels": [],
        "lock_link_wh_id": "",
        "batchs": [
          {
            "batch_no": "",
            "qty": 0,
            "sku_id": "",
            "supplier_name": "",
            "supplier_id": 0,
            "ioi_id": "",
            "product_date": ""
          }
        ],
        "wms_co_id": 1,
        "wh_id": 1,
        "sns": [
          {
            "sku_id": "",
            "sn": ""
          }
        ],
        "receiver_address": "",
        "creator_name": "juanbai",
        "logistics_company": "",
        "link_wms_co_id": 10048367,
        "l_id": "",
        "items": [
          {
            "i_id": "",
            "batch_id": "",
            "sku_id": "#0000006-2",
            "expiration_date": "",
            "ioi_id": 8514866,
            "io_id": 3417323,
            "product_date": "",
            "unit": "",
            "cost_amount": 0,
            "properties_value": "我是单品颜色规格",
            "qty": 0,
            "name": "haha123",
            "r_qty": 0,
            "supplier_id": 0,
            "cost_price": 0
          }
        ],
        "status": "Cancelled"
      }
    ],
    "page_index": 1,
    "has_next": false,
    "data_count": 2,
    "page_count": 1,
    "page_size": 30
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

## 库存调拨上传（跨仓调拨）

`/open/allocate/kc/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 库存调拨上传（跨仓调拨） |
| 接口路径 | `/open/allocate/kc/upload` |
| docType / docId | 12 / 48 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=12&docId=48 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/allocate/kc/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/allocate/kc/upload` |


### 接口说明

创建跨仓调拨单
 比如从主仓的销退仓调拨到分仓的次品仓

 关于 is_confirming 和 is_confirm 说明：
 is_confirming： 审核/取消审核 （ 开了功能 非销售出库单据占有库存 才有用 ）
 is_confirm： 确认出库(调拨完成)

 默认 状态流转：
 创建【 待确认 】→确认出库(调拨完成)【调拨中】→确认入库【完成】

 开了功能 状态流转：
 创建【 待审核 】→审核【 已确认 】→确认出库(调拨完成)【调拨中】→确认入库【完成】

 更多调拨API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=24&currentPage=1&pageSize=20

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
| data | object | 是 |  |  |
| data.datas | array | 是 |  |  |
| data.datas[] | object | 否 |  |  |
| data.datas[].so_id | string | 是 | A4912019052300000351 | 线上订单号 |
| data.datas[].io_id | string | 是 | 11 | 调拨出单号 |
| data.datas[].allocateIn_io_id | string | 否 |  | 如is_confirm传true返回调拨入单号 |

### 请求示例

```json
[
  {
    "lc_id": "",
    "lock_wh_id": 0,
    "link_co_id": 0,
    "io_date": "",
    "receiver_city": "",
    "go_co_id": 0,
    "receiver_district": "",
    "is_confirming": true,
    "remark": "测试",
    "warehouse": 0,
    "receiver_mobile": "",
    "labels": [],
    "receiver_state": "",
    "link_warehouse": 0,
    "so_id": "21120211072883513540",
    "price": 0,
    "is_confirm": true,
    "receiver_name": "",
    "receiver_address": "",
    "l_id": "",
    "items": [
      {
        "batch_id": "",
        "sku_sns": [],
        "qty": 2,
        "sku_id": "sn2",
        "remark": "",
        "expiration_date": "",
        "produced_date": "",
        "cost_price": 0
      }
    ],
    "link_lock_wh_id": 0
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
        "so_id": "A4912019052300000351",
        "io_id": "11"
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

## 库存调拨上传（仓内调拨）

`/open/jushuitan/allocate/in/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 库存调拨上传（仓内调拨） |
| 接口路径 | `/open/jushuitan/allocate/in/upload` |
| docType / docId | 12 / 49 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=12&docId=49 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/allocate/in/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/allocate/in/upload` |


### 接口说明

系统相关界面：【库存】------【库存调拨】
 该接口支持一个公司账号内的仓内调拨，支持主仓和分仓的仓内调拨。

 更多调拨API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=24&currentPage=1&pageSize=20

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
| io_date | string | 是 | 2021-07-2815:30:00 | 调拨时间 |
| link_warehouse | integer | 是 | 2 | 调入仓 1是主仓，2是销退仓，3是进货仓，4是次品仓，自定义1仓=6，自定义2仓=7，自定义3仓=8，自定义4仓=9，自定义5仓=10，自定义6仓=11，自定义7仓=12，自定义8仓=13，自定义9仓=14，自定义10仓=15（对应ERP仓库资料设定页面） |
| remark | string | 是 | test | 备注 |
| so_id | string | 是 | 2021072900116134555036959 | 外部调拨单号，最长不超过50;唯一（单据上传成功之后对应页面线上订单号） |
| warehouse | integer | 是 | 1 | 调出仓公司内仓库id：1是主仓，2是销退仓，3是进货仓，4是次品仓，自定义1仓=6，自定义2仓=7，自定义3仓=8，自定义4仓=9，自定义5仓=10，自定义6仓=11，自定义7仓=12，自定义8仓=13，自定义9仓=14，自定义10仓=15（对应ERP仓库资料设定页面） |
| wms_co_id | integer | 否 | 12252 | 分仓编号（对应ERP需要第三方物流或分仓页面,编码查询：https://openweb.jushuitan.com/dev-doc?docType=1&docId=3） |
| l_id | string | 否 |  | 物流单号 |
| lc_id | string | 否 |  | 物流公司编码 |
| items | array | 是 |  | 商品集合 |
| items[] | object | 否 |  |  |
| items[].qty | integer | 是 | 5 | 商品数量 |
| items[].sku_id | string | 是 | XJT1 | 商品编码 |
| items[].batch_id | string | 否 |  | 批次号 |
| items[].produced_date | string | 否 |  | 生产日期 |
| items[].expiration_date | string | 否 |  | 有效期 |
| items[].remark | string | 否 |  | 备注 |
| items[].sku_sns | array | 否 |  | 唯一码集合（开启唯一码及商品开启唯一码）is_confirm = true有效，记录唯一码流水 |
| items[].sku_sns[] | string | 否 |  |  |
| items[].cost_print | number | 否 |  | 成本价（1、小数限制4位，超出4舍5入处理 2、数值传空时，默认取商品资料成本价 3、最长位数，同库存调拨单成本价的限制） |
| labels | array | 否 |  | 标记｜多标签 |
| labels[] | string | 否 |  |  |
| is_confirm | boolean | 否 |  | 是否自动确认单据 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  | 数据集合 |
| data.data | object | 否 |  |  |
| data.data.io_id | integer | 否 | 1178744 | 调拨单号 |
| data.data.so_id | string | 否 | 2021072900116134555036959 | 外部调拨单号 |

### 请求示例

```json
{
  "wms_co_id": 12252,
  "link_warehouse": 2,
  "io_date": "2021-07-28 15:30:00",
  "so_id": "2021072900116134555036959",
  "remark": "test",
  "warehouse": 1,
  "labels": [
    "1",
    "2"
  ],
  "is_confirm": false,
  "items": [
    {
      "batch_id": "",
      "qty": 5,
      "sku_id": "XJT1",
      "expiration_date": "",
      "produced_date": ""
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
    "data": {
      "so_id": "2021072900116134555036959",
      "io_id": 1178744
    }
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

## 调拨单确认

`/open/jushuitan/allocate/confirm`

| 项 | 内容 |
|---|---|
| 接口名称 | 调拨单确认 |
| 接口路径 | `/open/jushuitan/allocate/confirm` |
| docType / docId | 12 / 64 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=12&docId=64 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/allocate/confirm` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/allocate/confirm` |


### 接口说明

ERP界面【库存调拨】
 仅支持待审核单据确认

 当主仓确认分仓单时，wms_co_id分仓编号必填

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
| io_id | integer | 是 |  | 调拨单号 |
| wms_co_id | integer | 否 |  | 分仓id（当单据为分仓调拨单时仓库编码必填） |
| remark | string | 否 |  | 备注 |
| is_force | boolean | 否 |  | 是否强制调拨 |
| items | array | 否 |  | 商品集合（只针对调拨出类型传商品明细有效果，调拨入是整单确认的） |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 否 |  | 商品编码 |
| items[].qty | integer | 否 |  | 商品数量 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 |  | 返回错误码；0代表成功 |
| issuccess | boolean | 否 |  | 是否成功 |
| msg | string | 否 |  | 提示信息 |

### 请求示例

```json
{
  "wms_co_id": 0,
  "is_force": true,
  "remark": "",
  "items": [
    {
      "qty": 0,
      "sku_id": ""
    }
  ],
  "io_id": 0
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
  "msg": "XXX",
  "issuccess": false
}
```


---

## 调拨单取消

`/open/jushuitan/allocate/cancel/v2`

| 项 | 内容 |
|---|---|
| 接口名称 | 调拨单取消 |
| 接口路径 | `/open/jushuitan/allocate/cancel/v2` |
| docType / docId | 12 / 266 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=12&docId=266 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/allocate/cancel/v2` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/allocate/cancel/v2` |


### 接口说明

注意：仅支持作废本仓单据 不支持作废推送到三方仓的其它出入库单据

 请谨慎操作！

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
| io_id | number | 是 |  | 调拨出库单号 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 返回码；0表示成功 |
| issuccess | boolean | 否 |  | 是否执行成功 |
| msg | string | 否 |  | 返回信息 |

### 请求示例

```json
{
  "io_id": 0
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
  "code": 120,
  "msg": "错误信息",
  "request_id": "xxxxxxxxx",
  "data": "{}/[]"
}
```


---

## 创建调拨差异单

`/open/jushuitan/diffallocate/create`

| 项 | 内容 |
|---|---|
| 接口名称 | 创建调拨差异单 |
| 接口路径 | `/open/jushuitan/diffallocate/create` |
| docType / docId | 12 / 357 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=12&docId=357 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/diffallocate/create` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/diffallocate/create` |


### 接口说明

ERP界面-【库存调拨】
 入参必须为已确认的调拨入单据，差异数支持负数

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
| io_id | string | 是 |  | 调拨入单号 |
| items | array | 是 |  | 商品集合 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 |  | 商品编码（最多100个） |
| items[].qty | number | 是 |  | 商品数量（调拨入库单的实际入库数量，差异数量是算出来的） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 状态码，0 代表成功 |
| issuccess | boolean | 是 |  | 是否调用成功，true是；false否 |
| msg | string | 是 |  | 返回描述 |
| data | array | 是 |  |  |
| data[] | object | 否 |  |  |
| data[].io_id | number | 是 |  | 创建的差异调拨单号 |

### 请求示例

```json
{
  "items": [
    {
      "qty": 0,
      "sku_id": ""
    }
  ],
  "io_id": ""
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "issuccess": true,
  "data": [
    {
      "io_id": 0
    }
  ]
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
