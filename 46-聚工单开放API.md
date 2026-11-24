# 聚水潭开放平台 · 聚工单开放API（线下版）

> 抓取日期：2026-11-23  
> 分类：聚工单开放API（docType=46）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=46&docId=1011

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 【收费】更新工单数据 | `/open/api/gd/open/workorder/updateworkorder` | 1011 | [打开](https://openweb.jushuitan.com/dev-doc?docType=46&docId=1011) |
| 【收费】添加工单数据 | `/open/api/gd/open/workorder/addworkorder` | 1127 | [打开](https://openweb.jushuitan.com/dev-doc?docType=46&docId=1127) |
| 【收费】查询所有工单类型列表 | `/open/api/gd/open/workordertype/queryallworkordertype` | 1130 | [打开](https://openweb.jushuitan.com/dev-doc?docType=46&docId=1130) |

## 目录

- [【收费】更新工单数据](#收费更新工单数据)
- [【收费】添加工单数据](#收费添加工单数据)
- [【收费】查询所有工单类型列表](#收费查询所有工单类型列表)

---

## 【收费】更新工单数据

`/open/api/gd/open/workorder/updateworkorder`

| 项 | 内容 |
|---|---|
| 接口名称 | 【收费】更新工单数据 |
| 接口路径 | `/open/api/gd/open/workorder/updateworkorder` |
| docType / docId | 46 / 1011 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=46&docId=1011 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/gd/open/workorder/updateworkorder` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/gd/open/workorder/updateworkorder` |


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
| data | object | 是 |  |  |
| data.wo_no | string | 是 | GD238394 | 工单号 |
| data.operate_type | string | 否 |  | 暂时支持操作（COMPLETE:完成工单,CANCEL:取消工单,CONFIRMING:标处理中,WAIT_CONFIRM:标待处理,REJECT_AUDIT:拒绝审核） |
| data.business_field_list | array | 是 |  |  |
| data.business_field_list[] | object | 否 |  |  |
| data.business_field_list[].field_id | string | 是 | attachmentField |  |
| data.business_field_list[].value_list | array | 是 |  |  |
| data.business_field_list[].value_list[] | string | 否 | https://dingdingimg.erp321.com/gd/imageC4D8E4C8B75140C9BF38AED6F6364A70.png |  |
| data.business_field_list[].value | string | 否 |  |  |
| data.business_field_list[].child_field_list | array | 否 |  | 表格字段信息 1. 商品信息每行数据任意一行包含参数erpItemId，会根据erpItemId参数更新 2. 商品信息所有行不传入erpItemId按行顺序更新 |
| data.business_field_list[].child_field_list[] | array | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| request_id | string | 否 |  |  |
| msg | string | 否 |  |  |
| data | object | 否 |  |  |
| data.data | null | 否 |  |  |
| data.page | null | 否 |  |  |
| data.now | number | 否 |  |  |

### 请求示例

```json
{
  "wo_no": "GD238394",
  "operate_type": "",
  "business_field_list": [
    {
      "field_id": "attachmentField",
      "value_list": [
        "https://dingdingimg.erp321.com/gd/imageC4D8E4C8B75140C9BF38AED6F6364A70.png"
      ]
    },
    {
      "field_id": "asid",
      "value": "123456"
    },
    {
      "field_id": "itemInfo",
      "child_field_list": [
        [
          {
            "field_id": "customSelectCascade1",
            "value_list": [
              "测试111",
              "测试2测试2",
              "测试3"
            ]
          }
        ]
      ]
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "trace_id": "",
  "code": 0,
  "data": {
    "data": "",
    "now": 0,
    "page": ""
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 【收费】添加工单数据

`/open/api/gd/open/workorder/addworkorder`

| 项 | 内容 |
|---|---|
| 接口名称 | 【收费】添加工单数据 |
| 接口路径 | `/open/api/gd/open/workorder/addworkorder` |
| docType / docId | 46 / 1127 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=46&docId=1127 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/gd/open/workorder/addworkorder` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/gd/open/workorder/addworkorder` |


### 接口说明

收费接口如需开通请联系销售/运营沟通
 business_field_list传值说明:

 基础字段映射：
 字段id 类型 title TEXT content TEXT beginTime DATE endTime DATE grade TEXT

 字段类型 传值字段 格式 TEXT/POPUP/SELECT/TEXTAREA value 字符串 MONEY/NUMBER value 浮点数(精确到小数点后2位) SELECT_MULTIPLE valueList 字符串 DATE/TIME value yyyy-MM-dd HH:mm:ss SELECT_CASCADE valueList List长度为3,第一个为第一级,第二个为第二级,第三个为第三级 FILE_UPLOAD valueList 每个附件的文件地址,必须为可访问的全路径(如:https://xxxx.com/ttt/ssss.png)

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
| data | object | 是 |  | 参数 |
| data.wo_type_id | string | 是 | DE4D184C511548EF9EA39F875CD1E48A | 工单类型ID |
| data.business_field_list | array | 是 |  | 业务字段列表 |
| data.business_field_list[] | object | 否 |  | 业务字段 |
| data.business_field_list[].field_id | string | 是 | actualPaidAmountField | 字段ID |
| data.business_field_list[].value | string | 是 | 123 | 业务字段值(字段类型为文本/日期/金额/数字/单选类型需将待修改的值传到该字段) |
| data.business_field_list[].value_list | array | 是 |  | 业务字段值(字段类型为多选/级联/上传附件类型需将待修改的值传到该字段) |
| data.business_field_list[].value_list[] | string | 否 |  | 字段值 |
| data.business_field_list[].receiver_value | object | 否 |  | 地址类信息 |
| data.business_field_list[].receiver_value.province | string | 是 |  | 省 |
| data.business_field_list[].receiver_value.city | string | 是 |  | 市 |
| data.business_field_list[].receiver_value.district | string | 是 |  | 区 |
| data.business_field_list[].receiver_value.address | string | 是 |  | 详细地址 |
| data.business_field_list[].receiver_value.phone | string | 否 |  | 联系电话 |
| data.business_field_list[].receiver_value.name | string | 否 |  | 联系人名字 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 状态码 0:成功,其他失败 |
| request_id | string | 否 |  | request_id |
| msg | string | 否 |  | 提示语 |
| data | object | 否 |  | 返回数据 |
| data.data | object | 否 |  | 返回 |
| data.data.wo_no | string | 否 |  | 创建的工单号 |

### 请求示例

```json
{
  "data": {
    "business_field_list": [
      {
        "field_id": "actualPaidAmountField",
        "value_list": [],
        "value": "123"
      }
    ],
    "wo_type_id": "DE4D184C511548EF9EA39F875CD1E48A"
  }
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "data": {
      "wo_no": ""
    }
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 【收费】查询所有工单类型列表

`/open/api/gd/open/workordertype/queryallworkordertype`

| 项 | 内容 |
|---|---|
| 接口名称 | 【收费】查询所有工单类型列表 |
| 接口路径 | `/open/api/gd/open/workordertype/queryallworkordertype` |
| docType / docId | 46 / 1130 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=46&docId=1130 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/gd/open/workordertype/queryallworkordertype` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/gd/open/workordertype/queryallworkordertype` |


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

_官方未提供请求字段 schema。_

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 状态码 0:成功,其他：失败 |
| request_id | string | 否 |  |  |
| msg | string | 否 |  | 提示语 |
| data | object | 否 |  | 数据 |
| data.data | array | 否 |  | 数据 |
| data.data[] | object | 否 |  | 工单类型列表 |
| data.data[].id | string | 否 |  | 工单类型ID |
| data.data[].name | string | 否 |  | 工单类型名字 |
| data.data[].description | string | 否 |  | 工单类型描述 |
| data.data[].sub_category | null | 否 |  | 工单类型子类型 |
| data.data[].business_field_list | array | 否 |  | 业务字段 |
| data.data[].business_field_list[] | object | 否 |  | 业务字段 |
| data.data[].business_field_list[].field_id | string | 是 |  | 字段ID |
| data.data[].business_field_list[].label | string | 是 |  | 字段名字 |
| data.data[].business_field_list[].type | string | 是 |  | 字段类型 |
| data.data[].business_field_list[].child_field_list | array | 是 |  | 子业务字段 |
| data.data[].business_field_list[].child_field_list[] | object | 否 |  | 子业务字段 |
| data.data[].business_field_list[].child_field_list[].field_id | string | 是 |  | 字段ID |
| data.data[].business_field_list[].child_field_list[].label | string | 是 |  | 字段名字 |
| data.data[].business_field_list[].child_field_list[].type | string | 是 |  | 字段类型 |
| data.data[].business_field_list[].child_field_list[].child_field_list | null | 是 |  |  |
| data.page | null | 否 |  |  |
| data.now | number | 否 |  |  |

### 请求示例

```json
{}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "data": [
      {
        "business_field_list": [
          {
            "field_id": "",
            "label": "",
            "type": "",
            "child_field_list": [
              {
                "field_id": "",
                "label": "",
                "type": "",
                "child_field_list": ""
              }
            ]
          }
        ],
        "sub_category": "",
        "name": "",
        "description": "",
        "id": ""
      }
    ],
    "now": 0,
    "page": ""
  },
  "request_id": ""
}
```


### 异常示例

_无_


---
