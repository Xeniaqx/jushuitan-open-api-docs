# 聚水潭开放平台 · 聚财快API（线下版）

> 抓取日期：2026-11-23  
> 分类：聚财快API（docType=65）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=65&docId=1639

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 智能会计中心_档案数据_批量保存 | `/open/api/ckopen/sac/archivedata/batchsave` | 1639 | [打开](https://openweb.jushuitan.com/dev-doc?docType=65&docId=1639) |
| 智能会计中心_单据数据_批量保存 | `/open/api/ckopen/sac/notedata/batchsave` | 1640 | [打开](https://openweb.jushuitan.com/dev-doc?docType=65&docId=1640) |

## 目录

- [智能会计中心_档案数据_批量保存](#智能会计中心_档案数据_批量保存)
- [智能会计中心_单据数据_批量保存](#智能会计中心_单据数据_批量保存)

---

## 智能会计中心_档案数据_批量保存

`/open/api/ckopen/sac/archivedata/batchsave`

| 项 | 内容 |
|---|---|
| 接口名称 | 智能会计中心_档案数据_批量保存 |
| 接口路径 | `/open/api/ckopen/sac/archivedata/batchsave` |
| docType / docId | 65 / 1639 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=65&docId=1639 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/ckopen/sac/archivedata/batchsave` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/ckopen/sac/archivedata/batchsave` |


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
| archive_type_code | string | 是 | 001 | 档案类型编码 |
| archive_datas | array | 是 |  | 档案类型数据 |
| archive_datas[] | object | 否 |  |  |
| archive_datas[].source | string | 是 |  | 来源 |
| archive_datas[].source_module_code | string | 是 |  | 来源模块代码 |
| archive_datas[].source_module_name | string | 是 |  | 来源模块标题 |
| archive_datas[].code | string | 是 | 001 | 编码 |
| archive_datas[].name | string | 是 | 红塔山 | 名称 |
| archive_datas[].uom_name | string | 是 | 箱 | 计量单位名称 |
| archive_datas[].json_data | string | 是 | {\"c_id\":\"001\",\"brand\":\"红塔山\",\"vc_name\":\"无\"} | 扩展数据 |
| archive_datas[].use_status | number | 是 | 0 | 使用状态（0可用 1禁用） |
| archive_datas[].data_status | number | 是 | 20 | 数据状态（-10已删除 0新增 10已暂存 20草稿 30流程审批中 40流程已拒绝 50流程已作废 100已审核 200已财审） |
| archive_datas[].remark | string | 是 |  | 备注 |
| archive_datas[].outer_id | string | 是 | 001 | 外部ID |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].id | number | 否 |  | ID |
| data[].code | string | 否 |  | 编码 |
| data[].name | string | 否 |  | 名称 |
| data[].outer_id | string | 否 |  | 外部ID |
| data[].issuccess | boolean | 否 |  | 是否成功 |
| data[].message | string | 否 |  | 失败时退回错误信息 |
| code | number | 否 |  |  |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "archive_datas": [
    {
      "source_module_name": "",
      "code": "001",
      "name": "红塔山",
      "use_status": 0,
      "remark": "",
      "source": "",
      "uom_name": "箱",
      "data_status": 20,
      "outer_id": "001",
      "json_data": "{\\\\\\c_id\\\\\\:\\\\\\001\\\\\\,\\\\\\brand\\\\\\:\\\\\\红塔山\\\\\\,\\\\\\vc_name\\\\\\:\\\\\\无\\\\\\}",
      "source_module_code": ""
    }
  ],
  "archive_type_code": "001"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": [
    {
      "code": "",
      "issuccess": true,
      "name": "",
      "id": 0,
      "message": "",
      "outer_id": ""
    }
  ],
  "request_id": ""
}
```


### 异常示例

_无_


---

## 智能会计中心_单据数据_批量保存

`/open/api/ckopen/sac/notedata/batchsave`

| 项 | 内容 |
|---|---|
| 接口名称 | 智能会计中心_单据数据_批量保存 |
| 接口路径 | `/open/api/ckopen/sac/notedata/batchsave` |
| docType / docId | 65 / 1640 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=65&docId=1640 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/ckopen/sac/notedata/batchsave` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/ckopen/sac/notedata/batchsave` |


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
| note_type_code | string | 是 | 001001001 | 单据类型编码 |
| note_datas | array | 是 |  | 单据数据 |
| note_datas[] | object | 否 |  |  |
| note_datas[].note_no | string | 是 | SPXS-202608-000001 | 单据号 |
| note_datas[].business_date | string | 是 | 2026-08-01 | 业务日期 |
| note_datas[].tag_1 | string | 是 | 打标 | 标签1 |
| note_datas[].tag_2 | string | 是 |  | 标签2 |
| note_datas[].tag_3 | string | 是 |  | 标签3 |
| note_datas[].json_data | string | 是 | {"note_no":"SPXS-202608-000001","date":"2026-08-01","customer_code":"202402000006","customer_name":"烟草公司","warehouse_code":"001","warehouse_name":"一号仓库","department_code":"006001001","department_name":"内贸一组","salesman_code":"8001","salesman_name":"胡晓莉","currency_code":"CNY","currency_name":"人民币","remark":"","tbnote_spxscb":[{"item_no":1,"product_code":"001","product_name":"红塔山","quantity":100,"tax_price":226,"tax_amount":22600,"tax_amount_local":22600,"price":200,"amount":20000,"amount_local":20000,"tax_rate":13,"tax":2600,"tax_local":2600,"cost_price":160,"cost_amount":16000,"remark":""},{"item_no":2,"product_code":"002","product_name":"石林","quantity":80,"tax_price":169.5,"tax_amount":13560,"tax_amount_local":13560,"price":150,"amount":12000,"amount_local":12000,"tax_rate":13,"tax":1560,"tax_local":1560,"cost_price":120,"cost_amount":9600,"remark":""}]} | 单据体数据 |
| note_datas[].data_status | number | 是 | 20 | 数据状态（-10已删除 0新增 10已暂存 20草稿 30流程审批中 40流程已拒绝 50流程已作废 100已审核 200已财审） |
| note_datas[].remark | string | 是 |  |  |
| note_datas[].outer_id | string | 是 | SPXS-202608-000001 | 外部ID |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].issuccess | boolean | 否 |  | 是否成功 |
| data[].note_no | string | 否 |  | 单据号码 |
| data[].message | string | 否 |  | 出错信息 |
| data[].outer_id | string | 否 |  | 外部id |

### 请求示例

```json
{
  "note_type_code": "001001001",
  "note_datas": [
    {
      "note_no": "SPXS-202608-000001",
      "remark": "",
      "business_date": "2026-08-01",
      "tag_1": "打标",
      "data_status": 20,
      "tag_2": "",
      "outer_id": "SPXS-202608-000001",
      "tag_3": "",
      "json_data": "{\\note_no\\:\\SPXS-202608-000001\\,\\date\\:\\2026-08-01\\,\\customer_code\\:\\202402000006\\,\\customer_name\\:\\烟草公司\\,\\warehouse_code\\:\\001\\,\\warehouse_name\\:\\一号仓库\\,\\department_code\\:\\006001001\\,\\department_name\\:\\内贸一组\\,\\salesman_code\\:\\8001\\,\\salesman_name\\:\\胡晓莉\\,\\currency_code\\:\\CNY\\,\\currency_name\\:\\人民币\\,\\remark\\:\\\\,\\tbnote_spxscb\\:[{\\item_no\\:1,\\product_code\\:\\001\\,\\product_name\\:\\红塔山\\,\\quantity\\:100,\\tax_price\\:226,\\tax_amount\\:22600,\\tax_amount_local\\:22600,\\price\\:200,\\amount\\:20000,\\amount_local\\:20000,\\tax_rate\\:13,\\tax\\:2600,\\tax_local\\:2600,\\cost_price\\:160,\\cost_amount\\:16000,\\remark\\:\\\\},{\\item_no\\:2,\\product_code\\:\\002\\,\\product_name\\:\\石林\\,\\quantity\\:80,\\tax_price\\:169.5,\\tax_amount\\:13560,\\tax_amount_local\\:13560,\\price\\:150,\\amount\\:12000,\\amount_local\\:12000,\\tax_rate\\:13,\\tax\\:1560,\\tax_local\\:1560,\\cost_price\\:120,\\cost_amount\\:9600,\\remark\\:\\\\}]}"
    }
  ]
}
```


### 响应示例

```json
{
  "code": 0,
  "data": [
    {
      "issuccess": true,
      "note_no": "",
      "message": "",
      "outer_id": ""
    }
  ],
  "success": true
}
```


### 异常示例

_无_


---
