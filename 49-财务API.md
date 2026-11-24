# 聚水潭开放平台 · 财务API（线下版）

> 抓取日期：2026-11-23  
> 分类：财务API（docType=49）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=49&docId=1246

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 付款单列表查询 | `/open/api/fmsopen/querypayment` | 1246 | [打开](https://openweb.jushuitan.com/dev-doc?docType=49&docId=1246) |
| 应付单列表查询 | `/open/api/fmsopen/querypayable` | 1247 | [打开](https://openweb.jushuitan.com/dev-doc?docType=49&docId=1247) |
| 【收费】台账数据查询 | `/open/webapi/fms/standingbook/getlistbybatch` | 1320 | [打开](https://openweb.jushuitan.com/dev-doc?docType=49&docId=1320) |
| 业务费用列表查询 | `/open/api/fmsopen/queryoperatingfee` | 1414 | [打开](https://openweb.jushuitan.com/dev-doc?docType=49&docId=1414) |
| 费用项目查询 | `/open/api/fmsopen/queryfinanceproject` | 1437 | [打开](https://openweb.jushuitan.com/dev-doc?docType=49&docId=1437) |

## 目录

- [付款单列表查询](#付款单列表查询)
- [应付单列表查询](#应付单列表查询)
- [【收费】台账数据查询](#收费台账数据查询)
- [业务费用列表查询](#业务费用列表查询)
- [费用项目查询](#费用项目查询)

---

## 付款单列表查询

`/open/api/fmsopen/querypayment`

| 项 | 内容 |
|---|---|
| 接口名称 | 付款单列表查询 |
| 接口路径 | `/open/api/fmsopen/querypayment` |
| docType / docId | 49 / 1246 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=49&docId=1246 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/fmsopen/querypayment` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/fmsopen/querypayment` |


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
| page_index | number | 是 | 1 | 第几页 |
| page_size | number | 是 | 1 | 页大小 |
| start_time | string | 否 | 2025-04-15 | 单据开始时间（与修改时间不能同时为空） |
| end_time | string | 否 | 2025-04-16 | 单据结束时间（与修改时间不能同时为空） |
| modified_begin | string | 否 |  | 最后修改时间-开始（与单据时间不能同时为空） |
| modified_end | string | 否 |  | 最后修改时间-结束（与单据时间不能同时为空） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| page_index | number | 否 |  | 第几页 |
| page_size | number | 否 |  | 多少条 |
| has_next | boolean | 否 |  | 是否有下一页 |
| count | number | 否 |  | 总条数 |
| pages | number | 否 |  | 总页数 |
| datas | array | 否 |  | 付款单数据集合 |
| datas[] | object | 否 |  |  |
| datas[].pay_id | number | 否 |  | 付款编号 |
| datas[].co_id | number | 否 |  | 公司编号 |
| datas[].pay_date | string | 否 |  | 单据日期 |
| datas[].status | string | 否 |  | 状态 |
| datas[].pay_account_number | string | 否 |  | 收款银行账号 |
| datas[].pay_pro_bank | string | 否 |  | 收款单位开户行 |
| datas[].seller_id | number | 否 |  | 往来单位编号 |
| datas[].seller | string | 否 |  | 往来单位名称 |
| datas[].pay_amount | null | 否 |  |  |
| datas[].amount | number | 否 |  | 付款金额 |
| datas[].less_amount | number | 否 |  | 扣款金额 |
| datas[].payway | string | 否 |  | 付款类型 |
| datas[].remark | string | 否 |  | 备注 |
| datas[].created | string | 否 |  | 创建时间 |
| datas[].creator | number | 否 |  | 创建人编号 |
| datas[].modified | string | 否 |  | 最后修改时间 |
| datas[].modifier | number | 否 |  | 最后修改人编号 |
| datas[].creator_name | string | 否 |  | 创建人名称 |
| datas[].modifier_name | string | 否 |  | 最后修改人名称 |
| datas[].po_id | number | 否 |  | 采购单号(仅支持“预付款”和“预付款退款”类型的付款单返回) |
| datas[].account | string | 否 |  | 付款账号 |
| datas[].ispaid | string | 否 |  | 是否支付 |
| datas[].paid_date | string | 否 |  | 打款时间 |
| datas[].labs | string | 否 |  | 标记\|多标签 |
| datas[].seller_type | string | 否 |  | 往来单位类型 |
| datas[].pay_account_name | string | 否 |  | 收款账户名称 |
| datas[].ts | number | 否 |  | 时间ts |
| datas[].paid_status | string | 否 |  | 打款状态，使用新版财务有值 |
| datas[].items | array | 否 |  | 付款单明细 |
| datas[].items[] | object | 否 |  |  |
| datas[].items[].autoid | number | 否 |  | 付款明细编号 |
| datas[].items[].pay_id | number | 否 |  | 付款单号 |
| datas[].items[].co_id | number | 否 |  | 公司编号 |
| datas[].items[].io_id | number | 否 |  | 来源单号（应付单号，费用单号和预付款单号等） |
| datas[].items[].amount | number | 否 |  | 本次金额 |
| datas[].items[].type | string | 否 |  | 类型 |
| datas[].items[].po_id | number | 否 |  | 采购单号(仅支持“预付冲抵”和“预付款退款”类型的明细返回) |
| datas[].items[].po_ids | string | 否 |  | “应付付款”类型付款单所关联的全部应付单中提取的采购单号集合 |
| datas[].paid_items | array | 否 |  |  |
| datas[].paid_items[] | object | 否 |  | 打款明细，使用新版财务有值 |
| datas[].paid_items[].paid_id | number | 否 |  | 打款明细id |
| datas[].paid_items[].pay_id | number | 否 |  | 付款单号 |
| datas[].paid_items[].type | string | 否 |  | 类型 |
| datas[].paid_items[].paid_account | string | 否 |  | 打款账户 |
| datas[].paid_items[].paid_acount_name | string | 否 |  | 打款账户名称 |
| datas[].paid_items[].paid_serial_number | string | 否 |  | 线上支付流水号 |
| datas[].paid_items[].paid_date | string | 否 |  | 打款时间 |
| datas[].paid_items[].paid_amount | number | 否 |  | 打款金额 |

### 请求示例

```json
{
  "start_time": "2025-04-15",
  "page_index": 1,
  "end_time": "2025-04-16",
  "page_size": 1
}
```


### 响应示例

```json
{
  "pages": 0,
  "datas": [
    {
      "seller": "",
      "pay_date": "",
      "modifier_name": "",
      "ispaid": "",
      "po_id": 0,
      "modifier": 0,
      "remark": "",
      "seller_type": "",
      "modified": "",
      "pay_pro_bank": "",
      "seller_id": 0,
      "amount": 0,
      "creator": 0,
      "paid_status": "",
      "created": "",
      "pay_amount": "",
      "pay_account_name": "",
      "co_id": 0,
      "payway": "",
      "ts": 1,
      "labs": "",
      "paid_items": [
        {
          "paid_acount_name": "",
          "paid_account": "",
          "paid_serial_number": "",
          "paid_id": 0,
          "paid_amount": 0,
          "pay_id": 0,
          "type": "",
          "paid_date": ""
        }
      ],
      "less_amount": 0,
      "creator_name": "",
      "pay_account_number": "",
      "pay_id": 0,
      "items": [
        {
          "amount": 0,
          "po_id": 0,
          "autoid": 0,
          "co_id": 0,
          "pay_id": 0,
          "type": "",
          "io_id": 0
        }
      ],
      "account": "",
      "paid_date": "",
      "status": ""
    }
  ],
  "page_index": 0,
  "count": 0,
  "has_next": true,
  "page_size": 0
}
```


### 异常示例

_无_


---

## 应付单列表查询

`/open/api/fmsopen/querypayable`

| 项 | 内容 |
|---|---|
| 接口名称 | 应付单列表查询 |
| 接口路径 | `/open/api/fmsopen/querypayable` |
| docType / docId | 49 / 1247 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=49&docId=1247 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/fmsopen/querypayable` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/fmsopen/querypayable` |


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
| page_index | number | 是 | 1 | 第几页 |
| page_size | number | 是 | 1 | 显示多少条 |
| start_time | string | 否 | 2025-04-15 | 单据开始时间（与修改时间不能同时为空） |
| end_time | string | 否 | 2025-04-16 | 单据结束时间（与修改时间不能同时为空） |
| type | number | 是 |  | 1查应付 2查期初应付 |
| modified_begin | string | 否 |  | 修改开始时间（与单据时间不能同时为空） |
| modifie_end | string | 否 |  | 修改结束时间（与单据时间不能同时为空） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| page_index | number | 否 |  | 第几页 |
| page_size | number | 否 |  | 多少条 |
| has_next | boolean | 否 |  | 是否有下一页 |
| count | number | 否 |  | 总条数 |
| pages | number | 否 |  | 总页数 |
| datas | array | 否 |  | 应付单数据集合 |
| datas[] | object | 否 |  |  |
| datas[].pinv_id | number | 是 |  | 应付单号 |
| datas[].co_id | number | 是 |  | 公司编号 |
| datas[].inv_type | string | 是 |  | 开票类型 |
| datas[].type | string | 是 |  | 发票类型 |
| datas[].status | string | 是 |  | 状态 |
| datas[].paid_amount | number | 是 |  | 已打款金额 |
| datas[].seller_id | number | 是 |  | 供应商编号 |
| datas[].created | string | 是 |  | 创建时间 |
| datas[].creator | number | 是 |  | 创建人编号 |
| datas[].modified | string | 是 |  | 最后更新时间 |
| datas[].modifier | number | 是 |  | 最后更新人编号 |
| datas[].creator_name | string | 是 |  | 创建人名称 |
| datas[].modifier_name | string | 是 |  | 最后修改人名称 |
| datas[].src_pinv_id | number | 是 |  | 红票对应原始单号 |
| datas[].tax_rate | number | 是 |  | 税率 |
| datas[].payable_type | string | 是 |  | 单据类型 |
| datas[].payable_date | string | 是 |  | 单据日期 |
| datas[].pinv_date | string | 是 |  | 发票日期 |
| datas[].pinv_code | string | 是 |  | 发票代码 |
| datas[].pinv_number | string | 是 |  | 发票号码 |
| datas[].other_amount | number | 是 |  | 其他金额 |
| datas[].inv_amount | number | 是 |  | 应付总额 |
| datas[].remark | string | 是 |  | 备注 |
| datas[].payment_status | string | 是 |  | 结算状态 |
| datas[].total_invoice_amount | number | 是 |  | 总额 |
| datas[].is_adjust_cost | string | 是 |  | 记录成本 |
| datas[].io_id | number | 是 |  | 入库单号 |
| datas[].ts | number | 是 |  | 时间ts |
| datas[].supplier_name | string | 是 |  | 供应商 |
| datas[].fee_amount | number | 是 |  | 费用总额，仅新版应付有值，不计入总额 |
| datas[].items | array | 是 |  | 应付明细 |
| datas[].items[] | object | 否 |  |  |
| datas[].items[].ipinv_id | number | 是 |  | 应付明细单号 |
| datas[].items[].pinv_id | number | 是 |  | 应付单号 |
| datas[].items[].co_id | number | 是 |  | 公司编号 |
| datas[].items[].o_id | number | 是 |  | 采购单号 |
| datas[].items[].io_id | number | 是 |  | 入库单号 |
| datas[].items[].ioi_id | number | 是 |  | 入仓明细ID |
| datas[].items[].sku_id | string | 是 |  | 商品编码 |
| datas[].items[].qty | number | 是 |  | 核销数量 |
| datas[].items[].amount | number | 是 |  | 核销金额(含税) |
| datas[].items[].inv_qty | number | 是 |  | 应付数量 |
| datas[].items[].inv_amount | number | 是 |  | 应付金额（含税） |
| datas[].items[].adjust_amount | number | 是 |  | 调整金额(含税) |
| datas[].free_items | array | 是 |  | 费用明细 |
| datas[].free_items[] | object | 否 |  |  |
| datas[].free_items[].pay_id | number | 是 |  | 应付费用单号 |
| datas[].free_items[].pinv_id | number | 是 |  | 应付单号 |
| datas[].free_items[].amount | number | 是 |  | 费用金额 |
| datas[].free_items[].remark | string | 是 |  | 备注 |
| datas[].free_items[].seller | string | 是 |  | 费用名称 |

### 请求示例

```json
{
  "start_time": "2025-04-15",
  "page_index": 1,
  "end_time": "2025-04-16",
  "type": 0,
  "page_size": 1
}
```


### 响应示例

```json
{
  "pages": 0,
  "datas": [
    {
      "modifier_name": "",
      "modifier": 0,
      "other_amount": 0,
      "remark": "",
      "type": "",
      "tax_rate": 0,
      "total_invoice_amount": 0,
      "payable_date": "",
      "pinv_date": "",
      "pinv_code": "",
      "modified": "",
      "inv_amount": 0,
      "supplier_name": "",
      "inv_type": "",
      "src_pinv_id": 0,
      "seller_id": 0,
      "creator": 0,
      "created": "",
      "payment_status": "",
      "co_id": 0,
      "ts": 1,
      "pinv_number": "",
      "io_id": 0,
      "free_items": [
        {
          "seller": "",
          "pinv_id": 0,
          "amount": 0,
          "remark": "",
          "pay_id": 0
        }
      ],
      "pinv_id": 0,
      "fee_amount": 0,
      "payable_type": "",
      "is_adjust_cost": "",
      "paid_amount": 0,
      "creator_name": "",
      "items": [
        {
          "pinv_id": 0,
          "amount": 0,
          "adjust_amount": 0,
          "ipinv_id": 0,
          "qty": 0,
          "inv_qty": 0,
          "co_id": 0,
          "o_id": 0,
          "sku_id": "",
          "inv_amount": 0,
          "ioi_id": 0,
          "io_id": 0
        }
      ],
      "status": ""
    }
  ],
  "page_index": 0,
  "count": 0,
  "has_next": true,
  "page_size": 0
}
```


### 异常示例

_无_


---

## 【收费】台账数据查询

`/open/webapi/fms/standingbook/getlistbybatch`

| 项 | 内容 |
|---|---|
| 接口名称 | 【收费】台账数据查询 |
| 接口路径 | `/open/webapi/fms/standingbook/getlistbybatch` |
| docType / docId | 49 / 1320 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=49&docId=1320 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/fms/standingbook/getlistbybatch` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/fms/standingbook/getlistbybatch` |


### 接口说明

收费接口如需开通请联系销售/运营沟通
 查询条件
 根据单据时间查询时，单据起始时间和截止时间必须都有值，且限制查询范围不可超过一个月 根据创建时间查询时，创建起始时间和截止时间必须都有值，且限制查询范围不可超过一个月 接口查询时单据时间和创建时间必须传一个 所有时间参数格式为: yyyy-MM-dd 或 yyyy-MM-dd HH:mm:ss 商家未开启批次加权时，不可根据批次号查询 商家未开启分仓加权时，不可根据仓储方查询 数据一致性
 由于台账存在重算场景，所以接口获取数据时理论存在数据一致性的问题，需要关注下；
 台账每日计算任务一般在0点随机分开始执行前一天数据计算，执行总耗时不超过1小时（刚启用台账的商家除外，刚启用商家从期初日期开始按天执行，任务每5分钟执行一次，直至执行到昨日结束）；
 重算任务每5分钟执行一次，24小时执行。

 性能考虑
 建议在非高峰期进行大批量数据获取；
 合理设置查询时间范围，避免单次查询数据量过大。

 速率限制
 开放平台对外接口限制每秒不超过5次请求，每分钟不超过100次请求。

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
| auto_id | number | 是 | 0 | 起始查询主键id |
| bill_begin_time | string | 是 | 2025-06-01 | 单据起始时间 |
| bill_end_time | string | 是 | 2025-06-30 | 单据截止时间 |
| io_ids | array | 否 |  | 进出仓单号集合 |
| io_ids[] | number | 否 |  |  |
| bill_types | array | 否 |  | 单据类型集合 |
| bill_types[] | string | 否 |  |  |
| wms_co_ids | array | 否 |  | 仓储方id集合 |
| wms_co_ids[] | number | 否 |  |  |
| sku_ids | array | 否 |  | 商品编码集合 |
| sku_ids[] | string | 否 |  |  |
| batch_ids | array | 否 |  | 生产批次号集合 |
| batch_ids[] | string | 否 |  |  |
| create_begin_time | string | 否 |  | 创建起始时间 |
| create_end_time | string | 否 |  | 创建截止时间 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].auto_id | number | 否 |  | 主键id |
| data[].bill_date | string | 否 |  | 单据日期 |
| data[].sku_id | string | 否 |  | 商品编码 |
| data[].io_id | number | 否 |  | 进出仓单号 |
| data[].ioi_id | number | 否 |  | 进出仓明细单号 |
| data[].bill_type | string | 否 |  | 单据类型 |
| data[].data_type | string | 否 |  | 出入类型 |
| data[].batch_id | null | 否 |  | 生产批次号 |
| data[].batch_produced_date | null | 否 |  | 生产日期 |
| data[].batch_expiration_date | null | 否 |  | 有效期至 |
| data[].begin_price | null | 否 |  | 期初单价 |
| data[].begin_qty | number | 否 |  | 期初数量 |
| data[].begin_amount | number | 否 |  | 期初金额 |
| data[].inout_price | number | 否 |  | 发生单价 |
| data[].inout_qty | number | 否 |  | 发生数量 |
| data[].inout_amount | number | 否 |  | 发生金额 |
| data[].end_price | number | 否 |  | 期末单价 |
| data[].end_qty | number | 否 |  | 期末数量 |
| data[].end_amount | number | 否 |  | 期末金额 |
| data[].wash_type_name | string | 否 |  | 成本类型 |
| data[].wms_name | string | 否 |  | 仓储方名称 |
| data[].remark | null | 否 |  | 备注 |
| data[].created | string | 否 |  | 创建时间 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "auto_id": 0,
  "wms_co_ids": [],
  "bill_end_time": "2025-06-30",
  "sku_ids": [],
  "bill_types": [],
  "create_begin_time": "",
  "io_ids": [],
  "bill_begin_time": "2025-06-01",
  "create_end_time": "",
  "batch_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": [
    {
      "begin_price": "",
      "bill_date": "",
      "batch_id": "",
      "created": "",
      "end_price": 0,
      "sku_id": "",
      "end_qty": 0,
      "remark": "",
      "begin_amount": 0,
      "batch_expiration_date": "",
      "ioi_id": 0,
      "io_id": 0,
      "auto_id": 0,
      "begin_qty": 0,
      "inout_price": 0,
      "wms_name": "",
      "wash_type_name": "",
      "data_type": "",
      "bill_type": "",
      "batch_produced_date": "",
      "inout_qty": 0,
      "inout_amount": 0,
      "end_amount": 0
    }
  ],
  "request_id": ""
}
```


### 异常示例

_无_


---

## 业务费用列表查询

`/open/api/fmsopen/queryoperatingfee`

| 项 | 内容 |
|---|---|
| 接口名称 | 业务费用列表查询 |
| 接口路径 | `/open/api/fmsopen/queryoperatingfee` |
| docType / docId | 49 / 1414 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=49&docId=1414 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/fmsopen/queryoperatingfee` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/fmsopen/queryoperatingfee` |


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
| page_index | number | 是 | 1 | 页码 |
| page_size | number | 是 | 5 | 每页条数 |
| fee_ids | array | 否 |  | 费用单据id集合 |
| fee_ids[] | string | 否 |  |  |
| bill_begin_date | string | 是 | 2025-07-01 | 单据起始时间 |
| bill_end_date | string | 是 | 2025-10-01 | 单据截止时间 |
| bill_type | array | 否 |  | 单据类型 |
| bill_type[] | string | 否 | 应付业务费用 |  |
| status | array | 否 |  | 状态 |
| status[] | string | 否 | Confirmed |  |
| modified_begin | string | 否 |  | 最后修改时间-开始 |
| modified_end | string | 否 |  | 最后修改时间-结束 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| page_index | number | 否 |  | 页码 |
| page_size | number | 否 |  | 每页条数 |
| has_next | boolean | 否 |  | 是否有下一页 |
| count | number | 否 |  | 总条数 |
| pages | number | 否 |  | 总页数 |
| code | number | 否 |  | 返回编码 |
| is_success | boolean | 否 |  | 是否成功 |
| msg | string | 否 |  | 提示信息 |
| datas | array | 否 |  | 数据集 |
| datas[] | object | 否 |  |  |
| datas[].fee_id | number | 否 |  | 费用单号 |
| datas[].bill_type | string | 否 |  | 单据类型 |
| datas[].fee_date | string | 否 |  | 单据日期 |
| datas[].status | string | 否 |  | 状态 |
| datas[].seller_type | string | 否 |  | 往来单位类型 |
| datas[].seller_id | number | 否 |  | 往来单位id |
| datas[].seller_name | string | 否 |  | 往来单位 |
| datas[].from_bill_type | string | 否 |  | 来源单据类型 |
| datas[].currency | string | 否 |  | 币种 |
| datas[].is_adjust_cost | boolean | 否 |  | 是否记录成本 |
| datas[].remark | string | 否 |  | 备注 |
| datas[].rate | number | 否 |  | 税率 |
| datas[].amount | number | 否 |  | 含税金额 |
| datas[].tax_out_amount | number | 否 |  | 除税金额 |
| datas[].tax_amount | number | 否 |  | 税额 |
| datas[].fee_type_id | number | 否 |  | 费用编码 |
| datas[].fee_type_code | string | 否 |  | 项目编码 |
| datas[].fee_type_name | string | 否 |  | 费用名称 |
| datas[].is_create_payment | boolean | 否 |  | 是否生成付款单 |
| datas[].account | null | 否 |  | 付款账号 |
| datas[].account_name | null | 否 |  | 付款账号名称 |
| datas[].paid_amount | number | 否 |  | 已结算金额 |
| datas[].images | null | 否 |  | 图片 |
| datas[].owner_id | number | 否 |  | 业务员id |
| datas[].owner_name | string | 否 |  | 业务员名称 |
| datas[].is_print | boolean | 否 |  | 是否已打印 |
| datas[].created | string | 否 |  | 创建时间 |
| datas[].creator_name | string | 否 |  | 创建人 |
| datas[].modified | string | 否 |  | 修改时间 |
| datas[].modifier_name | string | 否 |  | 修改人 |
| datas[].wms_co_id | null | 否 |  | 仓储方id |
| datas[].is_init_bill | boolean | 否 |  | 是否初始化单据 |
| datas[].ts | number | 否 |  | 时间ts |
| datas[].items | array | 否 |  | 费用明细集合 |
| datas[].items[] | object | 否 |  |  |
| datas[].items[].fee_id | number | 否 |  | 费用单号 |
| datas[].items[].feeitem_id | number | 否 |  | 费用明细单号 |
| datas[].items[].from_id | number | 否 |  | 来源单号 |
| datas[].items[].p_from_id | number | 否 |  | 来源明细编号 |
| datas[].items[].sku_id | string | 否 |  | 商品编码 |
| datas[].items[].name | string | 否 |  | 商品名称 |
| datas[].items[].properties_value | string | 否 |  | 颜色及规格 |
| datas[].items[].weight | null | 否 |  | 重量 |
| datas[].items[].volume | null | 否 |  | 体积 |
| datas[].items[].qty | number | 否 |  | 数量 |
| datas[].items[].amount | number | 否 |  | 含税金额 |
| datas[].items[].rate_amount | number | 否 |  | 费用金额 |
| datas[].items[].amount_rate_out | null | 否 |  | 调整金额 |

### 请求示例

```json
{
  "page_index": 1,
  "bill_type": [],
  "bill_begin_date": "2025-07-01",
  "fee_ids": [],
  "bill_end_date": "2025-10-01",
  "page_size": 5,
  "status": []
}
```


### 响应示例

```json
{
  "msg": "",
  "pages": 0,
  "code": 0,
  "datas": [
    {
      "tax_amount": 0,
      "modifier_name": "",
      "owner_id": 0,
      "fee_type_id": 0,
      "remark": "",
      "fee_type_name": "",
      "seller_name": "",
      "rate": 0,
      "is_create_payment": true,
      "fee_date": "",
      "from_bill_type": "",
      "account_name": "",
      "seller_type": "",
      "bill_type": "",
      "modified": "",
      "currency": "",
      "is_print": true,
      "seller_id": 0,
      "amount": 0,
      "images": "",
      "owner_name": "",
      "created": "",
      "tax_out_amount": 0,
      "fee_type_code": "",
      "wms_co_id": "",
      "is_adjust_cost": true,
      "is_init_bill": true,
      "fee_id": 0,
      "paid_amount": 0,
      "creator_name": "",
      "items": [
        {
          "amount": 0,
          "amount_rate_out": "",
          "from_id": 0,
          "weight": "",
          "sku_id": "",
          "volume": "",
          "p_from_id": 0,
          "properties_value": "",
          "qty": 0,
          "fee_id": 0,
          "name": "",
          "rate_amount": 0,
          "feeitem_id": 0
        }
      ],
      "account": "",
      "status": "",
      "ts": 0
    }
  ],
  "page_index": 0,
  "count": 0,
  "has_next": true,
  "is_success": true,
  "page_size": 0
}
```


### 异常示例

_无_


---

## 费用项目查询

`/open/api/fmsopen/queryfinanceproject`

| 项 | 内容 |
|---|---|
| 接口名称 | 费用项目查询 |
| 接口路径 | `/open/api/fmsopen/queryfinanceproject` |
| docType / docId | 49 / 1437 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=49&docId=1437 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/fmsopen/queryfinanceproject` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/fmsopen/queryfinanceproject` |


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
| include_children | boolean | 是 | true | 返回结构，true 子项目跟随父项目返回，false 所有项目平铺返回 不传默认子项目跟随父项目返回 |
| enable | boolean | 否 | true | 是否查询启用项目，true查启用，false查禁用，不传查全部 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| page_index | number | 否 |  | 页码 |
| page_size | number | 否 |  | 每页条数 |
| has_next | boolean | 否 |  | 是否有下一页 |
| count | number | 否 |  | 总条数 |
| pages | number | 否 |  | 总页数 |
| code | number | 否 |  | 返回编码 |
| is_success | boolean | 否 |  | 是否成功 |
| msg | string | 否 |  | 提示信息 |
| datas | array | 否 |  | 费用项目 |
| datas[] | object | 否 |  |  |
| datas[].csg_id | number | 是 |  | 项目编号 |
| datas[].pcsg_id | number | 是 |  | 父项目编号 |
| datas[].code | string | 是 |  | 项目编码 |
| datas[].name | string | 是 |  | 项目名称 |
| datas[].remark | string | 是 |  | 备注 |
| datas[].level | number | 是 |  | 层级 |
| datas[].enabled | string | 是 |  | 是否启用 |
| datas[].is_last_level | string | 是 |  | 是否末级 |
| datas[].parent_code | string | 是 |  | 父项目编码 |
| datas[].parent_name | string | 是 |  | 父项目名称 |
| datas[].create_time | string | 是 |  | 创建时间 |
| datas[].children | array | 是 |  | 子节点，请求includeChildren为true或者没传时有值 |
| datas[].children[] | object | 否 |  |  |
| datas[].children[].csg_id | number | 是 |  | 项目编号 |
| datas[].children[].pcsg_id | number | 是 |  | 父项目编号 |
| datas[].children[].code | string | 是 |  | 项目编码 |
| datas[].children[].name | string | 是 |  | 项目名称 |
| datas[].children[].remark | string | 是 |  | 备注 |
| datas[].children[].level | number | 是 |  | 层级 |
| datas[].children[].enabled | string | 是 |  | 是否启用 |
| datas[].children[].is_last_level | string | 是 |  | 是否末级 |
| datas[].children[].parent_code | string | 是 |  | 父项目编码 |
| datas[].children[].parent_name | string | 是 |  | 父项目名称 |
| datas[].children[].create_time | string | 是 |  | 创建时间 |
| datas[].children[].children | array | 是 |  |  |
| datas[].children[].children[] | string | 否 |  |  |
| datas[].children[].labels | null | 是 |  | 标签 |
| datas[].labels | ['array', 'null'] | 是 |  | 标签 |

### 请求示例

```json
{
  "include_children": true,
  "enable": true
}
```


### 响应示例

```json
{
  "msg": "",
  "pages": 0,
  "code": 0,
  "datas": [
    {
      "parent_name": "",
      "code": "",
      "create_time": "",
      "level": 0,
      "remark": "",
      "enabled": "",
      "labels": "",
      "children": [
        {
          "parent_name": "",
          "code": "",
          "create_time": "",
          "level": 0,
          "remark": "",
          "enabled": "",
          "labels": "",
          "children": [],
          "csg_id": 0,
          "name": "",
          "parent_code": "",
          "is_last_level": "",
          "pcsg_id": 0
        }
      ],
      "csg_id": 0,
      "name": "",
      "parent_code": "",
      "is_last_level": "",
      "pcsg_id": 0
    }
  ],
  "page_index": 0,
  "count": 0,
  "has_next": true,
  "is_success": true,
  "page_size": 0
}
```


### 异常示例

_无_


---
