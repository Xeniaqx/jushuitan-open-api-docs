# 聚水潭开放平台 · 采购API（线下版）

> 抓取日期：2026-11-23  
> 分类：采购API（docType=6）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=6&docId=26

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 采购单查询 | `/open/purchase/query` | 26 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=26) |
| 采购单上传 | `/open/jushuitan/purchase/upload` | 27 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=27) |
| 供应商上传 | `/open/supplier/upload` | 28 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=28) |
| 供应商查询 | `/open/supplier/query` | 29 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=29) |
| 加工单查询 | `/open/jushuitan/manufacture/query` | 52 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=52) |
| 加工单上传 | `/open/jushuitan/manufacture/upload` | 55 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=55) |
| 采购单加工单标签（新增/移除） | `/open/jushuitan/purchaselabel/upload` | 63 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=63) |
| 预约入库上传 | `/open/jushuitan/appointmentin/upload` | 92 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=92) |
| 预约入库查询列表 | `/open/jushuitan/purchasebooking/query` | 156 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=156) |
| 变更采购单状态 | `/open/jushuitan/purchase/change/status` | 193 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=193) |
| 采购单/加工单/预约入库单作废 | `/open/webapi/wmsapi/purchase/cancel` | 452 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=452) |
| 修改采购单 | `/open/webapi/wmsapi/openpurchase/editpurchase` | 698 | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=698) |

## 目录

- [采购单查询](#采购单查询)
- [采购单上传](#采购单上传)
- [供应商上传](#供应商上传)
- [供应商查询](#供应商查询)
- [加工单查询](#加工单查询)
- [加工单上传](#加工单上传)
- [采购单加工单标签（新增/移除）](#采购单加工单标签新增移除)
- [预约入库上传](#预约入库上传)
- [预约入库查询列表](#预约入库查询列表)
- [变更采购单状态](#变更采购单状态)
- [采购单/加工单/预约入库单作废](#采购单加工单预约入库单作废)
- [修改采购单](#修改采购单)

---

## 采购单查询

`/open/purchase/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 采购单查询 |
| 接口路径 | `/open/purchase/query` |
| docType / docId | 6 / 26 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=26 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/purchase/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/purchase/query` |


### 接口说明

系统相关界面：【采购】------【采购单管理】

 如需获取实际入库数量请调用采购入库查询接口： https://openweb.jushuitan.com/dev-doc?docType=7&docId=901 ，对应采购入库单（已入库状态）的商品明细数量

 更多采购API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=19&currentPage=1&pageSize=20

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
| modified_begin | string | 否 | 2021-12-02 00:00:00 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与外部单号不能同时为空 |
| modified_end | string | 否 | 2021-12-09 00:00:00 | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与外部单号不能同时为空 |
| so_ids | array | 否 |  | 外部单号 对应采购单管理页面外部单号(且对应采购单上传的external_id)，和时间段不能同时为空 |
| so_ids[] | string | 否 |  |  |
| po_ids | array | 否 |  | 采购单号 与时间查询条件不能同时为空 |
| po_ids[] | string | 否 |  |  |
| is_lock | string | 否 | true | 是否返回运营云仓信息 |
| status | string | 否 | WaitConfirm | 采购单状态:Creating:草拟,WaitConfirm:待审核,Confirmed:已确认,WaitDeliver:待发货,WaitReceive:待收货,Finished:完成,Cancelled:作废 |
| statuss | array | 否 |  | 采购单状态(可传多个):Creating:草拟,WaitConfirm:待审核,Confirmed:已确认,WaitDeliver:待发货,WaitReceive:待收货,Finished:完成,Cancelled:作废 |
| statuss[] | string | 否 |  |  |

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
| data.datas | array | 否 |  | 数据集合 |
| data.datas[] | object | 否 |  |  |
| data.datas[].po_date | string | 否 | 2021-11-1815:31:49 | 采购日期 |
| data.datas[].po_id | integer | 否 | 113622 | 采购单号 |
| data.datas[].so_id | string | 否 |  | 外部单号;对应采购单管理页面外部单号(且对应采购单上传的external_id) |
| data.datas[].remark | string | 否 |  | 备注 |
| data.datas[].status | string | 否 | Confirmed | 状态:Creating:草拟,WaitConfirm:待审核,Confirmed:已确认,Finished:完成,Cancelled:作废，Delete:删除 |
| data.datas[].supplier_id | integer | 否 | 763 | 供应商编码 |
| data.datas[].seller | string | 否 | 广州许诺化妆品有限公司123 | 供应商名称 |
| data.datas[].tax_rate | integer | 否 |  | 税率 |
| data.datas[].purchaser_name | string | 否 | 肺棘 | 采购员 |
| data.datas[].send_address | string | 否 | 上海上海市浦东新区华业公寓 | 送货地址 |
| data.datas[].plat_so_id | string | 否 |  | 1688线上采购单号 |
| data.datas[].outer_status | string | 否 |  | 1688线上采购状态 |
| data.datas[].member_id | string | 否 |  | 1688线上d |
| data.datas[].member_name_1688  | string | 否 |  | 1688线上采购账号(开了基础设置：Aliababa.Purchase) |
| data.datas[].online_purchase_memos  | string | 否 |  | 1688 线上采购备忘(开了基础设置：Aliababa.Purchase 且 开了统一开关：cb.showtwpurchase) |
| data.datas[].plat_pay_date | string | 否 |  | 线上付款时间 |
| data.datas[].term | string | 否 |  | 合同条款 |
| data.datas[].item_type | string | 否 | 成品 | 商品类型 |
| data.datas[].items | array | 否 |  | 商品明细数据集合 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].sku_id | string | 否 | 1234560 | 商品编码 |
| data.datas[].items[].name | string | 否 | 羊毛双面围巾 | 商品名称 |
| data.datas[].items[].qty | integer | 否 | 1 | 数量，非实际入库数量，如需获取实际入库数量请调用采购入库查询接口，对应采购入库单（已入库状态）的商品明细数量 |
| data.datas[].items[].plan_arrive_qty | integer | 否 |  | 协议到货数量 |
| data.datas[].items[].price | number | 否 | 5999.4 | 单价 |
| data.datas[].items[].i_id | string | 否 | 102025 | 款号 |
| data.datas[].items[].po_id | integer | 否 | 113622 | 采购单编号 |
| data.datas[].items[].poi_id | integer | 否 | 620961 | 采购单明细编号 |
| data.datas[].items[].delivery_date | string | 否 |  | 协议到货日期 |
| data.datas[].items[].remark | string | 否 |  | 备注 |
| data.datas[].items[].tax_rate | number | 否 |  | 税率 |
| data.datas[].items[].qc_qty | number | 否 |  | 质检数 |
| data.datas[].items[].qc_quality_qty | number | 否 |  | 质检正品数 |
| data.datas[].items[].qc_defective_qty | number | 否 |  | 质检次品数 |
| data.datas[].items[].inQty | number | 否 |  | 已入库数 |
| data.datas[].items[].return_qty | number | 否 |  | 退货数 |
| data.datas[].items[].is_delivery | number | 否 |  | 是否上架：2全部上架 1部分上架 0未上架 |
| data.datas[].labels | string | 否 |  | 多标签 |
| data.datas[].confirm_date | string | 否 | 2021-11-1817:43:20 | 审核生效日期 |
| data.datas[].finish_time | string | 否 |  | 完成日期 |
| data.datas[].modified | string | 否 |  | 修改时间 |
| data.datas[].wms_co_id | integer | 否 | 0 | 分仓编码（非分仓编码比如空值或者0都是主仓的） |
| data.datas[].receive_status | string | 否 |  | 收货状态:Timeout:预计收货超时,Received:全部入库,Part_Received:部分入库,空值或Not_Received:未入库 |
| data.datas[].more_rate | number | 否 | 0.0 | 溢装比 |
| data.datas[].freight | number | 否 |  | 运费 |
| data.datas[].lock_lwh_id | number | 否 |  | 运营云仓编码 （入参是否返回运营云仓信息字段传true才会返回）采购单界面指定运营云仓时返回 |
| data.datas[].lock_priority_json | string | 否 | "{\"149\":\"\"}" | 运营云仓编码（采购单由 运营云仓 采购申请 生成时返回） |
| data.datas[].merge_po_id | string | 否 |  | 汇总采购单号 |
| data.datas[].source_o_id | number | 否 |  | 来源单号 |
| data.datas[].payment_method | string | 否 |  | 支付方式（CurrentSettlement：现结-立付；MonthlyStatement：账期结算；CashOnDelivery：现结-到付） |
| data.datas[].logistics | array | 否 |  | 物流信息 |
| data.datas[].logistics[] | string | 否 |  |  |
| data.datas[].l_id | string | 否 |  | 物流单号 |
| data.datas[].logistics_company | string | 否 |  | 物流公司 |
| data.datas[].receiver_name | string | 否 |  | 收件人姓名 |
| data.datas[].receiver_phone | string | 否 |  | 收件人电话 |

### 请求示例

```json
{
  "page_index": 1,
  "page_size": 50,
  "po_ids": [
    "649281"
  ]
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
        "seller": "标签",
        "send_address": "   地址",
        "po_id": 649281,
        "item_type": "成品",
        "freight": null,
        "logistics": [
          {
            "logistics_company": "无",
            "l_id": "无"
          }
        ],
        "remark": "API接单",
        "tax_rate": 0,
        "so_id": "C26013080",
        "purchaser_name": "姐",
        "modified": "2026-01-28 20:32:48",
        "receiver_name": "",
        "term": "无",
        "wms_co_name": "",
        "payment_method": null,
        "more_rate": 15,
        "po_date": "2026-01-12 20:23:54",
        "finish_time": null,
        "receive_status": "Part_Received",
        "labels": "暂无标签",
        "wms_co_id": 0,
        "confirm_date": "2026-01-12 21:04:54",
        "logistics_company": "无",
        "l_id": "无",
        "receiver_phone": "",
        "supplier_id": 16109904,
        "source_o_id": null,
        "items": [
          {
            "i_id": "****",
            "amount": 0,
            "po_id": 649281,
            "plan_arrive_qty": 0,
            "sku_id": "****",
            "remark": null,
            "inQty": 3,
            "is_delivery": 0,
            "qc_quality_qty": null,
            "tax_rate": 0,
            "delivery_date": "2026-01-19 23:59:59",
            "properties_value": "白;XS",
            "custom_info": null,
            "price": 0,
            "qty": 20,
            "name": "****",
            "qc_qty": null,
            "poi_id": 5576571,
            "return_qty": null,
            "qc_defective_qty": null
          }
        ],
        "status": "Confirmed"
      }
    ],
    "requestId": null,
    "page_index": 1,
    "has_next": false,
    "data_count": 1,
    "page_count": 1,
    "page_size": 50
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

## 采购单上传

`/open/jushuitan/purchase/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 采购单上传 |
| 接口路径 | `/open/jushuitan/purchase/upload` |
| docType / docId | 6 / 27 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=27 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/purchase/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/purchase/upload` |


### 接口说明

系统相关界面：【采购】------【采购单管理】

 更多采购API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=19&currentPage=1&pageSize=20

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
| is_confirm | boolean | 否 | true | 是否自动确认单据 |
| wms_co_id | integer | 否 |  | 分仓编号 |
| supplier_id | integer | 是 | 3726343 | 供应商编码 |
| item_type | string | 否 | 半成品 | 商品类型:成品/半成品/原材料 |
| external_id | string | 是 | 202106071848 | 外部单号 （单据上传成功之后对应页面外部单号） |
| remark | string | 否 | 测试 | 备注（如果不传字段key也不要传）；可更新非作废、非完成状态的采购单 |
| term | string | 否 | 合同条款 | 合同条款 |
| send_address | string | 否 | 地址 | 送货地址 |
| purchaser_name | string | 否 | 采购人 | 采购员 |
| tax_rate | integer | 否 | 0 | 税率 ，17%时请传17 |
| more_rate | integer | 否 |  | 溢装比例，传1就是1% |
| po_date | string | 否 | 2020-3-22 00:00:00 | 采购日期 |
| currency | string | 否 | EUR | 币种 |
| items | array | 是 |  | 明细列表 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | CU-1 | 商品编码 |
| items[].qty | integer | 是 | 100 | 数量 |
| items[].price | number | 否 | 20 | 价格 |
| items[].remark | string | 否 |  | 明细备注；可更新非作废、非完成状态的采购单 |
| items[].tax_rate | integer | 否 | 0 | 商品明细税率，17%时请传17 |
| items[].plan_arrive_qty | number | 否 |  | 协议到货数量 |
| items[].plan_arrive_date | string | 否 |  | 协议到货时间 |
| items[].batch_id | string | 否 |  | 批次号（需要开启生产批次开关） |
| items[].produced_date | string | 否 |  | 批次生产日期 |
| items[].expiration_date | string | 否 |  | 批次有效期 |
| items[].currency_price | number | 否 |  | 外币金额 |
| l_id | string | 否 | 123 | 物流单号；可更新非作废、非完成状态的采购单 |
| logistics_company | string | 否 | 滴滴 | 物流公司；可更新非作废、非完成状态的采购单 |
| receiver_state | string | 否 |  | 省 |
| receiver_city | string | 否 |  | 市 |
| receiver_district | string | 否 |  | 区\|县（省市区都填写地址默认填写的省市区如不填写取仓库的省市区） |
| freight | number | 否 |  | 运费 |
| labels | array | 否 |  | 标签 |
| labels[] | string | 否 |  |  |
| lock_lwh_id | number | 否 |  | 运营云仓编码 |
| is_edit | boolean | 否 |  | 是否更新单据（true才会更新） |
| payment_method | string | 否 |  | 付款方式（CurrentSettlement 现结-立付 CashOnDelivery 现结-到付 MonthlyStatement 账期结算） |
| accounting_period_days | string | 否 |  | 账期天数（付款方式有值才起效） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 |  | 错误描述 |
| data | object | 否 |  |  |
| data.data | object | 否 |  |  |
| data.data.po_id | integer | 否 | 2842 | 聚水潭采购单号 |
| data.data.external_id | string | 否 | 202003241670 | 外部采购单号（单据上传成功之后对应页面外部单号） |

### 请求示例

```json
{
  "po_date": "2020-3-22 00:00:00",
  "send_address": "地址",
  "item_type": "半成品",
  "receiver_city": "",
  "receiver_district": "",
  "merge_po_id": "",
  "external_id": "202106071848",
  "remark": "测试",
  "tax_rate": 0,
  "receiver_state": "",
  "wms_co_id": 0,
  "is_confirm": true,
  "purchaser_name": "采购人",
  "term": "合同条款",
  "logistics_company": "滴滴",
  "l_id": "123",
  "supplier_id": 3726343,
  "items": [
    {
      "price": 20,
      "qty": 100,
      "plan_arrive_date": "2020-3-25 00:00:00",
      "sku_id": "CU-1",
      "remark": "",
      "tax_rate": 0
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
    "data": {
      "po_id": 2842,
      "external_id": "202003241670"
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

## 供应商上传

`/open/supplier/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 供应商上传 |
| 接口路径 | `/open/supplier/upload` |
| docType / docId | 6 / 28 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=28 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/supplier/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/supplier/upload` |


### 接口说明

系统相关界面：【设置】------【供应商信息】

 自2020年1月开始，开放平台接口将逐步调整为只接收HTTPS请求
 修改的判断依据： name或者supplier_code有一个已存在，则修改，两个值都不存在，则新增

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
| data.page_size | integer | 否 | 2 | 每页多少条 |
| data.page_index | integer | 否 | 1 | 第几页 |
| data.data_count | integer | 否 | 2 | 总条数 |
| data.page_count | integer | 否 | 1 | 总页数 |
| data.has_next | boolean | 否 | false | 是否有下一页 |
| data.datas | array | 否 |  | 数据集合 |
| data.datas[] | object | 否 |  |  |
| data.datas[].id | integer | 否 | 3726342 | 供应商内部编码 erp唯一 |
| data.datas[].issuccess | boolean | 否 | true | 是否成功 |
| data.datas[].msg | string | 否 | name[测试111];supplier_code[供应商编码1254]新增成功! | 提示信息 |
| data.datas[].name | string | 否 | 测试111 | 供应商名称 |
| data.datas[].supplier_code | string | 否 | 供应商编码1254 | 供应商编码 |

### 请求示例

```json
[
  {
    "address": "地址",
    "begin_date": "2020-01-03 14:34:40",
    "mobile": "手机",
    "remark": "备注1",
    "enabled": true,
    "phone": "电话",
    "depositbank": "开户银行",
    "name": "测试111",
    "acountnumber": "银行账号",
    "supplier_code": "供应商编码1254",
    "contacts": "联系人",
    "remark3": "备注3",
    "bankacount": "账户名称",
    "remark2": "备注2",
    "group": ""
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
        "msg": "name[测试111];supplier_code[供应商编码1254]新增成功!",
        "issuccess": true,
        "name": "测试111",
        "id": 3726342,
        "supplier_code": "供应商编码1254"
      }
    ],
    "page_index": 1,
    "has_next": false,
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

## 供应商查询

`/open/supplier/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 供应商查询 |
| 接口路径 | `/open/supplier/query` |
| docType / docId | 6 / 29 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=29 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/supplier/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/supplier/query` |


### 接口说明

系统相关界面：【设置】------【供应商信息】

 自2020年1月开始，开放平台接口将逐步调整为只接收HTTPS请求

 更多采购API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=19&currentPage=1&pageSize=20

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
| supplier_codes | array | 否 |  | 供应商编码 |
| supplier_codes[] | string | 否 |  |  |
| page_index | integer | 否 | 1 | 第几页，从1开始 |
| page_size | integer | 否 | 30 | 默认30，最大不超过500 |
| modified_begin | string | 否 | 2021-12-0215:55:06 | 修改起始时间 |
| modified_end | string | 否 | 2021-12-0915:55:06 | 修改结束时间；时间跨度不能超过1天 |
| supplier_ids | array | 否 |  | 供应商内部编码 最大50条 |
| supplier_ids[] | integer | 否 |  |  |
| names | array | 否 |  | 供应商名称 最大50条 |
| names[] | string | 否 |  |  |

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
| data.datas | array | 否 |  | 数据集合 |
| data.datas[] | object | 否 |  |  |
| data.datas[].supplier_id | integer | 否 | 63316 | 供应商内部编码 |
| data.datas[].supplier_code | string | 否 | xincheng | 供应商编码 |
| data.datas[].name | string | 否 | 辛橙 | 供应商名称 |
| data.datas[].modified | string | 否 | 2020-04-2409:16:43 | 修改时间 |
| data.datas[].remark | string | 否 |  | 备注1 |
| data.datas[].remark2 | string | 否 |  | 备注2 |
| data.datas[].remark3 | string | 否 |  | 备注3 |
| data.datas[].group | string | 否 | 啦啦啦 | 供应商分类 |
| data.datas[].enabled | boolean | 否 |  | 是否启用，true：启用，false：未启用 |
| data.datas[].depositbank | string | 否 |  | 开户银行 |
| data.datas[].bankacount | string | 否 |  | 账户名称 |
| data.datas[].acountnumber | string | 否 |  | 银行账号 |

### 请求示例

```json
{
  "names": [],
  "supplier_codes": [],
  "page_index": 1,
  "modified_begin": "2021-12-0215:55:06",
  "modified_end": "2021-12-0915:55:06",
  "supplier_ids": [],
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
        "depositbank": "",
        "name": "辛橙",
        "modified": "2020-04-2409:16:43",
        "remark": "",
        "acountnumber": "",
        "supplier_id": 63316,
        "supplier_code": "xincheng",
        "remark3": "",
        "enabled": true,
        "bankacount": "",
        "remark2": "",
        "group": "啦啦啦"
      }
    ],
    "page_index": 1,
    "has_next": false,
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

## 加工单查询

`/open/jushuitan/manufacture/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 加工单查询 |
| 接口路径 | `/open/jushuitan/manufacture/query` |
| docType / docId | 6 / 52 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=52 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/manufacture/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/manufacture/query` |


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
| page_size | integer | 否 | 30 | 每页多少条，默认20条，最大100条 |
| start_time | string | 是 | 2022-02-1715:55:06 | 起始时间，和结束时间必须同时存在，时间间隔不能超过七天 |
| end_time | string | 是 | 2022-02-2315:55:06 | 结束时间，和起始时间必须同时存在，时间间隔不能超过七天 |
| date_type | integer | 否 | 0 | 默认0；0=修改时间，1=创建时间，2=加工日期 |
| so_ids | array | 否 |  | 外部单号 列表，最大20，和开始时间，结束时间不能同时为空 |
| so_ids[] | string | 否 |  |  |
| mo_ids | array | 否 |  | 加工单号 列表，最大20，和开始时间，结束时间不能同时为空 |
| mo_ids[] | string | 否 |  |  |
| statusList | array | 否 |  | 状态:Creating:草拟,WaitConfirm:待审核,Confirmed:已确认,Finished:完成,Cancelled:作废，和开始时间，结束时间不能同时为空 |
| statusList[] | string | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| page_size | integer | 否 |  | 每页多少条 |
| page_index | integer | 否 |  | 第几页 |
| has_next | boolean | 否 |  | 是否有下一页 |
| page_count | integer | 否 |  | 总页数 |
| data_count | integer | 否 |  | 总条数 |
| datas | array | 否 |  | 数据集合 |
| datas[] | object | 否 |  |  |
| datas[].po_id | integer | 否 |  | 加工单号 |
| datas[].po_date | string | 否 |  | 加工日期 |
| datas[].seller | string | 否 |  | 加工工厂 |
| datas[].send_address | string | 否 |  | 送货地址 |
| datas[].term | string | 否 |  | 合同条款 |
| datas[].status | string | 否 |  | 状态；WaitConfirm=待审核；Confirmed=已确认；Finished=完成；Cancelled=作废 |
| datas[].purchaser_name | string | 否 |  | 下单人 |
| datas[].labels | string | 否 |  | 标签 |
| datas[].print_count | integer | 否 |  | 打印次数 |
| datas[].manufacture_type  | string | 否 |  | 加工类型：组装加工/改码加工/拆分加工 |
| datas[].sub_type | string | 否 |  | 加工种类 |
| datas[].weight | number | 否 |  | 预估重量 |
| datas[].volume | number | 否 |  | 预估体积 |
| datas[].wms_co_id | integer | 否 |  | 加工仓储方编号 |
| datas[].receipt_wms_co_id | integer | 否 |  | 收货仓储方编号 |
| datas[].modified | string | 否 |  | 修改时间 |
| datas[].created | string | 否 |  | 创建时间 |
| datas[].items | array | 否 |  | 成品集合 |
| datas[].items[] | object | 否 |  |  |
| datas[].items[].pic | string | 否 |  | 图片 |
| datas[].items[].sku_id | string | 否 |  | 商品编码 |
| datas[].items[].name | string | 否 |  | 商品名称 |
| datas[].items[].properties_value | string | 否 |  | 颜色及规格 |
| datas[].items[].i_id | string | 否 |  | 款式编码 |
| datas[].items[].qty | integer | 否 |  | 数量 |
| datas[].items[].plan_arrive_qty | integer | 否 |  | 预计完成加工数 |
| datas[].items[].delivery_date | string | 否 |  | 预计加工完成时间 |
| datas[].items[].price | number | 否 |  | 物料成本 |
| datas[].items[].processing_charges | number | 否 |  | 加工费 |
| datas[].items[].amount | number | 否 |  | 总金额 |
| datas[].items[].remark | string | 否 |  | 备注 |
| datas[].items[].io_qty | integer | 否 |  | 已入库数 |
| datas[].raws | array | 否 |  | 原料集合 |
| datas[].raws[] | object | 否 |  |  |
| datas[].raws[].pic | string | 否 |  | 图片 |
| datas[].raws[].sku_id | string | 否 |  | 商品编码 |
| datas[].raws[].name | string | 否 |  | 商品名称 |
| datas[].raws[].properties_value | string | 否 |  | 颜色及规格 |
| datas[].raws[].qty | integer | 否 |  | 数量 |
| datas[].raws[].remark | string | 否 |  | 备注 |
| datas[].batchs | array | 否 |  | 批次集合 |
| datas[].batchs[] | object | 否 |  |  |
| datas[].batchs[].batch_no | string | 否 |  | 批次号 |
| datas[].batchs[].sku_id | string | 否 |  | 商品编码 |
| datas[].batchs[].qty | integer | 否 |  | 数量 |
| datas[].batchs[].product_date | string | 否 |  | 批次日期 |
| datas[].batchs[].supplier_id | integer | 否 |  | 供应商编号 |
| datas[].batchs[].supplier_name | string | 否 |  | 供应商名称 |
| datas[].batchs[].expiration_date | string | 否 |  | 有效期至 |
| datas[].wave_id | integer | 否 |  | 拣货批次号 |
| datas[].remark | string | 否 |  | 备注 |
| datas[].out_lwh_id | integer | 否 |  | 收货运营云仓编号 |
| datas[].in_lwh_id | integer | 否 |  | 加工运营云仓编号 |
| code | integer | 否 |  | 错误码 |
| issuccess | boolean | 否 |  | true代表成功 |
| msg | string | 否 |  | 错误信息 |

### 请求示例

```json
{
  "start_time": "2022-02-17 15:55:06",
  "end_time": "2022-02-23 15:55:06",
  "page_index": 1,
  "page_size": 30,
  "date_type": 0
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {
    "datas": [],
    "page_index": 1,
    "has_next": false,
    "data_count": 0,
    "page_count": 0,
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

## 加工单上传

`/open/jushuitan/manufacture/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 加工单上传 |
| 接口路径 | `/open/jushuitan/manufacture/upload` |
| docType / docId | 6 / 55 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=55 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/manufacture/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/manufacture/upload` |


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
| so_id | string | 是 |  | 外部单号 |
| is_force_confirm | boolean | 否 |  | 强制审核，默认false |
| po_date | string | 是 |  | 加工单时间 |
| outer_po_id | string | 否 |  | 线上单号 |
| seller_id | integer | 是 |  | 加工工厂编号（供应商编号） |
| send_address | string | 否 |  | 送货地址 |
| term | string | 否 |  | 合同条款 |
| labels | array | 否 |  | 标签</div |
| labels[] | string | 否 |  |  |
| wms_co_id | integer | 否 |  | 加工仓储方 |
| receipt_wms_co_id | integer | 否 |  | 收货仓储方 |
| remark | string | 否 |  | 备注 |
| items | array | 是 |  | 加工后商品；当选择加工类型=拆分加工，加工后商品不传值，在审核时会根据成品BOM自动生成 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 |  | 商品编码 |
| items[].qty | number | 是 |  | 数量 |
| items[].plan_arrive_qty | number | 否 |  | 预计完成加工数 |
| items[].delivery_date | string | 否 |  | 预计完成加工时间 |
| items[].price | string | 否 |  | 物料成本 |
| items[].processing_charges | string | 否 |  | 加工费 |
| items[].remark | string | 否 |  | 备注 |
| raws | array | 否 |  | 加工前商品；当选择加工类型=组装加工，加工前商品不传值，在审核时会根据成品BOM自动生成 |
| raws[] | object | 否 |  |  |
| raws[].sku_id | string | 是 |  | 商品编码 |
| raws[].qty | string | 是 |  | 数量 |
| raws[].plan_arrive_qty | string | 否 |  | 预计完成加工数 |
| raws[].delivery_date | string | 否 |  | 预计完成加工时间 |
| raws[].price | string | 否 |  | 物料成本 |
| raws[].processing_charges | string | 否 |  | 加工费 |
| raws[].remark | string | 否 |  | 备注 |
| is_confirm | boolean | 否 |  | 是否自动确认单据（默认false待审核） |
| manufacture_type | number | 否 |  | 1.组装加工；2.拆分加工(不传或其他值都认为是组装加工，如果labels中已指定组装加工或拆分加工。则优先以labels中的类型为准，否则取manufacture_type) |
| manufacture_mode | number | 否 |  | 加工模式：1.随机加工；2.标准加工(BOM)（不传或或传入其它值都认为是随机加工，如果labels中已指定标准加工(BOM)或随机加工，则已labels中的加工模式为准。否则取manufacture_mode） |
| more_rate | number | 否 |  | 溢装比例，范围0~1000，精度两位小数 |
| wh_id | number | 否 |  | 加工仓库：默认为主仓（主仓=1，销退仓=2，进货仓=3，次品仓=4，自定义1仓=6，自定义2仓=7，自定义3仓=8，自定义4仓=9，自定义5仓=10，自定义6仓=11，自定义7仓=12，自定义8仓=13，自定义9仓=14，自定义10仓=15（对应ERP仓库资料设定页面，剩下的仓以此类推）） |
| receipt_wh_id | number | 否 |  | 收货仓库，默认为空（主仓=1，销退仓=2，进货仓=3，次品仓=4，自定义1仓=6，自定义2仓=7，自定义3仓=8，自定义4仓=9，自定义5仓=10，自定义6仓=11，自定义7仓=12，自定义8仓=13，自定义9仓=14，自定义10仓=15（对应ERP仓库资料设定页面，剩下的仓以此类推）） |
| out_lwh_id | number | 否 |  | 加工虚拟仓 |
| receipt_lwh_id | number | 否 |  | 收货虚拟仓 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 0代码成功 |
| issuccess | boolean | 否 | true | 是否成功描述 |
| msg | string | 否 | 执行成功 | 执行结果描述 |
| data | object | 否 |  |  |
| data.po_id | number | 否 |  | 加工单号 |
| data.so_id | string | 否 |  | 线上单号 |

### 请求示例

```json
{
  "po_date": "",
  "outer_po_id": "",
  "wms_co_id": 0,
  "send_address": "",
  "so_id": "",
  "receipt_wms_co_id": 0,
  "is_confirm": true,
  "term": "",
  "remark": "",
  "items": [
    {
      "delivery_date": "",
      "plan_arrive_qty": 0,
      "price": "",
      "qty": 0,
      "sku_id": "",
      "remark": "",
      "processing_charges": ""
    }
  ],
  "seller_id": 0,
  "labels": []
}
```


### 响应示例

```json
{
  "data": {
    "po_id": 47817,
    "so_id": "20240515174927550721"
  },
  "code": 0,
  "issuccess": true,
  "msg": "执行成功"
}
```


### 异常示例

```json
{
  "code": 190,
  "msg": "验证失败！无API权限，请申请API权限"
}
```


---

## 采购单加工单标签（新增/移除）

`/open/jushuitan/purchaselabel/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 采购单加工单标签（新增/移除） |
| 接口路径 | `/open/jushuitan/purchaselabel/upload` |
| docType / docId | 6 / 63 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=63 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/purchaselabel/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/purchaselabel/upload` |


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
| po_id | integer | 否 |  | 采购单号/ 加工单号 ，与线上单号不能同时为空，二者都存在时以采购单号为准 |
| so_id | string | 否 |  | 线上单号，与采购单号不能同时为空，二者都存在时以采购单号为准 |
| labels | array | 是 |  | 标签列表，数量大于0且小于20，单个标签长度10，不可重复 |
| labels[] | string | 否 |  |  |
| action_type | integer | 否 |  | 操作类型，1=新增，2=移除，默认1 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 |  | 状态码 |
| msg | string | 否 |  | 执行结果描述 |
| data | object | 是 |  | 业务返回结果 |

### 请求示例

```json
{
  "po_id": 0,
  "action_type": 0,
  "so_id": "",
  "labels": []
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

## 预约入库上传

`/open/jushuitan/appointmentin/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 预约入库上传 |
| 接口路径 | `/open/jushuitan/appointmentin/upload` |
| docType / docId | 6 / 92 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=92 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/appointmentin/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/appointmentin/upload` |


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
| po_ids | array | 否 |  | 采购单号列表，最大10个，无采购预约入库，供应商内部id必填 |
| po_ids[] | integer | 否 | 6321 | 采购单号 |
| wms_co_id | integer | 否 | 11111111 | 分仓编号 |
| supplier_id | integer | 否 | 1231231 | 供应商内部编号 无采购单时必填 |
| external_id | string | 是 | 202007201834 | 外部预约单号 |
| plan_arrive_date | string | 是 | 2025-04-18 16:37:16 | 预约到货时间 |
| remark | string | 否 | 备注 | 备注 |
| send_address | string | 否 | 送货地址1 | 送货地址 |
| item_type | string | 是 | 正品 | 商品类型；可选值：成品；半成品；原材料 |
| labels | string | 是 |  | 标签，多个逗号分隔 |
| items | array | 是 |  | 商品列表 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | CBB01 | 商品编码 |
| items[].qty | integer | 是 | 1 | 预约到货数量，审核前可更新 |
| is_confirm | boolean | 是 | true | 是否自动确认；默认false |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 |  | 错误码 |
| msg | string | 否 |  | 错误描述 |
| data | object | 否 |  | 返回内容 |
| data.external_id | string | 否 |  | 外部单号 |
| data.po_id | integer | 否 |  | 内部预约单号 |

### 请求示例

```json
{
  "wms_co_id": 11111111,
  "send_address": "送货地址1",
  "item_type": "正品",
  "is_confirm": true,
  "plan_arrive_date": "2020-7-20",
  "external_id": "202007201834",
  "remark": "备注",
  "supplier_id": 1231231,
  "items": [
    {
      "qty": 1,
      "sku_id": "CBB01"
    }
  ],
  "po_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "po_id": 0,
    "external_id": ""
  }
}
```


### 异常示例

```json
{
  "code": 130,
  "issuccess": false,
  "msg": "无采购单预约入库，需要选择供应商信息"
}
```


---

## 预约入库查询列表

`/open/jushuitan/purchasebooking/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 预约入库查询列表 |
| 接口路径 | `/open/jushuitan/purchasebooking/query` |
| docType / docId | 6 / 156 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=156 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/purchasebooking/query` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/purchasebooking/query` |


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
| start_time | string | 否 |  | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天 |
| end_time | string | 否 |  | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天 |
| page_index | integer | 是 |  | 第几页，从1 开始 |
| page_size | integer | 是 |  | 每页多少条，最大100条 |
| bio_ids | array | 否 |  | 预约单号（最大20，仅查询近一 年内的单据，与时间条件不能同时为空） |
| bio_ids[] | number | 否 |  |  |
| po_ids | array | 否 |  | 采购单号（最大20，仅查询近一 年内的单据，与时间条件不能同时为空） |
| po_ids[] | number | 否 |  |  |
| external_ids | array | 否 |  | 外部单号（最大20，仅查询近一 年内的单据，与时间条件不能同时为空） |
| external_ids[] | string | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| page_size | integer | 否 |  | 每页多少条 |
| page_index | integer | 否 |  | 第几页 |
| has_next | boolean | 否 |  | 是否有下一页 |
| page_count | integer | 否 |  | 总页数 |
| data_count | integer | 否 |  | 总条数 |
| datas | array | 否 |  | 数据集合 |
| datas[] | object | 否 |  |  |
| datas[].po_id | integer | 否 |  | 预约单号 |
| datas[].merge_po_id | string | 否 |  | 采购单号 |
| datas[].seller_id | integer | 否 |  | 供应商编号 |
| datas[].seller | string | 否 |  | 供应商名称 |
| datas[].external_id | string | 否 |  | 线上单号 |
| datas[].created | string | 否 |  | 创建时间 |
| datas[].plan_arrive_date | string | 否 |  | 预计到货时间 |
| datas[].modified | string | 否 |  | 修改时间 |
| datas[].status | string | 否 |  | 状态：WaitConfirm ：待审核：Confirmed ：已确认；Finished ：完成；Cancelled：作废；OuterConfirming ：外部确认中 |
| datas[].remark | string | 否 |  | 备注 |
| datas[].send_address | string | 否 |  | 收货地址 |
| datas[].creator_name | string | 否 |  | 创建人 |
| datas[].wms_co_id | integer | 否 |  | 分仓编号 |
| datas[]. items | array | 否 |  | 创建人 |
| datas[]. items[] | object | 否 |  | 商品明细 |
| datas[]. items[].poi_id | integer | 否 |  | 入库子单号 |
| datas[]. items[].sku_id | string | 否 |  | 商品编码 |
| datas[]. items[].i_id | string | 否 |  | 商品款号 |
| datas[]. items[].name | string | 否 |  | 商品名称 |
| datas[]. items[].properties_value | string | 否 |  | 颜色及规格 |
| datas[]. items[].qty | integer | 否 |  | 采购数量 |
| datas[]. items[].plan_qty | integer | 否 |  | 本次入库数量 |
| datas[]. items[].plan_arrive_qty | integer | 否 |  | 预约到货数量 |
| datas[]. items[].remark | string | 否 |  | 备注 |
| datas[]. items[].in_qty | integer | 否 |  | 预约已入库数量（需要在ERP设置配置项） |
| code | integer | 否 |  | 错误码 |
| msg | string | 否 |  | 错误信息 |

### 请求示例

```json
{
  "start_time": "2020-09-9 00:00:00",
  "end_time": "2020-09-15 23:59:59",
  "page_index": 1,
  "page_size": 30
}
```


### 响应示例

```json
{
  "page_size": 30,
  "page_index": 1,
  "has_next": false,
  "page_count": 1,
  "data_count": 1,
  "datas": [
    {
      "po_id": 3985,
      "merge_po_id": "",
      "seller_id": 69413,
      "seller": "test09105",
      "external_id": "202009140942",
      "created": "2020-09-14 16:38:27",
      "plan_arrive_date": "2020-07-20 00:00:00",
      "modified": "2020-09-14 16:38:27",
      "status": "WaitConfirm",
      "remark": "备注",
      "send_address": "送货地址1",
      "creator_name": null,
      "items": [
        {
          "poi_id": 7285,
          "sku_id": "CU-6",
          "i_id": "CU-6",
          "name": "安德玛男鞋",
          "properties_value": "26",
          "qty": 0,
          "plan_qty": 0,
          "plan_arrive_qty": 5,
          "remark": ""
        }
      ]
    }
  ],
  "code": 0,
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

## 变更采购单状态

`/open/jushuitan/purchase/change/status`

| 项 | 内容 |
|---|---|
| 接口名称 | 变更采购单状态 |
| 接口路径 | `/open/jushuitan/purchase/change/status` |
| docType / docId | 6 / 193 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=193 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/purchase/change/status` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/purchase/change/status` |


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
| so_ids | array | 否 |  | 外部采购单号,与内部采购单号不能同时为空 |
| so_ids[] | string | 否 |  |  |
| po_ids | array | 否 |  | 内部采购单号，与外部采购单号不能同时为空 |
| po_ids[] | string | 否 |  |  |
| option | number | 是 |  | 操作 1:审核生效 2:变更修改 3:作废 4:完成 5:取消已完成 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 否 |  | 0 代表成功 |
| issuccess | string | 否 |  | 是否成功 |
| msg | string | 否 |  | 错误提示信息 |
| result | array | 否 |  | 结果集合 |
| result[] | object | 否 |  |  |
| result[].code | string | 否 |  | 0 代表成功 |
| result[].issuccess | string | 否 |  | 是否成功 |
| result[].msg | string | 否 |  | 错误提示信息 |
| result[].po_id | string | 否 |  | ERP 内部单号，唯一 |
| result[].so_id | string | 否 |  | 外部采购单单号 |
| result[].status | string | 否 |  | 采购单状态 |

### 请求示例

```json
{
  "so_ids": [
    "PO20220827032"
  ],
  "option": 1
}
```


### 响应示例

```json
{
  "code": 0,
  "issuccess": true,
  "msg": "",
  "result": [
    {
      "code": 0,
      "issuccess": true,
      "msg": "",
      "po_id": 542066,
      "so_id": "PO20220827032",
      "status": "已确认"
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

## 采购单/加工单/预约入库单作废

`/open/webapi/wmsapi/purchase/cancel`

| 项 | 内容 |
|---|---|
| 接口名称 | 采购单/加工单/预约入库单作废 |
| 接口路径 | `/open/webapi/wmsapi/purchase/cancel` |
| docType / docId | 6 / 452 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=452 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/purchase/cancel` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/purchase/cancel` |


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
| po_ids | array | 是 |  | 采购单/加工单/预约入库单内部号（与so_ids二选一必填一项都填写以po_ids为准） |
| po_ids[] | integer | 否 | 234422 |  |
| type | string | 是 | po | 类型（ po：采购单； mo ：加工单；bio：预约入库单 ） |
| so_ids | array | 是 |  | 采购单/加工单/预约入库单线上单号 |
| so_ids[] | string | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | null | 否 |  |  |
| msg | string | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "so_ids": [],
  "type": "po",
  "po_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": "",
  "request_id": ""
}
```


### 异常示例

_无_


---

## 修改采购单

`/open/webapi/wmsapi/openpurchase/editpurchase`

| 项 | 内容 |
|---|---|
| 接口名称 | 修改采购单 |
| 接口路径 | `/open/webapi/wmsapi/openpurchase/editpurchase` |
| docType / docId | 6 / 698 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=6&docId=698 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/openpurchase/editpurchase` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/openpurchase/editpurchase` |


### 接口说明

1、待审核状态的采购单支持修改所有字段，已审核状态的采购单仅支持修改物流公司、物流单号、备注、明细备注4个字段
 2、修改明细必须所有明细sku_id传进来，否则会删除未传入的sku明细

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
| external_id | string | 否 | wsy123456 | 外部单号，与内部采购单号必填一项 |
| po_id | number | 否 |  | 内部采购单号，与外部单号必填一项 |
| wms_co_id | number | 否 |  | 分仓id |
| supplier_id | number | 否 |  | 供应商id |
| item_type | string | 否 |  | 商品类型:成品/半成品/原材料 |
| remark | string | 否 |  | 备注 |
| term | string | 否 |  | 合同条款 |
| send_address | string | 否 |  | 送货详细地址 |
| purchaser_name | string | 否 |  | 采购员 |
| tax_rate | number | 否 |  | 税率 |
| more_rate | number | 否 |  | 溢装比例 |
| po_date | string | 否 |  | 采购日期 |
| logistics_company | string | 否 |  | 物流公司 |
| l_id | string | 否 |  | 物流单号 |
| labels | array | 否 |  | 多标签字段 |
| labels[] | string | 否 |  |  |
| freight | number | 否 |  | 运费 |
| receiver_name | string | 否 |  | 收货人姓名 |
| receiver_phone | string | 否 |  | 收货人电话 |
| lock_lwh_id | number | 否 |  | 虚拟仓Id |
| items | array | 否 |  | 采购明细 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 |  | 商品编码 |
| items[].qty | number | 否 |  | 数量 |
| items[].price | number | 否 |  | 采购单价格 |
| items[].batch_id | string | 否 |  | 生产批次号 |
| items[].produced_date | string | 否 |  | 生产日期 |
| items[].expiration_date | string | 否 |  | 有效期至 |
| items[].delivery_date | string | 否 |  | 协议到货日期 |
| items[].plan_arrive_qty | number | 否 |  | 协议到货数量 |
| items[].remark | string | 否 |  | 备注 |
| items[].tax_rate | number | 否 |  | 税率 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 执行码 |
| msg | string | 是 |  | 返回信息 |
| request_id | string | 是 |  |  |
| data | object | 是 |  |  |
| data.success | boolean | 是 |  | 是否执行成功。true为成功 |
| data.message | string | 是 |  | 返回信息 |

### 请求示例

```json
{
  "po_date": "",
  "send_address": "",
  "item_type": "",
  "freight": 0,
  "external_id": "wsy123456",
  "remark": "",
  "tax_rate": 0,
  "labels": [],
  "lock_lwh_id": 0,
  "wms_co_id": 0,
  "purchaser_name": "",
  "receiver_name": "",
  "term": "",
  "logistics_company": "",
  "l_id": "",
  "receiver_phone": "",
  "supplier_id": 0,
  "items": [
    {
      "batch_id": "",
      "price": 0,
      "qty": 0,
      "plan_arrive_date": "",
      "sku_id": "",
      "remark": "",
      "expiration_date": "",
      "tax_rate": 0,
      "produced_date": ""
    }
  ],
  "more_rate": 0
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": {
    "success": true,
    "message": ""
  },
  "request_id": null
}
```


### 异常示例

```json
{
  "msg": "外部单号或采购单号必传",
  "code": 1,
  "data": null,
  "msg_type": "string",
  "request_id": "1a312e5f17543725470732514e0069"
}
```


---
