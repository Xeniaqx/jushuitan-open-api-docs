# 聚水潭开放平台 · 票聚API（线下版）

> 抓取日期：2026-11-23  
> 分类：票聚API（docType=61）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=61&docId=1047

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 【收费】开票结果查询-奇门 | `37zf6iaq2d.jushuitan.shengsuan.invoiceresult.query` | 1047 | [打开](https://openweb.jushuitan.com/dev-doc?docType=61&docId=1047) |
| 修改商品基本开票信息 | `/open/webapi/itemapi/invoice/openimport` | 1197 | [打开](https://openweb.jushuitan.com/dev-doc?docType=61&docId=1197) |
| 【收费】发票回调 | `/open/fms/intranet/invoice/callback` | 1261 | [打开](https://openweb.jushuitan.com/dev-doc?docType=61&docId=1261) |
| 【收费】开票结果查询 | `/open/fms/intranet/queryinvoiceinfoforopen` | 1430 | [打开](https://openweb.jushuitan.com/dev-doc?docType=61&docId=1430) |
| 【收费】导入非订单开票申请 | `/open/fms/general/apply/manual/import` | 1623 | [打开](https://openweb.jushuitan.com/dev-doc?docType=61&docId=1623) |

## 目录

- [【收费】开票结果查询-奇门](#收费开票结果查询-奇门)
- [修改商品基本开票信息](#修改商品基本开票信息)
- [【收费】发票回调](#收费发票回调)
- [【收费】开票结果查询](#收费开票结果查询)
- [【收费】导入非订单开票申请](#收费导入非订单开票申请)

---

## 【收费】开票结果查询-奇门

`37zf6iaq2d.jushuitan.shengsuan.invoiceresult.query`

| 项 | 内容 |
|---|---|
| 接口名称 | 【收费】开票结果查询-奇门 |
| 接口路径 | `37zf6iaq2d.jushuitan.shengsuan.invoiceresult.query` |
| docType / docId | 61 / 1047 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=61&docId=1047 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com37zf6iaq2d.jushuitan.shengsuan.invoiceresult.query` |
| 正式环境 | `https://openapi.jushuitan.com37zf6iaq2d.jushuitan.shengsuan.invoiceresult.query` |


### 接口说明

实际文档参见：https://open.jushuitan.com/document.aspx?doc_id=2376

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

_官方未提供返回字段 schema。_

### 请求示例

```json
{
  "field_1": ""
}
```


### 响应示例

```json
{
  "field_2": ""
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

## 修改商品基本开票信息

`/open/webapi/itemapi/invoice/openimport`

| 项 | 内容 |
|---|---|
| 接口名称 | 修改商品基本开票信息 |
| 接口路径 | `/open/webapi/itemapi/invoice/openimport` |
| docType / docId | 61 / 1197 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=61&docId=1197 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/invoice/openimport` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/invoice/openimport` |


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
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.is_new_add_invoice_type | boolean | 否 | false | 是否新增发票类型 |
| data.error_message | string | 否 | 导入数据有误 | 错误消息 |
| data.finish | boolean | 否 | true | 是否完成 |
| data.success_count | number | 否 | 0 | 成功的数量 |
| data.fail_count | number | 否 | 1 | 失败的数量 |
| data.skip_count | number | 否 | 0 | 跳过的数量（新旧一样无需更新） |
| data.fail_datas | array | 否 |  | 失败明细 |
| data.fail_datas[] | object | 否 |  |  |
| data.fail_datas[].sku_id | string | 否 | #001 | 商品编码 |
| data.fail_datas[].error_type | string | 否 | 错误 | 失败类型 |
| data.fail_datas[].error_message | string | 否 | 开票基本售价非有效数字 | 失败信息 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
[
  {
    "qty_str": "1",
    "tax_rate_zero_str": "",
    "tax_code": "税务编码1",
    "tax_code_short": "税务编码简称1",
    "sale_price_str": "aaa",
    "name": "开票名称1",
    "issuing_office": "开票单位1",
    "sku_id": "#001",
    "type": "开票分类1",
    "spec": "开票规格1",
    "tax_rate_str": "0.1"
  }
]
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "error_message": "导入数据有误",
    "fail_datas": [
      {
        "error_message": "开票基本售价非有效数字",
        "error_type": "错误",
        "sku_id": "#001"
      }
    ],
    "is_new_add_invoice_type": false,
    "success_count": 0,
    "finish": true,
    "skip_count": 0,
    "fail_count": 1
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 【收费】发票回调

`/open/fms/intranet/invoice/callback`

| 项 | 内容 |
|---|---|
| 接口名称 | 【收费】发票回调 |
| 接口路径 | `/open/fms/intranet/invoice/callback` |
| docType / docId | 61 / 1261 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=61&docId=1261 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/fms/intranet/invoice/callback` |
| 正式环境 | `https://openapi.jushuitan.com/open/fms/intranet/invoice/callback` |


### 接口说明

收费接口如需开通请联系销售/运营沟通

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
| invoice_id | string | 是 |  | 发票流水号 |
| status | number | 是 |  | 发票状态 0 失败 1 成功 |
| invoice_no | string | 否 |  | 发票号码 |
| pdf_url | string | 否 |  | 发票pdfUrl |
| ofd_url | string | 否 |  | 发票ofdUrl |
| xml)url | string | 否 |  | 发票xmlUrl |
| shout_url | string | 否 |  | 发票shoutUrl |
| invoiced | string | 否 |  | 开票日期yyyy-MM-dd HH:mm:ss |
| fail_msg | string | 否 |  | 失败原因 |
| tax_number | string | 否 |  | 销方税号 |
| drawer | string | 否 |  | 开票人 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| msg | string | 否 |  |  |
| data | object | 否 |  |  |
| code | number | 否 |  |  |

### 请求示例

```json
{
  "invoiced": "",
  "invoice_no": "",
  "invoice_id": "",
  "pdf_url": "",
  "xml_url": "",
  "ofd_url": "",
  "status": "",
  "fail_msg": ""
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

## 【收费】开票结果查询

`/open/fms/intranet/queryinvoiceinfoforopen`

| 项 | 内容 |
|---|---|
| 接口名称 | 【收费】开票结果查询 |
| 接口路径 | `/open/fms/intranet/queryinvoiceinfoforopen` |
| docType / docId | 61 / 1430 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=61&docId=1430 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/fms/intranet/queryinvoiceinfoforopen` |
| 正式环境 | `https://openapi.jushuitan.com/open/fms/intranet/queryinvoiceinfoforopen` |


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
| create_begin_date | string | 否 |  | 发票创建时间-开始（格式 yyyy-MM-dd HH:mm:ss） |
| create_end_date | string | 否 |  | 发票创建时间-结束（格式 yyyy-MM-dd HH:mm:ss） |
| direct | string | 否 |  | 开票类型（蓝票 "BLUE" 红票 "RED"） |
| invoice_begin_date | string | 否 |  | 发票开票时间-开始（格式 yyyy-MM-dd HH:mm:ss） |
| invoice_end_date | string | 否 |  | 发票开票时间-结束（格式 yyyy-MM-dd HH:mm:ss） |
| so_ids | array | 否 |  | 订单号列表 |
| so_ids[] | string | 否 |  |  |
| invoice_ids | string | 否 |  | 发票流水号 |
| status_list | array | 否 |  | 状态（TO_INVOICE("TO_INVOICE", "待开票"), REPAIRING("REPAIRING", "修复中"), INVOICING("INVOICING", "开票中"), WAITING("WAITING", "等待中"), INVOICED("INVOICED", "开票成功"), INVOICE_REFUSE("INVOICE_REFUSE", "已打回"), INVOICE_FAIL("INVOICE_FAIL", "开票失败")） |
| status_list[] | string | 否 |  |  |
| page_num | string | 否 |  | 页码 |
| page_size | string | 否 |  | 数量 |
| type | string | 否 |  | 发票类型（"QD_COMMON", "全电普通发票" "QD_SPECIAL", "全电增值税专票"） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].bill_no | string | 否 |  | 发票单据号 |
| data[].so_ids | string | 否 |  | 线上订单号 |
| data[].status | string | 否 |  | 开票状态（TO_INVOICE, "待开票" SUBMITTED, "已提交开票" INVOICING, "开票中" INVOICED, "开票成功" INVOICE_FAIL, "开票失败"） |
| data[].direct | string | 否 |  | 开票类型（BLUE, "蓝票" RED, "红票"） |
| data[].total_amount | string | 否 |  | 开票金额(含税) |
| data[].tax_amount | string | 否 |  | 税额 |
| data[].amount | string | 否 |  | 去税金额 |
| data[].buyer_title_type | string | 否 |  | 抬头类型（ PERSON, "个人" ENTERPRISE, "单位"） |
| data[].type | string | 否 |  | 发票类型（QD_COMMON, "全电普通发票" QD_SPECIAL, "全电增值税专票"） |
| data[].seller_name | string | 否 |  | 销方开票主体 |
| data[].seller_tax_no | string | 否 |  | 销方纳税人识别号 |
| data[].seller_bank_account | string | 否 |  | 销方银行账号 |
| data[].seller_bank | string | 否 |  | 销方开户行 |
| data[].seller_address | string | 否 |  | 销方地址 |
| data[].seller_phone | string | 否 |  | 销方电话 |
| data[].buyer_title | string | 否 |  | 购方抬头名称 |
| data[].buyer_tax_no | string | 否 |  | 购方纳税人识别号 |
| data[].buyer_bank | string | 否 |  | 购方开户银行 |
| data[].buyer_account | string | 否 |  | 购方开户银行账户 |
| data[].buyer_phone | string | 否 |  | 购方电话 |
| data[].buyer_address | string | 否 |  | 购方地址 |
| data[].comment | string | 否 |  | 发票备注 |
| data[].invoice_no | string | 否 |  | 发票号码 |
| data[].xmlUrl | string | 否 |  | xml文件链接 |
| data[].pdfUrl | string | 否 |  | pdf文件链接 |
| data[].ofdUrl | string | 否 |  | ofd文件链接 |
| data[].shortUrl | string | 否 |  | 交付链接 |
| data[].original_blue_invoice_no | string | 否 |  |  |
| data[].id | string | 否 |  |  |
| data[].shop_name | string | 否 |  | 店铺 |
| data[].shop_id | string | 否 |  | 店铺id |
| data[].drp_name | string | 否 |  | 分销商 |
| data[].drp_id | string | 否 |  | 分销商编码 |
| data[].cus_id | string | 否 |  | 客户编码 |
| data[].invoiced | string | 否 |  | 开票时间 |
| data[].created | string | 否 |  | 创建时间 |
| data[].updated | string | 否 |  | 修改时间 |
| data[].fail_reason | string | 否 |  | 开票失败原因 |
| data[].wait_reason | string | 否 |  | 开票等待原因 |
| data[].cancel_reason | string | 否 |  | 打回原因 |
| data[].red_status | boolean | 否 |  | 蓝票红冲状态（true=已红冲， false/null=未红冲） |
| data[].invoice_details | array | 否 |  | 发票明细 |
| data[].invoice_details[] | object | 否 |  |  |
| data[].invoice_details[].line_type | string | 是 |  | 行类型（NORMAL, "正常行" DISCOUNT "折扣行" WITH_DISCOUNT "被折扣行"） |
| data[].invoice_details[].item_type | string | 是 |  | 明细类型，固定为0 |
| data[].invoice_details[].sku_id | string | 是 |  | 商品编码 |
| data[].invoice_details[].sku_name | string | 是 |  | 开票名称 |
| data[].invoice_details[].sku_tax_code | string | 是 |  | 商品税务编码 |
| data[].invoice_details[].sku_tax_text | string | 是 |  | 商品税务编码简称 |
| data[].invoice_details[].specs | string | 是 |  | 规格 |
| data[].invoice_details[].unit | string | 是 |  | 单位 |
| data[].invoice_details[].price | string | 是 |  | 单价 |
| data[].invoice_details[].tax_flag | boolean | 是 |  | 单价是否含税 |
| data[].invoice_details[].sku_tax_rate | string | 是 |  | 税率 |
| data[].invoice_details[].duty_free | string | 是 |  | 税率标识(NORMAL_TAX_RATE "正常税率" DUTY "免税" NO_TAX "不征税" ZERO_TAX_RATE "普通零税率") |
| data[].invoice_details[].qty | string | 是 |  | 开票数量 |
| data[].invoice_details[].total_amount | string | 是 |  | 开票金额(含税) |
| data[].invoice_details[].tax_amount | string | 是 |  | 税额 |
| data[].invoice_details[].amount | string | 是 |  | 开票金额(除税) |
| data[].invoice_details[].so_id | string | 是 |  | 商品原始线上订单号 |
| data[].invoice_details[].oi_id | string | 是 |  | 内部订单号 |
| data[].invoice_details[].id | string | 是 |  | 明细id |
| data[].original_invoice_details | array | 否 |  | 原始发票明细 |
| data[].original_invoice_details[] | object | 否 |  |  |
| data[].original_invoice_details[].line_type | string | 是 |  | 明细类型，固定为0 |
| data[].original_invoice_details[].item_type | string | 是 |  | 行类型（NORMAL, "正常行" DISCOUNT "折扣行" WITH_DISCOUNT "被折扣行"） |
| data[].original_invoice_details[].sku_id | string | 是 |  | 商品编码 |
| data[].original_invoice_details[].sku_name | string | 是 |  | 开票名称 |
| data[].original_invoice_details[].sku_tax_code | string | 是 |  | 商品税务编码 |
| data[].original_invoice_details[].sku_tax_text | string | 是 |  | 商品税务编码简称 |
| data[].original_invoice_details[].specs | string | 是 |  | 规格 |
| data[].original_invoice_details[].unit | string | 是 |  | 单位 |
| data[].original_invoice_details[].price | string | 是 |  | 单价 |
| data[].original_invoice_details[].tax_flag | boolean | 是 |  | 单价是否含税 |
| data[].original_invoice_details[].sku_tax_rate | string | 是 |  | 税率 |
| data[].original_invoice_details[].duty_free | string | 是 |  | 税率标识（NORMAL_TAX_RATE "正常税率" DUTY "免税" NO_TAX "不征税" ZERO_TAX_RATE "普通零税率"） |
| data[].original_invoice_details[].qty | string | 是 |  | 开票数量 |
| data[].original_invoice_details[].total_amount | string | 是 |  | 开票金额(含税) |
| data[].original_invoice_details[].tax_amount | string | 是 |  | 税额 |
| data[].original_invoice_details[].amount | string | 是 |  | 开票金额(除税) |
| data[].original_invoice_details[].so_id | string | 是 |  | 商品原始线上订单号 |
| data[].original_invoice_details[].oi_id | string | 是 |  | 内部订单号 |
| data[].original_invoice_details[].id | string | 是 |  | 明细id |
| msg | null | 否 |  |  |
| code | number | 否 |  |  |
| request_id | string | 否 |  |  |

### 请求示例

```json
{
  "create_begin_date": "",
  "invoice_end_date": "",
  "so_ids": [],
  "create_end_date": "",
  "invoice_ids": "",
  "status_list": [],
  "direct": "",
  "page_num": "",
  "invoice_begin_date": "",
  "type": "",
  "page_size": ""
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": [
    {
      "tax_amount": "",
      "drp_name": "",
      "original_blue_invoice_no": "",
      "shortUrl": "",
      "drp_id": "",
      "red_status": true,
      "direct": "",
      "bill_no": "",
      "type": "",
      "buyer_title": "",
      "cus_id": "",
      "buyer_bank": "",
      "pdfUrl": "",
      "so_ids": "",
      "seller_name": "",
      "buyer_tax_no": "",
      "seller_phone": "",
      "id": "",
      "seller_bank_account": "",
      "original_invoice_details": [
        {
          "tax_amount": "",
          "sku_tax_rate": "",
          "amount": "",
          "item_type": "",
          "duty_free": "",
          "sku_id": "",
          "oi_id": "",
          "sku_tax_code": "",
          "specs": "",
          "unit": "",
          "tax_flag": true,
          "total_amount": "",
          "sku_tax_text": "",
          "price": "",
          "so_id": "",
          "line_type": "",
          "qty": "",
          "sku_name": "",
          "id": ""
        }
      ],
      "amount": "",
      "buyer_address": "",
      "invoice_details": [
        {
          "tax_amount": "",
          "sku_tax_rate": "",
          "amount": "",
          "item_type": "",
          "duty_free": "",
          "sku_id": "",
          "oi_id": "",
          "sku_tax_code": "",
          "specs": "",
          "unit": "",
          "tax_flag": true,
          "total_amount": "",
          "sku_tax_text": "",
          "price": "",
          "so_id": "",
          "line_type": "",
          "qty": "",
          "sku_name": "",
          "id": ""
        }
      ],
      "invoiced": "",
      "buyer_title_type": "",
      "seller_bank": "",
      "buyer_account": "",
      "created": "",
      "invoice_no": "",
      "buyer_phone": "",
      "shop_name": "",
      "seller_address": "",
      "xmlUrl": "",
      "shop_id": "",
      "cancel_reason": "",
      "ofdUrl": "",
      "total_amount": "",
      "seller_tax_no": "",
      "comment": "",
      "fail_reason": "",
      "wait_reason": "",
      "updated": "",
      "status": ""
    }
  ],
  "request_id": ""
}
```


### 异常示例

_无_


---

## 【收费】导入非订单开票申请

`/open/fms/general/apply/manual/import`

| 项 | 内容 |
|---|---|
| 接口名称 | 【收费】导入非订单开票申请 |
| 接口路径 | `/open/fms/general/apply/manual/import` |
| docType / docId | 61 / 1623 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=61&docId=1623 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/fms/general/apply/manual/import` |
| 正式环境 | `https://openapi.jushuitan.com/open/fms/general/apply/manual/import` |


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
| act | string | 是 |  |  |
| data | object | 是 |  |  |

### 请求示例

```json
[
  {
    "address": "",
    "remark": "",
    "title": "",
    "title_type": "",
    "bank": "",
    "tax_no": "",
    "seller_tax_no": "",
    "phone": "",
    "apply_remark": "",
    "o_id": "",
    "invoice_type": "",
    "details": [
      {
        "specs": "",
        "tax_code": "",
        "unit": "",
        "total_amount": "",
        "discount_amount": "",
        "qty": "",
        "duty_free": "",
        "sku_id": "",
        "sku_name": "",
        "tax_rate": ""
      }
    ],
    "need_agree": 0,
    "account": "",
    "email": ""
  }
]
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "act": "",
  "data": ""
}
```


### 异常示例

_无_


---
