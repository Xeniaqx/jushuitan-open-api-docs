# 聚水潭开放平台 · 跨境API（线下版）

> 抓取日期：2026-11-23  
> 分类：跨境API（docType=44）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=44&docId=1144

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 获取用户启用的物流列表及渠道 | `/open/webapi/cblogisticsapi/cbchannels/getuseropenlogisticsinfo` | 1144 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=1144) |
| 查询商品报关信息 | `/open/webapi/cb/cbitem/getdeclares` | 1207 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=1207) |
| 查询调拨单头程费用 | `/open/webapi/wmsapi/allocate/loadallocatefeev2` | 1280 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=1280) |
| 跨境售后单查询 | `/open/webapi/cb/cborder/getrefunds` | 1110 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=1110) |
| 送仓包裹返回仓 | `/open/webapi/cbdtwapi/cbdtw/getpackageinfo` | 1426 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=1426) |
| 尾程运费回写接口 | `/open/webapi/cblogisticsapi/cbexpressstatement/savefee` | 489 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=489) |
| 1688商品映射推送 | `/open/webapi/globalapi/skumap/mapping` | 502 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=502) |
| 更新订单跨境物流信息 | `/open/jushuitan/crossborder/forwarder/upload` | 71 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=71) |
| 创建头程单 | `/open/webapi/cb/cbfirsttrip/createfirsttrip` | 891 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=891) |
| 跨境订单查询 | `/open/webapi/cb/cborder/getorders` | 1109 | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=1109) |

## 目录

- [获取用户启用的物流列表及渠道](#获取用户启用的物流列表及渠道)
- [查询商品报关信息](#查询商品报关信息)
- [查询调拨单头程费用](#查询调拨单头程费用)
- [跨境售后单查询](#跨境售后单查询)
- [送仓包裹返回仓](#送仓包裹返回仓)
- [尾程运费回写接口](#尾程运费回写接口)
- [1688商品映射推送](#1688商品映射推送)
- [更新订单跨境物流信息](#更新订单跨境物流信息)
- [创建头程单](#创建头程单)
- [跨境订单查询](#跨境订单查询)

---

## 获取用户启用的物流列表及渠道

`/open/webapi/cblogisticsapi/cbchannels/getuseropenlogisticsinfo`

| 项 | 内容 |
|---|---|
| 接口名称 | 获取用户启用的物流列表及渠道 |
| 接口路径 | `/open/webapi/cblogisticsapi/cbchannels/getuseropenlogisticsinfo` |
| docType / docId | 44 / 1144 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=1144 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/cblogisticsapi/cbchannels/getuseropenlogisticsinfo` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/cblogisticsapi/cbchannels/getuseropenlogisticsinfo` |


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
| code | number | 否 |  | 响应码 |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].delivery_id | number | 是 |  | 物流商Id |
| data[].delivery_name | string | 是 |  | 物流商名称 |
| data[].original_delivery_code | string | 是 |  | 原始物流商code |
| data[].original_delivery_name | string | 是 |  | 原始物流商名称 |
| data[].open_channels | array | 是 |  | 启用渠道列表 |
| data[].open_channels[] | object | 否 |  |  |
| data[].open_channels[].channel_name | string | 是 |  | 渠道名称 |
| data[].open_channels[].channel_code | string | 是 |  | 渠道Code |
| data[].open_channels[].shorter_name | string | 是 |  | 自定义名称 |
| data[].open_channels[].sorting_code | string | 是 |  | 分拣码 |
| data[].open_channels[].channel_mappings | array | 是 |  | 渠道映射 |
| data[].open_channels[].channel_mappings[] | object | 否 |  |  |
| data[].open_channels[].channel_mappings[].plat_type | string | 是 |  | 店铺类型 |
| data[].open_channels[].channel_mappings[].plat_name | string | 是 |  | 店铺类型名称 |
| data[].open_channels[].channel_mappings[].plat_channel_code | string | 是 |  | 映射Code |
| data[].open_channels[].channel_mappings[].plat_channel_name_cn | string | 是 |  | 中文名称 |
| data[].open_channels[].channel_mappings[].plat_channel_name_en | string | 是 |  | 英文名称 |
| data[].open_channels[].channel_mappings[].tracking_url | string | 是 |  | 追踪Url |
| msg | null | 否 |  | 异常描述 |
| request_id | null | 否 |  |  |

### 请求示例

```json
{}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": [
    {
      "delivery_name": "",
      "delivery_id": 0,
      "open_channels": [
        {
          "channel_name": "",
          "channel_mappings": [
            {
              "plat_type": "",
              "plat_channel_code": "",
              "plat_name": "",
              "plat_channel_name_en": "",
              "tracking_url": "",
              "plat_channel_name_cn": ""
            }
          ],
          "shorter_name": "",
          "sorting_code": "",
          "channel_code": ""
        }
      ]
    }
  ],
  "request_id": ""
}
```


### 异常示例

_无_


---

## 查询商品报关信息

`/open/webapi/cb/cbitem/getdeclares`

| 项 | 内容 |
|---|---|
| 接口名称 | 查询商品报关信息 |
| 接口路径 | `/open/webapi/cb/cbitem/getdeclares` |
| docType / docId | 44 / 1207 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=1207 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/cb/cbitem/getdeclares` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/cb/cbitem/getdeclares` |


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
| sku_ids | array | 否 |  | 商品编码列表，最大20个 |
| sku_ids[] | string | 否 |  |  |
| modified_begin | string | 否 |  | 修改开始时间 |
| modified_end | string | 否 |  | 修改结束时间。时间间隔不能超过7天 |
| page_size | number | 否 |  | 每页多少条，默认20，最大50 |
| page_index | number | 否 |  | 第几页，从第一页开始，默认1 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.page_index | number | 是 | 1 | 第几页 |
| data.page_size | number | 是 | 20 | 每页多少条 |
| data.data_count | number | 是 | 200 | 总数量 |
| data.page_count | number | 是 | 10 | 总共多少页 |
| data.has_next | boolean | 是 | true | 是否有下一页 |
| data.data | array | 是 |  | 数据 |
| data.data[] | object | 否 |  |  |
| data.data[].i_id | string | 是 | AAA | 款式编码 |
| data.data[].sku_id | string | 是 | AAA-01 | 商品编码 |
| data.data[].declare_name_z_n | string | 是 | hat | 商品名称英文 |
| data.data[].declare_name_e_n | string | 是 | 帽子 | 商品名称中文 |
| data.data[].declare_amount | number | 是 | 30 | 报关金额 |
| data.data[].is_get_price | boolean | 是 | false | 是否取商品实际售价，true取实际售价，false取declareAmount |
| data.data[].declare_weight | number | 是 | 0.3 | 报关重量 |
| data.data[].is_get_weight | boolean | 是 | false | 是否取商品重量，true取商品重量，false取declareWeight |
| data.data[].hs_code | string | 是 | 7606929900 | 海关编码 |
| data.data[].post_tax_num | string | 是 | 000031000000001 | 行政税号 |
| data.data[].unit1 | string | 是 | 件 | 第一计量单位 |
| data.data[].unit2 | string | 是 | 套 | 第二计量单位 |
| data.data[].is_liquid | boolean | 是 | false | 含非液体化妆品 |
| data.data[].is_battery | boolean | 是 | false | 含电池 |
| data.data[].is_paste | boolean | 是 | false | 膏体 |
| data.data[].is_powder | boolean | 是 | false | 粉末 |
| data.data[].is_magnetic | boolean | 是 | false | 带磁 |
| data.data[].is_fluid | boolean | 是 | false | 液体 |
| data.data[].is_special_cargo | boolean | 是 | false | 特货 |
| data.data[].other_attr | object | 是 |  | 其他属性 |
| data.data[].other_attr.declarematerial | string | 是 | 棉 | 材质 |
| data.data[].other_attr.declareuse | string | 是 | 防寒保暖 | 用途 |
| data.data[].other_attr.origin_country | string | 是 | US | 原产国 |
| data.data[].other_attr.cpsccertifierid | string | 是 |  | 进口商识别码(CPSC) |
| data.data[].other_attr.cpscproductid | string | 是 |  | 产品识别码(CPSC) |
| data.data[].other_attr.cpscversionid | string | 是 |  | 证书版本标识(CPSC) |
| data.data[].other_attr.cpscintendedusecode | string | 是 |  | 用途代码(CPSC) |
| data.data[].other_attr.domesticsource | string | 是 |  | 境内货源地 |
| data.data[].other_attr.declarematerialen | string | 是 |  | 英文材质 |
| data.data[].other_attr.declareuseen | string | 是 |  | 英文用途 |
| data.data[].other_attr.declareelement | string | 是 |  | 申报要素 |
| data.data[].other_attr.formaldeclarenamecn | string | 是 |  | 正式报关中文名 |
| data.data[].other_attr.formaldeclaremodel | string | 是 |  | 正式报关型号 |
| data.data[].other_attr.productcompany | string | 是 |  | 生产销售单位 |
| data.data[].other_attr.productcompanycode | string | 是 |  | 生产销售单位18位代码 |
| data.data[].other_attr.attrinfos | array | 是 |  | 阿里巴巴国际站专用属性 |
| data.data[].other_attr.attrinfos[] | object | 否 |  |  |
| data.data[].other_attr.attrinfos[].name | string | 是 | 粉末 | 属性名称 |
| data.data[].other_attr.attrinfos[].code | string | 是 | stive | 属性编码 |
| data.data[].other_attr.attrinfos[].childrens | array | 是 |  | 子数量列表 |
| data.data[].other_attr.attrinfos[].childrens[] | object | 否 |  |  |
| data.data[].other_attr.attrinfos[].ischecked | string | 是 | true | 是否启用 |
| data.data[].modified | string | 是 | 2023-12-01 20:00:01 | 修改时间 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "sku_ids": [],
  "page_index": 0,
  "modified_begin": "",
  "modified_end": "",
  "page_size": 0
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "data": [
      {
        "i_id": "AAA",
        "is_liquid": false,
        "is_fluid": false,
        "declare_name_e_n": "帽子",
        "is_paste": false,
        "is_get_price": false,
        "is_special_cargo": false,
        "is_get_weight": false,
        "sku_id": "AAA-01",
        "declare_weight": 0.3,
        "hs_code": "1234567890",
        "is_magnetic": false,
        "is_powder": false,
        "is_battery": false,
        "modified": "2023-12-01 20:00:01",
        "other_attr": "",
        "declare_name_z_n": "hat",
        "declare_amount": 30
      }
    ],
    "page_index": 1,
    "has_next": true,
    "data_count": 200,
    "page_count": 10,
    "page_size": 20
  },
  "request_id": ""
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

## 查询调拨单头程费用

`/open/webapi/wmsapi/allocate/loadallocatefeev2`

| 项 | 内容 |
|---|---|
| 接口名称 | 查询调拨单头程费用 |
| 接口路径 | `/open/webapi/wmsapi/allocate/loadallocatefeev2` |
| docType / docId | 44 / 1280 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=1280 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/allocate/loadallocatefeev2` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/allocate/loadallocatefeev2` |


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
| modify_end_time | string | 是 | 2025-05-15 00:00:00 | 修改结束时间（时间、调拨单号、头程单号三个至少必填一个） |
| page_num | number | 是 | 1 | 分页（必填) |
| modify_start_time | string | 是 | 2025-05-14 00:00:00 | 修改开始时间（时间、调拨单号、头程单号三个至少必填一个） |
| io_ids | array | 是 |  | 调拨单号（时间、调拨单号、头程单号三个至少必填一个） |
| io_ids[] | number | 否 | 21233937 |  |
| first_trip_codes | array | 是 |  | 头程编号（时间、调拨单号、头程单号三个至少必填一个） |
| first_trip_codes[] | string | 否 | "FS202505081737149" |  |
| page_size | number | 是 | 10 | 每页条数（必填) |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.allocatefee_detail_list | array | 否 |  |  |
| data.allocatefee_detail_list[] | object | 否 |  |  |
| data.allocatefee_detail_list[].first_trip_code | string | 否 |  | 头程单号 |
| data.allocatefee_detail_list[].modify_time | string | 否 |  | 修改时间 |
| data.allocatefee_detail_list[].real_sent_date | string | 否 |  | 实际发货时间 |
| data.allocatefee_detail_list[].io_ids | array | 否 |  | 调拨单号 |
| data.allocatefee_detail_list[].io_ids[] | number | 否 |  |  |
| data.allocatefee_detail_list[].logistics_info | array | 否 |  | 物流信息 |
| data.allocatefee_detail_list[].logistics_info[] | object | 否 |  |  |
| data.allocatefee_detail_list[].logistics_info[].logistics_name | string | 是 |  | 物流名称+渠道 |
| data.allocatefee_detail_list[].logistics_info[].freight_price | number | 是 |  | 运费 |
| data.allocatefee_detail_list[].logistics_info[].freight_currency | string | 是 |  | 运费币种 |
| data.allocatefee_detail_list[].logistics_info[].freight_cny_rate | number | 是 |  | 运费人民币汇率 |
| data.allocatefee_detail_list[].logistics_info[].tariff_price | number | 是 |  | 关税 |
| data.allocatefee_detail_list[].logistics_info[].tariff_currency | string | 是 |  | 关税币种 |
| data.allocatefee_detail_list[].logistics_info[].tariff_cny_rate | number | 是 |  | 关税人民币汇率 |
| data.allocatefee_detail_list[].logistics_info[].other_cost_price | number | 是 |  | 其他费用 |
| data.allocatefee_detail_list[].logistics_info[].other_cost_currency | string | 是 |  | 其他费用币种 |
| data.allocatefee_detail_list[].logistics_info[].other_cost_cny_rate | number | 是 |  | 其他费用人民币汇率 |
| data.allocatefee_detail_list[].logistics_info[].sku_fees | array | 是 |  | 商品明细费用 |
| data.allocatefee_detail_list[].logistics_info[].sku_fees[] | object | 否 |  |  |
| data.allocatefee_detail_list[].logistics_info[].sku_fees[].sku_id | string | 是 |  | 商品编码 |
| data.allocatefee_detail_list[].logistics_info[].sku_fees[].freight_price | number | 是 |  | 运费 |
| data.allocatefee_detail_list[].logistics_info[].sku_fees[].tariff_price | number | 是 |  | 关税 |
| data.allocatefee_detail_list[].logistics_info[].sku_fees[].other_cost_price | number | 是 |  | 其他费用 |
| data.allocatefee_detail_list[].logistics_info[].sku_fees[].share_qty | number | 是 |  | 分摊数量 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "modify_end_time": "2025-05-15 00:00:00",
  "first_trip_codes": [],
  "page_num": 1,
  "modify_start_time": "2025-05-14 00:00:00",
  "io_ids": [],
  "page_size": 10
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "allocatefee_detail_list": [
      {
        "first_trip_code": "",
        "modify_time": "",
        "io_ids": [],
        "real_sent_date": "",
        "logistics_info": [
          {
            "logistics_name": "",
            "freight_currency": "",
            "freight_cny_rate": 0,
            "tariff_price": 0,
            "tariff_currency": "",
            "tariff_cny_rate": 0,
            "freight_price": 0,
            "other_cost_currency": "",
            "other_cost_cny_rate": 0,
            "sku_fees": [
              {
                "tariff_price": 0,
                "freight_price": 0,
                "sku_id": "",
                "other_cost_price": 0,
                "share_qty": 0
              }
            ],
            "other_cost_price": 0
          }
        ]
      }
    ]
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 跨境售后单查询

`/open/webapi/cb/cborder/getrefunds`

| 项 | 内容 |
|---|---|
| 接口名称 | 跨境售后单查询 |
| 接口路径 | `/open/webapi/cb/cborder/getrefunds` |
| docType / docId | 44 / 1110 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=1110 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/cb/cborder/getrefunds` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/cb/cborder/getrefunds` |


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
| modified_begin | string | 是 | 2024-11-25 |  |
| modified_end | string | 是 | 2024-11-30 |  |
| as_ids | array | 否 |  | 售后单号组 |
| as_ids[] | number | 否 |  |  |
| good_status | string | 否 |  | 货物状态 |
| status | string | 否 |  | 售后单状态 |
| shop_status | string | 否 |  | 平台状态 |
| so_ids | array | 否 |  | 线上单号 |
| so_ids[] | string | 否 |  |  |
| shop_buyer_ids | array | 否 |  | 买家账号 |
| shop_buyer_ids[] | string | 否 |  |  |
| o_ids | array | 否 |  | 内部订单号 |
| o_ids[] | number | 否 |  |  |
| io_ids | array | 否 |  | 出库单号 |
| io_ids[] | string | 否 |  |  |
| shop_id | number | 否 |  | 店铺编号 |
| start_ts | number | 否 |  | 开始TS |
| current_page | number | 是 | 1 | 当前页 |
| page_size | number | 是 | 50 | 每页数 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.page_index | number | 否 |  | 当前页 |
| data.page_size | number | 否 |  | 分页数 |
| data.data_count | number | 否 |  | 总数量 |
| data.page_count | number | 否 |  | 总页数 |
| data.has_next | boolean | 否 |  | 是否有下页 |
| data.data | array | 否 |  | 数据对象列表 |
| data.data[] | object | 否 |  |  |
| data.data[].as_id | number | 是 |  | 售后单号 |
| data.data[].as_date | string | 是 |  | 售后时间 |
| data.data[].outer_as_id | string | 是 |  | 外部售后单号 |
| data.data[].o_id | string | 是 |  | 内部单号 |
| data.data[].so_id | string | 是 |  | 线上单号 |
| data.data[].type | string | 是 |  | 售后类型 |
| data.data[].created | string | 是 |  | 创建时间 |
| data.data[].labels | string | 是 |  | 标签 |
| data.data[].creator_name | string | 是 |  | 创建人 |
| data.data[].modified | string | 是 |  | 修改时间 |
| data.data[].modifier_name | string | 是 |  | 修改人 |
| data.data[].status | string | 是 |  | 状态 |
| data.data[].shop_status | string | 是 |  | 店铺状态 |
| data.data[].remark | string | 是 |  | 备注 |
| data.data[].io_id | string | 是 |  | 出库单号 |
| data.data[].question_type | string | 是 |  | 异常类型 |
| data.data[].warehouse | string | 是 |  | 分仓 |
| data.data[].refund | string | 是 |  | 退款金额 |
| data.data[].payment | string | 是 |  | 支付方式 |
| data.data[].good_status | string | 是 |  | 货物状态 |
| data.data[].node | string | 是 |  | 备注 |
| data.data[].order_status | string | 是 |  | 订单状态 |
| data.data[].shop_buyer_id | string | 是 |  | 店铺买家账号 |
| data.data[].shop_id | string | 是 |  | 店铺id |
| data.data[].receiver_name | string | 是 |  | 收件人姓名 |
| data.data[].receiver_mobile | string | 是 |  | 收件人手机 |
| data.data[].logistics_company | string | 是 |  | 物流公司 |
| data.data[].l_id | string | 是 |  | 物流单号 |
| data.data[].wh_id | string | 是 |  | 仓库类型 |
| data.data[].drp_co_name | string | 是 |  | 分销商id |
| data.data[].wms_co_id | string | 是 |  | 分仓id |
| data.data[].confirm_date | string | 是 |  | 确认时间 |
| data.data[].freight | string | 是 |  | 运费 |
| data.data[].drp_co_id_from | string | 是 |  | 分销商名称 |
| data.data[].drp_co_id_to | string | 是 |  | 供销商id |
| data.data[].order_type | string | 是 |  | 订单类型 |
| data.data[].buyer_apply_refund | string | 是 |  | 买家申请退款金额 |
| data.data[].free_amount | string | 是 |  | 优惠 |
| data.data[].ts | string | 是 |  | 时间戳 |
| data.data[].co_id | string | 是 |  | 商家id |
| data.data[].refund_items | array | 是 |  | 退款明细 |
| data.data[].refund_items[] | object | 否 |  |  |
| data.data[].refund_items[].asi_id | number | 是 |  | 退款明细id |
| data.data[].refund_items[].as_id | number | 是 |  | 售后单号 |
| data.data[].refund_items[].sku_id | string | 是 |  | 商品编码 |
| data.data[].refund_items[].qty | string | 是 |  | 数量 |
| data.data[].refund_items[].defective_qty | string | 是 |  | 次品数量 |
| data.data[].refund_items[].price | string | 是 |  | 价格 |
| data.data[].refund_items[].amount | string | 是 |  | 金额 |
| data.data[].refund_items[].name | string | 是 |  | 名称 |
| data.data[].refund_items[].pic | string | 是 |  | 图片 |
| data.data[].refund_items[].type | string | 是 |  | 售后类型 |
| data.data[].refund_items[].properties_value | string | 是 |  | 属性 |
| data.data[].refund_items[].outer_oi_id | string | 是 |  | 外部明细单号 |
| data.data[].refund_items[].sku_type | string | 是 |  | 商品类型 |
| data.data[].refund_items[].r_qty | string | 是 |  | 实退数量 |
| data.data[].refund_items[].item_sign | string | 是 |  | 明细签名 |
| data.data[].refund_items[].box_id | string | 是 |  | 箱号 |
| data.data[].refund_items[].combine_sku_id | string | 是 |  | 组合装商品编码 |
| data.data[].refund_items[].receive_date | string | 是 |  | 收货时间 |
| data.data[].refund_items[].shop_sku_id | string | 是 |  | 店铺商品编码 |
| data.data[].refund_items[].i_id | string | 是 |  | 款号 |
| data.data[].refund_items[].des | string | 是 |  | 描述 |
| data.data[].refund_items[].shop_amount | string | 是 |  | 店铺金额 |
| data.data[].refund_items[].is_gift | string | 是 |  | 是否赠品 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "o_ids": [],
  "start_ts": 0,
  "shop_status": "",
  "modified_begin": "2024-11-25",
  "io_ids": [],
  "as_ids": [],
  "good_status": "",
  "shop_buyer_ids": [],
  "shop_id": 0,
  "so_ids": [],
  "modified_end": "2024-11-30",
  "current_page": 1,
  "status": "",
  "page_size": 50
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "data": [
      {
        "modifier_name": "",
        "as_id": 0,
        "outer_as_id": "",
        "freight": "",
        "remark": "",
        "drp_co_name": "",
        "drp_co_id_from": "",
        "type": "",
        "good_status": "",
        "buyer_apply_refund": "",
        "order_status": "",
        "refund_items": [
          {
            "box_id": "",
            "i_id": "",
            "amount": "",
            "as_id": 0,
            "sku_type": "",
            "asi_id": 0,
            "item_sign": "",
            "sku_id": "",
            "pic": "",
            "type": "",
            "shop_amount": "",
            "shop_sku_id": "",
            "receive_date": "",
            "properties_value": "",
            "des": "",
            "is_gift": "",
            "price": "",
            "qty": "",
            "combine_sku_id": "",
            "name": "",
            "r_qty": "",
            "defective_qty": "",
            "outer_oi_id": ""
          }
        ],
        "so_id": "",
        "o_id": "",
        "modified": "",
        "receiver_name": "",
        "payment": "",
        "order_type": "",
        "free_amount": "",
        "shop_status": "",
        "question_type": "",
        "created": "",
        "co_id": "",
        "warehouse": "",
        "receiver_mobile": "",
        "io_id": "",
        "node": "",
        "shop_id": "",
        "shop_buyer_id": "",
        "wms_co_id": "",
        "wh_id": "",
        "drp_co_id_to": "",
        "confirm_date": "",
        "as_date": "",
        "creator_name": "",
        "logistics_company": "",
        "l_id": "",
        "status": "",
        "refund": "",
        "ts": ""
      }
    ],
    "page_index": 0,
    "has_next": true,
    "data_count": 0,
    "page_count": 0,
    "page_size": 0
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 送仓包裹返回仓

`/open/webapi/cbdtwapi/cbdtw/getpackageinfo`

| 项 | 内容 |
|---|---|
| 接口名称 | 送仓包裹返回仓 |
| 接口路径 | `/open/webapi/cbdtwapi/cbdtw/getpackageinfo` |
| docType / docId | 44 / 1426 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=1426 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/cbdtwapi/cbdtw/getpackageinfo` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/cbdtwapi/cbdtw/getpackageinfo` |


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
| package_id | string | 是 | PC2510205012308 | TEMU包裹号 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | object | 是 |  |  |
| data.warehouse_id | string | 是 |  | 平台收货仓ID |
| data.warehouse_name | string | 是 |  | 平台收货仓名称 |
| code | number | 是 |  |  |
| msg | string | 是 |  |  |
| request_id | string | 是 |  |  |

### 请求示例

```json
{
  "package_id": "PC2510205012308"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "warehouse_name": "",
    "warehouse_id": ""
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 尾程运费回写接口

`/open/webapi/cblogisticsapi/cbexpressstatement/savefee`

| 项 | 内容 |
|---|---|
| 接口名称 | 尾程运费回写接口 |
| 接口路径 | `/open/webapi/cblogisticsapi/cbexpressstatement/savefee` |
| docType / docId | 44 / 489 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=489 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/cblogisticsapi/cbexpressstatement/savefee` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/cblogisticsapi/cbexpressstatement/savefee` |


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
| order_id | integer | 是 | 34805308 | 内部订单号 |
| sale_order_id | string | 是 | 111-9131284-3690618 | 线上单号 |
| currency | string | 是 | USD | 币种 |
| amount | number | 是 | 20 | 金额 |
| outerwms_weight | number | 否 | 1 | 重量 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | boolean | 是 | true | 返回结果 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "amount": 20,
  "sale_order_id": "111-9131284-3690618",
  "outerwms_weight": 1,
  "currency": "USD",
  "order_id": 34805308
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

## 1688商品映射推送

`/open/webapi/globalapi/skumap/mapping`

| 项 | 内容 |
|---|---|
| 接口名称 | 1688商品映射推送 |
| 接口路径 | `/open/webapi/globalapi/skumap/mapping` |
| docType / docId | 44 / 502 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=502 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/globalapi/skumap/mapping` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/globalapi/skumap/mapping` |


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
| data.code | number | 否 |  |  |
| data.msg | string | 否 |  |  |
| data.data | null | 否 |  |  |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |
| success | boolean | 否 |  |  |

### 请求示例

```json
[
  {
    "member_id": "b2b-22126655131433c09d",
    "min_order_qty": 2,
    "plat_sku_id": "4074184537367",
    "plat_offer_id": "",
    "name": "纯棉方巾彩格纱布小毛巾婴幼儿童纱布口水巾幼儿园手帕毛巾批发-api",
    "sku_id": "",
    "pic": "https://cbu01.alicdn.com/img/ibank/O1CN01CuUogr22yc4q2qPYS_!!4158007189-0-cib.jpg",
    "supplier_id": 0,
    "plat_spec_id": "ac1817f4154ea86526945b98824b2157",
    "plat_p_v": "颜色:彩格粉色;规格（长*宽cm）:25*25",
    "url": "https://detail.1688.com/offer/579243433622.html"
  }
]
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "msg": "",
    "code": 0,
    "data": ""
  },
  "success": true,
  "request_id": ""
}
```


### 异常示例

_无_


---

## 更新订单跨境物流信息

`/open/jushuitan/crossborder/forwarder/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 更新订单跨境物流信息 |
| 接口路径 | `/open/jushuitan/crossborder/forwarder/upload` |
| docType / docId | 44 / 71 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=71 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/crossborder/forwarder/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/crossborder/forwarder/upload` |


### 接口说明

API 说明
 系统相关界面----【订单】
 只更新跨境订单物流信息，不更新订单状态，更新的物流信息在订单列表查看
 上传的PDF面单在ERP【国际运单号获取】----预览PDF快递单，查看（ 渠道 其他 不支持预览，但是可以把面单打出来看 ）

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
| items[].shop_id | string | 是 |  | 店铺编号 |
| items[].o_id | string | 是 |  | 内部单号 |
| items[].so_id | string | 是 |  | 线上单号 |
| items[].tracking_type | number | 否 |  | 类型；默认1000 |
| items[].tracking_code | string | 否 |  | 渠道编码；默认开放平台渠道（注意：tracking_no有值才会保存渠道相关信息） |
| items[].tracking_info | string | 否 |  | 渠道名称 |
| items[].l_id | string | 否 |  | 物流单号 |
| items[].lc_code | string | 否 |  | 物流公司编码 |
| items[].pdf_url | string | 否 |  | 面单pdf链接；如果需要ERP打印面单必填 |
| items[].tracking_no | string | 否 |  | 国际运单号 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | string | 否 |  | 返回数据 |
| code | number | 否 |  | 错误码 |
| issuccess | boolean | 否 |  | 是否执行成功 |
| msg | string | 否 |  | 执行描述 |

### 请求示例

```json
{
  "items": [
    {
      "shop_id": 11111111,
      "so_id": "Test",
      "o_id": "111",
      "tracking_info": "***",
      "tracking_code": "STEXPTHPH",
      "tracking_no": "111",
      "pdf_url": "",
      "lc_code": "SF",
      "l_id": "1111",
      "tracking_type": 140
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": "",
  "issuccess": true
}
```


### 异常示例

```json
{"code":0,"msg":"错误信息","request_id":"xxxxxx","data":{}/[]}
```


---

## 创建头程单

`/open/webapi/cb/cbfirsttrip/createfirsttrip`

| 项 | 内容 |
|---|---|
| 接口名称 | 创建头程单 |
| 接口路径 | `/open/webapi/cb/cbfirsttrip/createfirsttrip` |
| docType / docId | 44 / 891 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=891 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/cb/cbfirsttrip/createfirsttrip` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/cb/cbfirsttrip/createfirsttrip` |


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
| out_wms | integer | 是 | 10197090 | 转出仓Id |
| destination_wms | integer | 是 | 12514353 | 目的仓Id |
| first_trip_type | string | 是 | OverseasWms | 头程类型，海外仓头程：OverseasWms，FBA头程：FBA ，目前仅支持海外仓头程 |
| out_country | string | 否 | CN | 起运国编码，可选值从离线表中选取，离线表请访问:https://w.erp321.com/app/support/document.html#page=6815 |
| destination_country | string | 否 | US | 目的国编码，可选值从离线表中选取，离线表请访问:https://w.erp321.com/app/support/document.html#page=6815 |
| departure_port | string | 否 | 上海港 | 起运港，可选值在聚水潭ERP中维护 |
| destination_port | string | 否 | 洛杉矶港 | 目的港，可选值在聚水潭ERP中维护 |
| delivery_model | string | 否 | 海运 | 补货方式，可选值在聚水潭ERP中维护 |
| estimated_shipment_time | string | 否 | 2024-08-14 14:00:00 | 预计出货时间 |
| estimateInstock_date | string | 否 | 2024-08-14 14:00:00 | 预计到货时间 |
| pack_num | integer | 否 | 3 | 箱数 |
| pack_volume_total | number | 否 | 3.14 | 实际体积 m³ |
| pack_weight_total | number | 否 | 3.14 | 实际重量 kg |
| pack_volume_weight | number | 否 | 3.14 | 实际体积重 kg |
| pack_type | integer | 否 | 1 | 装柜方式，枚举：[0、默认，1、整柜，2、散柜，3、退货] |
| pack_size | integer | 否 | 1 | 箱型，枚举：[0、默认，1、40HQ，2、20HQ，3、40GP，4、20GP，5、散货入库，6、托盘入库，7、45HQ，8、53HQ，9、45GP] |
| pallet_number | string | 否 | PN7777722222 | 托盘号 |
| cabinet_no | string | 否 | CN8888888888 | 柜号 |
| declaration_company | string | 否 | 上海某某某报关公司 | 报关公司 |
| attachment_urls | array | 否 |  | 附件，最多支持三个附件 |
| attachment_urls[] | string | 否 | http://file.xxx.com/xxx.pdf | 附件地址链接（不做文件内容校验，请自行存储文件内容） |
| remark | string | 否 | 备注1 | 备注1，该备注会展示在头程单的备注1中 |
| remark2 | string | 否 | 备注2 | 备注2，该备注会展示在头程单的备注2中 |
| remark3 | string | 否 | 备注3 | 备注3，该备注会展示在头程单的备注3中 |
| remark4 | string | 否 | 备注4 | 备注4，该备注会展示在头程单的备注4中 |
| remark5 | string | 否 | 备注5 | 备注5，该备注会展示在头程单的备注5中 |
| items | array | 是 |  |  |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | baizhu001 | 普通商品资料商品编码 |
| items[].qty | integer | 是 | 1 | 头程计划数量 |
| auto_cfm | boolean | 否 | true | 是否自动确认头程计划（默认true） |
| is_auto_create_allocate | boolean | 否 | false | 是否自动创建调拨单，仅当AutoCfm == true 时生效，因为不确认头程计划就不能生成调拨单 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.first_trip_code | string | 否 |  | 头程单号 |
| data.message | string | 否 |  | 创建头程计划成功，但后续步骤失败的错误消息 |
| data.is_cfmed | boolean | 否 |  | 头程计划是否确认成功 |
| data.io_id | number | 否 |  | 调拨单号（如果生成调拨单成功，则返回调拨单号） |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "out_wms": 10197090,
  "first_trip_type": "OverseasWms",
  "destination_wms": 12514353,
  "remark": "测试头程",
  "auto_cfm": true,
  "is_auto_create_allocate": false,
  "items": [
    {
      "qty": 1,
      "sku_id": "baizhu001"
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
    "first_trip_code": "",
    "is_cfmed": true,
    "message": "",
    "io_id": 0
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 跨境订单查询

`/open/webapi/cb/cborder/getorders`

| 项 | 内容 |
|---|---|
| 接口名称 | 跨境订单查询 |
| 接口路径 | `/open/webapi/cb/cborder/getorders` |
| docType / docId | 44 / 1109 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=44&docId=1109 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/cb/cborder/getorders` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/cb/cborder/getorders` |


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
| modified_begin | string | 是 | 2024-12-01 | 修改开始时间 |
| modified_end | string | 是 | 2024-12-03 | 修改结束时间 |
| o_ids | array | 否 |  | 内部订单 |
| o_ids[] | number | 否 |  |  |
| status | string | 否 |  | 订单状态：待付款：WaitPay；发货中：Delivering；被合并：Merged；异常：Question；被拆分：Split；等供销商\|外仓发货：WaitOuterSent；已付款待审核：WaitConfirm；已客审待财审：WaitFConfirm；已发货：Sent；取消：Cancelled |
| not_status | string | 否 |  | 排除状态 |
| so_ids | array | 否 |  | 线上订单 |
| so_ids[] | string | 否 |  |  |
| io_ids | array | 否 |  | 出库单号 |
| io_ids[] | string | 否 |  |  |
| seller_flag | string | 否 |  | 旗帜 |
| l_id | string | 否 |  | 物流单号 |
| cb_l_id | string | 否 |  | 跨境物流单号 |
| order_types | array | 否 |  | 订单类型 |
| order_types[] | string | 否 |  |  |
| start_ts | number | 否 |  | 开始ts |
| current_page | number | 是 |  | 页码 |
| page_size | number | 是 |  | 返回订单数量 |
| shop_id | number | 否 |  | 店铺编码 |
| shop_name | string | 否 |  | 店铺名称 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.page_index | number | 否 | 1 | 页码 |
| data.page_size | number | 否 | 50 | 每页数量 |
| data.data_count | number | 否 |  | 总数量 |
| data.page_count | number | 否 |  | 总页数 |
| data.has_next | boolean | 否 |  | 是否有下页 |
| data.data | array | 否 |  | 订单列表 |
| data.data[] | object | 否 |  |  |
| data.data[].co_id | number | 是 |  | 商家id |
| data.data[].o_id | number | 是 |  | 内部订单号 |
| data.data[].shop_id | number | 是 |  | 店铺 |
| data.data[].so_id | string | 是 |  | 线上单号 |
| data.data[].order_date | string | 是 |  | 采购日期 |
| data.data[].shop_status | string | 是 |  | 平台状态 |
| data.data[].question_type | string | 是 |  | 异常类型 |
| data.data[].question_desc | string | 是 |  | 异常描述 |
| data.data[].status | string | 是 |  | 状态 |
| data.data[].shop_buyer_id | string | 是 |  | 买家id |
| data.data[].receiver_country | string | 是 |  | 收件人国家 |
| data.data[].receiver_state | string | 是 |  | 收件人省 |
| data.data[].receiver_city | string | 是 |  | 收件人市 |
| data.data[].receiver_district | string | 是 |  | 收件人区 |
| data.data[].receiver_address | string | 是 |  | 收件人地址 |
| data.data[].receiver_name | string | 是 |  | 收件人姓名 |
| data.data[].receiver_mobile | string | 是 |  | 收件人手机 |
| data.data[].receiver_phone | string | 是 |  | 收件人电话 |
| data.data[].receiver_town | string | 是 |  | 收件人镇 |
| data.data[].receiver_zip | string | 是 |  | 收件人邮编 |
| data.data[].buyer_id | string | 是 |  | 买家id |
| data.data[].send_date | string | 是 |  | 发货时间 |
| data.data[].pay_amount | string | 是 |  | 应付 |
| data.data[].freight | string | 是 |  | 运费 |
| data.data[].first_freight | string | 是 |  | 跨境订单-头程运费 |
| data.data[].outerwms_freight | string | 是 |  | 跨境订单-尾程运费 |
| data.data[].weight | string | 是 |  | 重量 |
| data.data[].f_weight | string | 是 |  | 实重 |
| data.data[].buyer_message | string | 是 |  | 买家留言 |
| data.data[].remark | string | 是 |  | 备注 |
| data.data[].invoice_title | string | 是 |  | 发票 |
| data.data[].is_cod | boolean | 是 |  | 是否货到付款 |
| data.data[].type | string | 是 |  | 订单类型 |
| data.data[].shop_site | string | 是 |  | 站点 |
| data.data[].free_amount | string | 是 |  | 优惠 |
| data.data[].paid_amount | string | 是 |  | 已付 |
| data.data[].pay_date | string | 是 |  | 付款时间 |
| data.data[].outer_pay_id | string | 是 |  | 支付单号 |
| data.data[].modified | string | 是 |  | 修改时间 |
| data.data[].order_from | string | 是 |  | 订单来源 |
| data.data[].shop_name | string | 是 |  | 店铺名称 |
| data.data[].seller_flag | string | 是 |  | 卖家标记 |
| data.data[].plan_delivery_date | string | 是 |  | 计划发货时间 |
| data.data[].lc_id | string | 是 |  | 物流编号 |
| data.data[].l_id | string | 是 |  | 物流单号 |
| data.data[].logistics_company | string | 是 |  | 物流公司 |
| data.data[].discount_rate | string | 是 |  | 折扣 |
| data.data[].tag | string | 是 |  | 标记 |
| data.data[].wms_co_id | string | 是 |  | 分仓id |
| data.data[].currency | string | 是 |  | 币种 |
| data.data[].labels | string | 是 |  | 标签 |
| data.data[].amount | string | 是 |  | 金额 |
| data.data[].drp_co_id_from | string | 是 |  | 分销商 |
| data.data[].is_split | boolean | 是 |  | 是否拆分 |
| data.data[].is_merge | boolean | 是 |  | 是否合并 |
| data.data[].creator_name | string | 是 |  | 创建人 |
| data.data[].buyer_tax_no | string | 是 |  | 买家税号 |
| data.data[].invoice_type | string | 是 |  | 发票类型 |
| data.data[].sign_time | string | 是 |  | 签收时间 |
| data.data[].logistics_sign_time | string | 是 |  | 国际物流跟踪界面包裹签收时间 |
| data.data[].skus | string | 是 |  | 商品 |
| data.data[].card_info | string | 是 |  | 证件信息 |
| data.data[].end_time | string | 是 |  | 结束时间 |
| data.data[].sender_address | string | 是 |  | 发件人信息 |
| data.data[].referrer_id | string | 是 |  | 主播id |
| data.data[].referrer_name | string | 是 |  | 主播名称 |
| data.data[].created | string | 是 |  | 创建时间 |
| data.data[].shipment | string | 是 |  | 买家指定物流 |
| data.data[].open_id | string | 是 |  |  |
| data.data[].outer_as_id | string | 是 |  |  |
| data.data[].ts | string | 是 |  |  |
| data.data[].buyer_paid_amount | string | 是 |  | 买家应付 |
| data.data[].seller_income_amount | string | 是 |  | 卖家应收 |
| data.data[].link_o_id | string | 是 |  | 关联单号 |
| data.data[].merge_so_id | string | 是 |  | 合并线上单号 |
| data.data[].outer_so_id | string | 是 |  | 外部单号 |
| data.data[].cb_l_id | string | 是 |  | 国际单号 |
| data.data[].cb_lc_code | string | 是 |  | 渠道编码 |
| data.data[].l_id_first_trip | string | 是 |  | 头程单号 |
| data.data[].l_id_last_trip | string | 是 |  | 尾程单号 |
| data.data[].cb_lc_name | string | 是 |  | 物流商名称 |
| data.data[].chosen_channel | string | 是 |  | 选择渠道 |
| data.data[].channel_name | string | 是 |  | 渠道名称(渠道别名) |
| data.data[].confirm_date | string | 是 |  | 审核时间 |
| data.data[].declare_amount | string | 是 |  | 申报金额 |
| data.data[].cb_total_tax | string | 是 |  | 跨境税金 |
| data.data[].freight_tax | string | 是 |  | 运费税 |
| data.data[].package_no | string | 是 |  | 包裹号 |
| data.data[].warehouse_oid | string | 是 |  | 仓库单号 |
| data.data[].platform_free_amount | string | 是 |  | 平台优惠 |
| data.data[].pay_free_amount | string | 是 |  | 支付优惠 |
| data.data[].referrer_free_amount | string | 是 |  | 主播优惠 |
| data.data[].shop_free_amount | string | 是 |  | 店铺优惠 |
| data.data[].refund_amount | string | 是 |  | 退款金额 |
| data.data[].first_freight_tariff | number | 是 |  | 跨境订单-头程关税 |
| data.data[].f_freight_other_expense | number | 是 |  | 跨境订单-头程其他费用 |
| data.data[].order_items | array | 是 |  | 订单明细 |
| data.data[].order_items[] | object | 否 |  |  |
| data.data[].order_items[].oi_id | number | 是 |  | 明细id |
| data.data[].order_items[].sku_id | string | 是 |  | 商品编码 |
| data.data[].order_items[].i_id | string | 是 |  | 款号 |
| data.data[].order_items[].shop_sku_id | string | 是 |  | 店铺商品编码 |
| data.data[].order_items[].shop_i_id | string | 是 |  | 店铺款号 |
| data.data[].order_items[].properties_value | string | 是 |  | 属性 |
| data.data[].order_items[].amount | string | 是 |  | 金额 |
| data.data[].order_items[].base_price | string | 是 |  | 基本售价 |
| data.data[].order_items[].qty | string | 是 |  | 数量 |
| data.data[].order_items[].name | string | 是 |  | 名称 |
| data.data[].order_items[].price | string | 是 |  | 单价（默认含税） |
| data.data[].order_items[].outer_oi_id | string | 是 |  | 外部关联id |
| data.data[].order_items[].refund_id | string | 是 |  | 退款id |
| data.data[].order_items[].refund_qty | string | 是 |  | 退货数量 |
| data.data[].order_items[].refund_status | string | 是 |  | 退款状态 |
| data.data[].order_items[].raw_so_id | string | 是 |  | 原始订单 |
| data.data[].order_items[].is_presale | boolean | 是 |  | 是否预售 |
| data.data[].order_items[].is_gift | boolean | 是 |  | 是否赠品 |
| data.data[].order_items[].item_status | string | 是 |  | 明细状态 |
| data.data[].order_items[].send_warehouse | string | 是 |  | 发货仓 |
| data.data[].order_items[].item_pay_amount | string | 是 |  | 实付金额 |
| data.data[].order_items[].referrer_id | string | 是 |  | 主播id |
| data.data[].order_items[].referrer_name | string | 是 |  | 主播名称 |
| data.data[].order_items[].discount_rate | string | 是 |  | 折扣 |
| data.data[].order_items[].pic | string | 是 |  | 图片 |
| data.data[].order_items[].sku_type | string | 是 |  | 商品类型 |
| data.data[].order_items[].remark | string | 是 |  | 备注 |
| data.data[].order_items[].src_combine_sku_id | string | 是 |  | 源组合装 |
| data.data[].order_items[].item_ext_data | string | 是 |  | 扩展信息 |
| data.data[].order_items[].buyer_paid_amount | string | 是 |  | 买家应付 |
| data.data[].order_items[].seller_income_amount | string | 是 |  | 卖家实收 |
| data.data[].order_items[].product_tax | string | 是 |  | 商品税 |
| data.data[].order_items[].product_freight | string | 是 |  | 商品运费 |
| data.data[].order_items[].product_free_amount | string | 是 |  | 商品优惠 |
| data.data[].order_items[].batch_id | string | 是 |  | 批次Id |
| data.data[].order_items[].produced_date | null | 是 |  | 生产日期 |
| data.data[].order_items[].expiration_date | null | 是 |  | 有效期 |
| data.data[].order_pays | array | 是 |  | 支付单 |
| data.data[].order_pays[] | object | 否 |  |  |
| data.data[].order_pays[].pay_id | number | 是 |  | 支付id |
| data.data[].order_pays[].outer_pay_id | string | 是 |  | 外部支付单号 |
| data.data[].order_pays[].pay_date | string | 是 |  | 支付时间 |
| data.data[].order_pays[].amount | string | 是 |  | 金额 |
| data.data[].order_pays[].payment | string | 是 |  | 支付方式 |
| data.data[].order_pays[].buyer_account | string | 是 |  | 买家账号 |
| data.data[].order_pays[].is_order_pay | boolean | 是 |  | 是否订单支付 |
| data.data[].order_pays[].status | string | 是 |  | 支付状态 |
| data.data[].order_pays[].pay_type | string | 是 |  | 支付类型 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "o_ids": [],
  "start_ts": 0,
  "order_types": [],
  "modified_begin": "2024-12-01",
  "io_ids": [],
  "status": "",
  "seller_flag": "",
  "so_ids": [],
  "modified_end": "2024-12-03",
  "l_id": "",
  "not_status": "",
  "current_page": 0,
  "page_size": 0
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "data": [
      {
        "plan_delivery_date": "",
        "referrer_id": "",
        "open_id": "",
        "f_weight": "",
        "chosen_channel": "",
        "drp_co_id_from": "",
        "buyer_id": "",
        "type": "",
        "discount_rate": "",
        "order_pays": [
          {
            "outer_pay_id": "",
            "pay_date": "",
            "amount": "",
            "buyer_account": "",
            "payment": "",
            "is_order_pay": true,
            "pay_type": "",
            "pay_id": 0,
            "status": ""
          }
        ],
        "send_date": "",
        "buyer_tax_no": "",
        "modified": "",
        "receiver_country": "",
        "tag": "",
        "card_info": "",
        "cb_l_id": "",
        "order_items": [
          {
            "i_id": "",
            "referrer_id": "",
            "batch_id": "",
            "product_tax": "",
            "remark": "",
            "product_freight": "",
            "pic": "",
            "item_ext_data": "",
            "shop_i_id": "",
            "expiration_date": "",
            "discount_rate": "",
            "produced_date": "",
            "src_combine_sku_id": "",
            "price": "",
            "base_price": "",
            "seller_income_amount": "",
            "outer_oi_id": "",
            "buyer_paid_amount": "",
            "is_presale": true,
            "amount": "",
            "send_warehouse": "",
            "item_pay_amount": "",
            "refund_status": "",
            "sku_type": "",
            "refund_qty": "",
            "sku_id": "",
            "item_status": "",
            "oi_id": 0,
            "refund_id": "",
            "shop_sku_id": "",
            "raw_so_id": "",
            "properties_value": "",
            "is_gift": true,
            "product_free_amount": "",
            "qty": "",
            "name": "",
            "referrer_name": ""
          }
        ],
        "buyer_paid_amount": "",
        "shipment": "",
        "shop_status": "",
        "buyer_message": "",
        "outer_so_id": "",
        "shop_free_amount": "",
        "created": "",
        "is_split": true,
        "weight": "",
        "shop_name": "",
        "labels": "",
        "shop_id": 0,
        "shop_buyer_id": "",
        "f_freight": "",
        "wms_co_id": "",
        "paid_amount": "",
        "referrer_name": "",
        "link_o_id": "",
        "status": "",
        "pay_date": "",
        "platform_free_amount": "",
        "pay_free_amount": "",
        "lc_id": "",
        "skus": "",
        "question_desc": "",
        "receiver_city": "",
        "invoice_title": "",
        "outer_as_id": "",
        "freight": "",
        "remark": "",
        "cb_total_tax": "",
        "is_cod": true,
        "receiver_state": "",
        "cb_financenew": "",
        "cb_lc_name": "",
        "receiver_zip": "",
        "so_id": "",
        "o_id": 0,
        "referrer_free_amount": "",
        "receiver_name": "",
        "refund_amount": "",
        "currency": "",
        "invoice_type": "",
        "seller_income_amount": "",
        "free_amount": "",
        "outer_pay_id": "",
        "amount": "",
        "warehouse_oid": "",
        "question_type": "",
        "package_no": "",
        "receiver_district": "",
        "receiver_town": "",
        "pay_amount": "",
        "co_id": 0,
        "end_time": "",
        "shop_site": "",
        "receiver_mobile": "",
        "sign_time": "",
        "seller_flag": "",
        "order_date": "",
        "merge_so_id": "",
        "sender_address": "",
        "order_from": "",
        "cb_lc_code": "",
        "is_merge": true,
        "freight_tax": "",
        "receiver_address": "",
        "logistics_company": "",
        "creator_name": "",
        "receiver_phone": "",
        "l_id": "",
        "ts": ""
      }
    ],
    "page_index": 1,
    "has_next": true,
    "data_count": 0,
    "page_count": 0,
    "page_size": 50
  },
  "cookie": "",
  "msg_type": "",
  "request_id": ""
}
```


### 异常示例

_无_


---
