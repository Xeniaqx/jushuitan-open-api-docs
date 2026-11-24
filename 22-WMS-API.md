# 聚水潭开放平台 · WMS API（线下版）

> 抓取日期：2026-11-23  
> 分类：WMS API（docType=22）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=22&docId=818

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 批量下架 | `/open/webapi/wmsapi/openoffshelve/skubatchoffshelve` | 818 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=818) |
| 批量上架 | `/open/webapi/wmsapi/openshelve/skubatchshelve` | 819 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=819) |
| 发货装箱功能 | `/open/webapi/wmsapi/shippingpack/addshippingpack` | 986 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=986) |
| 唯一码进出流水查询 | `/open/webapi/wmsapi/skusn/queryinoutitemskusns` | 996 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=996) |
| 打包机保存视频记录 | `/open/webapi/wmsapi/packageentries/saveipcvediorecord` | 1030 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=1030) |
| 发货-强制审核单件商品缺货订单 | `/open/webapi/wmsapi/checkoutopen/singleorderconfirms` | 593 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=593) |
| 查询极速发货订单数V2 | `/open/webapi/wmsapi/checkout/getfastdeliveryordercountv2` | 1319 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=1319) |
| 查询商品的推荐仓位 | `/open/webapi/wmsapi/openskubinquery/recommendskubin` | 1503 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=1503) |
| 生成快销标签 | `/open/webapi/wmsapi/openp2dskusn/createskusn` | 322 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=322) |
| 强制审核单件商品缺货订单并入库 | `/open/jushuitan/order/single/confirm` | 73 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=73) |
| 查询WMS工作日志 | `/open/webapi/wmsapi/worklog/getworklog` | 76 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=76) |
| 工作量补入 | `/open/webapi/wmsapi/worklog/workloadappend` | 154 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=154) |
| 查询快销唯一码信息 | `/open/jushuitan/skusn/load` | 173 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=173) |
| 跟踪信息查询 | `/open/jushuitan/skusn/query` | 252 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=252) |
| 进出仓流水 | `/open/jushuitan/inout/water/query` | 54 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=54) |
| 快销到货 | `/open/jushuitan/quicksale/arrival` | 436 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=436) |
| 根据箱号查询箱内商品推荐仓位 | `/open/webapi/wmsapi/openskubinquery/findskubin` | 450 | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=450) |

## 目录

- [批量下架](#批量下架)
- [批量上架](#批量上架)
- [发货装箱功能](#发货装箱功能)
- [唯一码进出流水查询](#唯一码进出流水查询)
- [打包机保存视频记录](#打包机保存视频记录)
- [发货-强制审核单件商品缺货订单](#发货-强制审核单件商品缺货订单)
- [查询极速发货订单数V2](#查询极速发货订单数v2)
- [查询商品的推荐仓位](#查询商品的推荐仓位)
- [生成快销标签](#生成快销标签)
- [强制审核单件商品缺货订单并入库](#强制审核单件商品缺货订单并入库)
- [查询WMS工作日志](#查询wms工作日志)
- [工作量补入](#工作量补入)
- [查询快销唯一码信息](#查询快销唯一码信息)
- [跟踪信息查询](#跟踪信息查询)
- [进出仓流水](#进出仓流水)
- [快销到货](#快销到货)
- [根据箱号查询箱内商品推荐仓位](#根据箱号查询箱内商品推荐仓位)

---

## 批量下架

`/open/webapi/wmsapi/openoffshelve/skubatchoffshelve`

| 项 | 内容 |
|---|---|
| 接口名称 | 批量下架 |
| 接口路径 | `/open/webapi/wmsapi/openoffshelve/skubatchoffshelve` |
| docType / docId | 22 / 818 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=818 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/openoffshelve/skubatchoffshelve` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/openoffshelve/skubatchoffshelve` |


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
| wms_co_id | number | 是 | 0 | 仓储方Id，默认传0 |
| warehouse_id | number | 是 | 1 | 暂存位所属仓库Id，主仓 = 1,销退仓 = 2,进货仓 = 3,次品仓 = 4,门店 = 5,自定义1仓 = 6,自定义2仓 = 7,自定义3仓 = 8,自定义4仓 = 9,自定义5仓 = 10,自定义6仓 = 11,自定义7仓 = 12,自定义8仓 = 13,自定义9仓 = 14,自定义10仓 = 15 |
| default_pack_type | number | 否 | 0 | 暂存位类型：0:仓库默认暂存位,3:拣货暂存位。主仓可传0、3，其它仓库只能传0 |
| items | array | 是 |  | 下架商品明细 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | A001 | 商品编码 |
| items[].bin_name | string | 是 | A-1-1 | 商品所在仓位 |
| items[].qty | number | 是 | 1 | 下架商品数量 |
| items[].sku_sns | array | 是 |  | 唯一码列表 |
| items[].sku_sns[] | string | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | object | 是 |  |  |

### 请求示例

```json
{
  "wms_co_id": 0,
  "items": [
    {
      "bin_name": "A-1-1",
      "qty": 1,
      "sku_id": "A001"
    }
  ],
  "warehouse_id": 1
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

## 批量上架

`/open/webapi/wmsapi/openshelve/skubatchshelve`

| 项 | 内容 |
|---|---|
| 接口名称 | 批量上架 |
| 接口路径 | `/open/webapi/wmsapi/openshelve/skubatchshelve` |
| docType / docId | 22 / 819 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=819 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/openshelve/skubatchshelve` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/openshelve/skubatchshelve` |


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
| wms_co_id | number | 否 | 0 | 仓储方Id，默认传0 |
| warehouse_id | number | 否 | 1 | 暂存位所属仓库Id，主仓 = 1,销退仓 = 2,进货仓 = 3,次品仓 = 4,门店 = 5,自定义1仓 = 6,自定义2仓 = 7,自定义3仓 = 8,自定义4仓 = 9,自定义5仓 = 10,自定义6仓 = 11,自定义7仓 = 12,自定义8仓 = 13,自定义9仓 = 14,自定义10仓 = 15 |
| default_pack_type | number | 否 | 0 | 默认值0 暂存位类型，0:仓库默认暂存位,3:拣货暂存位，4:补货暂存位。主仓可传0、3、4其它仓库只能传0 |
| items | array | 是 |  | 上架商品明细 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | A001 | 商品编码 |
| items[].bin_name | string | 是 | A-1-1 | 上架目标仓位 |
| items[].batch_id | string | 否 |  | 生产批次号 |
| items[].produced_date | string | 否 |  | 生产日期 |
| items[].expirtation_date | string | 否 |  | ExpirtationDate |
| items[].supplier_id | number | 否 |  | 供应商内部编码 |
| items[].qty | number | 是 | 1 | 上架商品数量 |
| items[].sku_sns | array | 否 |  | 唯一码列表 |
| items[].sku_sns[] | string | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | boolean | 是 |  |  |

### 请求示例

```json
{
  "wms_co_id": 0,
  "items": [
    {
      "bin_name": "A-1-1",
      "qty": 1,
      "sku_id": "A001"
    }
  ],
  "warehouse_id": 1
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": true
}
```


### 异常示例

_无_


---

## 发货装箱功能

`/open/webapi/wmsapi/shippingpack/addshippingpack`

| 项 | 内容 |
|---|---|
| 接口名称 | 发货装箱功能 |
| 接口路径 | `/open/webapi/wmsapi/shippingpack/addshippingpack` |
| docType / docId | 22 / 986 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=986 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/shippingpack/addshippingpack` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/shippingpack/addshippingpack` |


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
| io_id | number | 是 | 19921060 | 出库单号，优先查询 |
| lid | string | 是 | DPL131020100757 | 快递单号，出库单号查不到再查快递单号 |
| detail | array | 是 |  | 装箱明细 |
| detail[] | object | 否 |  |  |
| detail[].sku_id | string | 是 | 0305-1 | 商品编码 |
| detail[].qty | integer | 是 | 1 | 装箱数量 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 状态码，无异常=0 |
| data | object | 否 |  | 接口数据 |
| data.io_id | number | 否 |  | 出库单号 |
| data.o_id | number | 否 |  | 订单号 |
| data.lc_l_id | string | 否 |  | 快递单号 |
| data.logistics_company | string | 否 |  | 快递公司 |
| data.inout_qty | number | 否 |  | 单据数量 |
| data.shop_id | number | 否 |  | 店铺ID |
| data.shop_buyer_id | null | 否 |  | 买家ID |
| data.total_packed_qty | number | 否 |  | 总装箱数量 |
| data.pack_ids | array | 否 |  | 箱号 |
| data.pack_ids[] | string | 否 |  |  |
| data.co_id | number | 否 |  | 商家ID |
| data.error | string | 否 |  | 错误信息，即便状态为0，也会存在一些错误，这个错误信息有数据表示装箱失败 |
| msg | null | 否 |  | 接口信息 |
| msg_type | string | 否 |  | 接口类型：'json' \| 'string' |

### 请求示例

```json
{
  "lid": "DPL131020100757",
  "detail": [
    {
      "qty": 1,
      "sku_id": "0305-1"
    }
  ],
  "io_id": 19921060
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "shop_id": 0,
    "shop_buyer_id": "",
    "o_id": 0,
    "lc_l_id": "",
    "co_id": 0,
    "logistics_company": "",
    "total_packed_qty": 0,
    "error": "",
    "inout_qty": 0,
    "io_id": 0
  },
  "msg_type": ""
}
```


### 异常示例

_无_


---

## 唯一码进出流水查询

`/open/webapi/wmsapi/skusn/queryinoutitemskusns`

| 项 | 内容 |
|---|---|
| 接口名称 | 唯一码进出流水查询 |
| 接口路径 | `/open/webapi/wmsapi/skusn/queryinoutitemskusns` |
| docType / docId | 22 / 996 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=996 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/skusn/queryinoutitemskusns` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/skusn/queryinoutitemskusns` |


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
| wms_co_id | integer | 是 | 0 | 指定查询的仓储方 |
| page_index | integer | 是 | 1 | 页码，从1开始 |
| page_size | integer | 是 | 1000 | 每页查询条数，默认1000，最大1000 |
| io_ids | array | 否 |  | 进出仓单号数组 |
| io_ids[] | integer | 否 |  |  |
| o_ids | array | 否 |  | 内部订单号数组 |
| o_ids[] | integer | 否 |  |  |
| sku_sns | array | 否 |  | 唯一码数组 |
| sku_sns[] | string | 否 |  |  |
| create_time_start | string | 否 | 2025-01-01 00:00:00 | 创建开始时间，io_ids、o_Ids、sku_sns有值时，时间不限，可不填，否则最多查30天 |
| create_time_end | string | 否 | 2025-01-02 00:00:00 | 创建结束时间,如果时间条件不传，默认查前7天的数据（如当前是25年3月13日16点，会查询2025-03-07 00:00:00到2025-03-14 00:00:00） |
| last_ioi_sn_id  | integer | 否 |  | 唯一码流水翻页查询使用 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].io_id | number | 否 |  | 进出仓单号 |
| data[].o_id | null | 否 |  | 内部订单号 |
| data[].inout_type | number | 否 |  | 单据类型，1=采购入库;2=采购退货,3=销售出仓,4=销售退货,5=调拨出,6=调拨入,7=盘点,8=差异,9=结算,10=领用出仓,11=领用退仓,12=期初,13=其它出库,14=其它进仓,15=发票,16=加工出仓,17=加工进仓,18=其它退货 |
| data[].sku_id | string | 否 |  | 商品编码 |
| data[].sku_sn | string | 否 |  | 唯一码 |
| data[].cost_price | null | 否 |  | 单价 |
| data[].cost_amount | number | 否 |  | 价格 |
| data[].remark | null | 否 |  | 备注 |
| data[].create_time | string | 否 |  | 创建时间 |
| data[].modified_time | string | 否 |  | 修改时间 |
| data[].supplier_id | null | 否 |  | 供应商Id |
| data[].supplier_name | null | 否 |  | 供应商名称 |
| data[].ioi_sn_id  | integer | 否 |  | 唯一码流水主键 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "o_ids": [],
  "wms_co_id": 0,
  "sku_sns": [],
  "page_index": 1,
  "io_ids": [],
  "create_time_start": "2025-01-01 00:00:00",
  "create_time_end": "2025-01-02 00:00:00",
  "page_size": 1000
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": [
    {
      "cost_amount": 0,
      "modified_time": "",
      "create_time": "",
      "inout_type": 0,
      "o_id": "",
      "sku_id": "",
      "sku_sn": "",
      "remark": "",
      "supplier_name": "",
      "supplier_id": "",
      "io_id": 0,
      "cost_price": ""
    }
  ],
  "request_id": ""
}
```


### 异常示例

_无_


---

## 打包机保存视频记录

`/open/webapi/wmsapi/packageentries/saveipcvediorecord`

| 项 | 内容 |
|---|---|
| 接口名称 | 打包机保存视频记录 |
| 接口路径 | `/open/webapi/wmsapi/packageentries/saveipcvediorecord` |
| docType / docId | 22 / 1030 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=1030 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/packageentries/saveipcvediorecord` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/packageentries/saveipcvediorecord` |


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
| io_ids | string | 否 | "" | 出库单号（与快递单号不能同时为空） |
| l_ids | string | 否 | "000000097451352" | 快递单号（与出库单号不能同时为空） |
| vedio_duration | number | 是 | 100 | 视频时长 |
| d_ids | string | 是 | 139,140 | 监控设备号 |
| operation | string | 是 | 一单一货验货 | 操作枚举值：一单一货验货、一单一货连打验货、一单多货验货、发货装箱、称重、快销发货、打包登记 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | string | 否 |  |  |
| msg | string | 否 |  |  |
| request_id | string | 否 |  |  |

### 请求示例

```json
{
  "d_ids": "139,140",
  "vedio_duration": 100,
  "io_ids": "\\\\",
  "l_ids": "\\000000097451352\\",
  "operation": "一单一货验货"
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

## 发货-强制审核单件商品缺货订单

`/open/webapi/wmsapi/checkoutopen/singleorderconfirms`

| 项 | 内容 |
|---|---|
| 接口名称 | 发货-强制审核单件商品缺货订单 |
| 接口路径 | `/open/webapi/wmsapi/checkoutopen/singleorderconfirms` |
| docType / docId | 22 / 593 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=593 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/checkoutopen/singleorderconfirms` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/checkoutopen/singleorderconfirms` |


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
| lc_id | string | 否 |  | 快递公司id |
| is_single | boolean | 否 | true | 是否单件 |
| items | array | 是 |  | 商品数量 |
| items[] | object | 否 |  |  |
| items[].batch_id | string | 否 |  | 批次号 |
| items[].pack_id | string | 否 |  | 箱号 |
| items[].qty | number | 是 | 2 | 数量 |
| items[].sku_id | string | 是 | CS-1-10 | 商品编码 |
| items[].sku_sn | array | 否 |  | 唯一码 |
| items[].sku_sn[] | string | 否 |  |  |
| items[].price | number | 否 |  | 采购单价 |
| items[].plan_arrive_date | string | 否 |  | 预计到货日 |
| items[].produced_date | string | 否 |  | 生产日期 |
| items[].remark | string | 否 |  | 备注 |
| items[].expiration_date | string | 否 |  | 有效期至 |
| items[].tax_rate | number | 否 |  | 税率 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  |  |
| message | string | 是 |  | 提示信息 |
| data | object | 是 |  | 匹配sku数量 |
| data.success | string | 是 |  |  |
| data.message | string | 是 |  |  |
| data.sku_data | object | 是 |  |  |
| data.sku_data.sku_id | string | 是 |  | 商品数量 |
| data.sku_data.qty | number | 是 |  | 匹配数量 |

### 请求示例

```json
{
  "lc_id": "",
  "is_single": true,
  "items": [
    {
      "pack_id": "",
      "batch_id": "",
      "price": 0,
      "qty": 2,
      "plan_arrive_date": "",
      "sku_id": "CS-1-10",
      "sku_sn": [],
      "remark": "",
      "expiration_date": "",
      "tax_rate": 0,
      "produced_date": ""
    }
  ]
}
```


### 响应示例

```json
{
  "code": 0,
  "data": {
    "success": "",
    "message": "",
    "sku_data": {
      "qty": 0,
      "sku_id": ""
    }
  },
  "message": ""
}
```


### 异常示例

_无_


---

## 查询极速发货订单数V2

`/open/webapi/wmsapi/checkout/getfastdeliveryordercountv2`

| 项 | 内容 |
|---|---|
| 接口名称 | 查询极速发货订单数V2 |
| 接口路径 | `/open/webapi/wmsapi/checkout/getfastdeliveryordercountv2` |
| docType / docId | 22 / 1319 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=1319 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/checkout/getfastdeliveryordercountv2` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/checkout/getfastdeliveryordercountv2` |


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
| sku_id | string | 是 | XWY-1 | 商品编码 |
| qty | number | 否 | 1 | 匹配数量，默认值1，最大值500，超过500取500 |
| platform | number | 是 | 1 | 平台（传固定值1） |
| wms_co_id | number | 否 |  | 分仓编码 |
| owner_co_id | number | 否 |  | 货主编码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.order_count | string | 否 |  | 可以极速发货的订单数【PDA分货时按照实际数量查询】 |
| data.order_info | array | 否 |  | 极速订单信息 |
| data.order_info[] | object | 否 |  |  |
| data.order_info[].o_id | number | 否 |  | 内部订单号 |
| data.order_info[].io_id | number | 否 |  | 出库单号 |
| data.order_info[].logistics_company | null | 否 |  | 快递公司 |
| data.order_info[].pay_date | string | 否 |  | 付款时间 |
| data.order_info[].plan_delivery_date | string | 否 |  | 计划发货时间 |
| data.order_info[].is_multi | boolean | 否 |  | 是否多件订单 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "wms_co_id": 0,
  "qty": 1,
  "owner_co_id": 0,
  "sku_id": "XWY-1",
  "platform": 1
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "order_count": "",
    "order_info": [
      {
        "plan_delivery_date": "",
        "pay_date": "",
        "o_id": 0,
        "logistics_company": "",
        "io_id": 0,
        "is_multi": true
      }
    ]
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 查询商品的推荐仓位

`/open/webapi/wmsapi/openskubinquery/recommendskubin`

| 项 | 内容 |
|---|---|
| 接口名称 | 查询商品的推荐仓位 |
| 接口路径 | `/open/webapi/wmsapi/openskubinquery/recommendskubin` |
| docType / docId | 22 / 1503 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=1503 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/openskubinquery/recommendskubin` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/openskubinquery/recommendskubin` |


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
| sku_id | string | 是 | A001 | 商品编码/条码 |
| sku_id_type | number | 否 |  | SkuId识别类型，0：商品编码，1：自动识别，支持商品编码，国标码，辅助码等 |
| wms_co_id | integer | 否 |  | 仓储方Id，用于主仓授权后可以指定操作分仓 |
| owner_co_id | integer | 否 |  | 货主公司号（三方仓指定货主场景） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 是 |  |  |
| data.sku_id | string | 是 |  | 商品编码 |
| data.bin | string | 否 |  | 推荐的仓位，可能为空 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "wms_co_id": 0,
  "sku_id_type": 0,
  "owner_co_id": 0,
  "sku_id": "A001"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "bin": "",
    "sku_id": ""
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 生成快销标签

`/open/webapi/wmsapi/openp2dskusn/createskusn`

| 项 | 内容 |
|---|---|
| 接口名称 | 生成快销标签 |
| 接口路径 | `/open/webapi/wmsapi/openp2dskusn/createskusn` |
| docType / docId | 22 / 322 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=322 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/openp2dskusn/createskusn` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/openp2dskusn/createskusn` |


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
| order_ids | array | 是 |  | 订单号 |
| order_ids[] | integer | 否 | 41954710 |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  |  |
| msg | string | 是 |  |  |
| data | object | 是 |  |  |
| data.status | number | 是 |  | 默认0 生成中 1：生成完成且成功 -1：生成失败中断提示 |
| data.sku_sn_num | number | 是 |  | 当前已生成的标签数 |
| data.messages | string | 是 |  | 结果提示 |

### 请求示例

```json
{
  "order_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "messages": "",
    "sku_sn_num": 0,
    "status": 0
  }
}
```


### 异常示例

_无_


---

## 强制审核单件商品缺货订单并入库

`/open/jushuitan/order/single/confirm`

| 项 | 内容 |
|---|---|
| 接口名称 | 强制审核单件商品缺货订单并入库 |
| 接口路径 | `/open/jushuitan/order/single/confirm` |
| docType / docId | 22 / 73 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=73 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/order/single/confirm` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/order/single/confirm` |


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
| supplier_id | number | 否 |  | ERP内部供应商编号 |
| external_id | string | 是 |  | 外部采购入库单号，唯一 |
| wms_co_id | number | 否 |  | 分仓编码 |
| po_id | number | 否 |  | ERP内部采购单号 |
| remark | string | 否 |  | 备注 |
| tax_rate | number | 否 |  | 税率 |
| co_id | number | 否 |  | 货主仓库编码 |
| lc_id | string | 否 |  | 快递公司代码 |
| items | array | 是 |  | 商品信息 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 |  | SN码或者商品编码 |
| items[].qty | number | 否 |  | 商品数量（不填写默认是1，填写按照填写的为准） |
| items[].sku_sn | array | 否 |  | sn码 |
| items[].sku_sn[] | string | 否 |  |  |
| items[].price | number | 否 |  | 单价 |
| items[].batch_id | string | 否 |  | 开启生产批次，批次号必填 |
| items[].produced_date	 | string | 否 |  | 开启生产批次，生产日期必填 |
| items[].expiration_date | string | 否 |  | 开启生产批次，有效期必填 |
| items[].remark | string | 否 |  | 备注 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 非0失败 |
| msg | string | 否 |  | 错误描述 |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].external_id | string | 否 |  | 外部采购入库单号 |
| data[].io_id | number | 否 |  | 内部采购入库单号 |

### 请求示例

```json
{
  "wms_co_id": 0,
  "lc_id": "",
  "po_id": 0,
  "co_id": 0,
  "external_id": "",
  "remark": "",
  "supplier_id": 0,
  "items": [
    {
      "batch_id": "",
      "price": 0,
      "qty": 0,
      "sku_id": "",
      "sku_sn": [],
      "remark": "",
      "expiration_date": "",
      "produced_date": ""
    }
  ],
  "tax_rate": 0
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": [
    {
      "external_id": "",
      "io_id": 0
    }
  ]
}
```


### 异常示例

```json
{"code":0,"msg":"错误信息","request_id":"xxxxxx","data":{}/[]}
```


---

## 查询WMS工作日志

`/open/webapi/wmsapi/worklog/getworklog`

| 项 | 内容 |
|---|---|
| 接口名称 | 查询WMS工作日志 |
| 接口路径 | `/open/webapi/wmsapi/worklog/getworklog` |
| docType / docId | 22 / 76 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=76 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/worklog/getworklog` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/worklog/getworklog` |


### 接口说明

查询分仓数据需要分仓单独授权，如果存在多个分仓需要授权需要用服务商应用进行授权，自有商城应用只能授权一个仓

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
| sku_ids | array | 否 |  | 商品编码 |
| sku_ids[] | string | 否 | "YYYY-18" |  |
| types | array | 否 |  | 操作类型；InitToPack:初始化装箱，InitShelve:初始化上架，In:采购进仓，InShelve:快速上架，OtherIn:其他进仓，PurchaseOut:采购退货，Shelve:上架，OffShelve:下架，Pack:装箱，pick:拣货，seed:播种，checkout:出库验货，PrintExpess:打印快递单，aftersale:售后，PackStocktaking:箱盘点，ShippingPack:发货装箱，Move:移货，MoveSku:移货，MovePackBin:移箱，OpenPack:开箱，Stocktaking:盘点，BinPackToOut:仓位出库，bindInout:绑定批次 ，order_structure:包材按结构修正修正日志，Package:打包，pick_return:拣货归还，DefaultPackToOut:拣货位出库，all_unbind:解除拣货绑定，UnbindInout:整单解除批次绑定，UnbindInoutSku:按商品解除批次绑定，OtherOut:其他出库，FastStockRevise:直接修改库存，PaperPickToDefault:纸质拣货 ，PaperReturn:纸质拣货归还 ，DefaultCheckOut:通用暂存位出库，LidAppendPrint:快递单补打快递，Modifylock_amount:分销商登记账款，PackageMartial:包材日志，PrintSent:打印快递单，StockPlan:盘点任务，每个仓位的提交日志，StockTask:库存盘点任务日志，del.skuhiscostprice:台账删除历史成本价，del.combine:删除组合装资料，del.combinesku:删除子商品，del.itemsku:删除商品资料，del.purchaseitem:删除采购单明细，del.skuhisprice:删除历史成本价，del.category:删除类目，del.inoutapplyitem:删除其它出入库申请单明细，del.aftersaleitem:删除售后商品，del.itemsku_mapper:记录店铺商品资料删除WorkLog日志，del.inoutitem:进出仓单据明细删除日志 |
| types[] | string | 否 | "In",'MoveSku" |  |
| page_num | number | 否 |  | 第几页；从0页开始 |
| page_size | number | 否 |  | 分页大小；一页最大50条 |
| created_date_start | string | 是 |  | 日志开始时间 |
| created_date_end | string | 是 |  | 日志结束时间；默认查询前一天数据 |
| owner_co_id | number | 否 |  | 货主编码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| msg | string | 否 |  |  |
| code | string | 否 |  |  |
| request_id | string | 否 |  |  |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].creator | string | 否 |  | 创建人编号 |
| data[].pack_id | string | 否 |  | 箱号 |
| data[].created | string | 否 |  | 创建时间 |
| data[].bin | string | 否 |  | 仓位 |
| data[].autoid | string | 否 |  | 序号 |
| data[].co_id | number | 否 |  | 公司编码 |
| data[].sku_id | string | 否 |  | 商品编码 |
| data[].remark | string | 否 |  | 备注 |
| data[].type | string | 否 |  | 类型 |
| data[].id1 | string | 否 |  | 单据编码1 |
| data[].id2 | string | 否 |  | 单据编码2 |
| data[].qty | string | 否 |  | 数量 |
| data[].owner_co_id | number | 否 |  | 货主编码 |
| data[].s2 | string | 否 |  | 在type为"In"(入库)的情况下,记录的是采购单号； |

### 请求示例

```json
{
  "types": [],
  "created_date_end": "",
  "sku_ids": [],
  "owner_co_id": 0,
  "page_num": 0,
  "created_date_start": "",
  "page_size": 0
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": [
    {
      "creator": "",
      "pack_id": "",
      "created": "",
      "bin": "",
      "autoid": "",
      "co_id": 0,
      "sku_id": "",
      "remark": "",
      "type": "",
      "id2": "",
      "id1": "",
      "qty": "",
      "owner_co_id": 0,
      "s2": ""
    }
  ],
  "request_id": ""
}
```


### 异常示例

```json
{"code":0,"msg":"错误信息","request_id":"xxxxxx","data":{}/[]}
```


---

## 工作量补入

`/open/webapi/wmsapi/worklog/workloadappend`

| 项 | 内容 |
|---|---|
| 接口名称 | 工作量补入 |
| 接口路径 | `/open/webapi/wmsapi/worklog/workloadappend` |
| docType / docId | 22 / 154 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=154 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/worklog/workloadappend` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/worklog/workloadappend` |


### 接口说明

action_type不同要求不填的参数不同
 action_type为 0、1、3、4时，lid （快递单号）、oid（内部订单号）、wave_id（批次号） 三选一
action_type 为 2时为拣货补入，lid （快递单号）、oid（内部订单号）、 wave_id （批次号）、 po_id（ 加工单号 ） 四选一
 action_type 大于 5时为自定义名称补入，lid （快递单号）、oid（内部订单号）、 wave_id （批次号）、 po_id（ 加工单号） 、
 【商品编码（商品编码、国标码、辅助码、唯一码）、商品数量】五选一

 以上的几种情况的 wave_id 的值支持传入 （批次号或者快递单号）

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
| wave_id | number | 否 |  | 批次号 |
| lid | string | 否 | ZJS000352543542 | 快递单号 |
| last_lid | string | 否 |  | 最后一个快递单号 |
| po_id | number | 否 |  | 加工单号 |
| sku_sn_po_id | number | 否 |  | 快销采购单号 |
| oid | number | 否 |  | 内部订单号 |
| packer | string | 是 | 210095 | 操作人Id |
| packer_name | string | 是 | 白砂 | 操作人名称 |
| package_sku_id | string | 否 |  | 包材商品编码 |
| is_unlimited_express | boolean | 否 | false | 不限定快递 |
| sku_id | string | 否 |  | 商品编码 |
| sku_sn | string | 否 |  | 唯一码 |
| sku_num | number | 否 |  | 按商品补入数量 |
| is_combine | boolean | 否 | false | 是否组合装编码 |
| action_type | number | 是 | 0 | 补入类型 默认 为 0 打包登记（1：打包登记；2：拣货补入；3：验货补入；5：发货质检补入；大于5的 为 自定义补货） |
| area | string | 否 |  | 仓位区域 |
| ioid | number | 否 |  | 出库单号 |
| is_only_checked_inout | boolean | 否 | false | 是否只补入该批次已出库的出库单的拣货工作量 |
| tpw_selected_co_id | number | 否 | 0 | 第三方仓选中的商家 |
| is_allow_pack_before_deliver | boolean | 否 | false | 是否允许发货前打包登记 |
| is_cross_border | boolean | 否 | false | 是否跨境订单 |
| is_write_log_qty_by_machining_in_qty | boolean | 否 | false | 加工单补入是否按实际加工入库数量补入 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | object | 否 |  |  |
| data.message | string | 否 |  |  |
| data.success | boolean | 否 |  |  |

### 请求示例

```json
{
  "area": "",
  "packer": "210095",
  "is_cross_border": false,
  "package_sku_id": "",
  "sku_num": 0,
  "po_id": 0,
  "action_type": 0,
  "lid": "ZJS000352543542",
  "packer_name": "白砂",
  "is_combine": false,
  "is_write_log_qty_by_machining_in_qty": false,
  "sku_id": "",
  "sku_sn": "",
  "oid": 0,
  "sku_sn_po_id": 0,
  "ioid": "",
  "is_unlimited_express": false,
  "is_allow_pack_before_deliver": false,
  "last_lid": "",
  "is_only_checked_inout": false,
  "wave_id": 0,
  "tpw_selected_co_id": 0
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "success": true,
    "message": ""
  }
}
```


### 异常示例

_无_


---

## 查询快销唯一码信息

`/open/jushuitan/skusn/load`

| 项 | 内容 |
|---|---|
| 接口名称 | 查询快销唯一码信息 |
| 接口路径 | `/open/jushuitan/skusn/load` |
| docType / docId | 22 / 173 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=173 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/skusn/load` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/skusn/load` |


### 接口说明

【ERP界面】-【快销采购标签管理】
 默认排除了已发货的标签数据， 需要查所有except_status:[] 传空数组
 注意传参时需要传“排除标签状态”except_status字段时， 请选择下面的枚举项上传，请上传对应的枚举值
 None = 0,
 Pack = 1,
 Pick = 2,
 Pick1 = 21,
 Pick2 = 22,
 PickReturn = 23,
 /// 纸质拣货
 PaperPick = 24,
 Seed = 3,
 Checkout = 4,
 //WaitIn=5,
 Purchaseout = 6,
 Otherout = 7,
 /// 快销采购
 Purchase = 8,
 /// 外采播种
 PurchaseSeed = 9,
 /// 出库。发货装箱中唯一码非出库状态时，将修改成此状态
 Out = 16,
 /// 快销收货
 Receive = 32,
 /// 快销模式补货商品
 InStock = 33,
 /// 售后
 AfterSale = 64,
 Create = 98,
 Cancelled = 99,
 Purchase2 = 998,
 Printing = 999,
 WaitConfirm = 101,
 /// 待入库
 WaitPack = 102

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
| page_index | number | 是 |  | 第几页 |
| page_size | number | 是 |  | 页大小；默认30条，最大500条 |
| start_time | string | 否 |  | 创建开始时间 |
| end_time | string | 否 |  | 创建结束时间 |
| last_max_id | number | 否 |  | 上一页最大id |
| from_o_id | array | 否 |  | 来源订单；与时间查询条件不能同时为空 |
| from_o_id[] | number | 否 |  |  |
| so_id | array | 否 |  | 线上单号：最大限制100 |
| so_id[] | string | 否 |  |  |
| sku_sn | array | 否 |  | 快销标签，与时间条件不能同时为空 |
| sku_sn[] | string | 否 |  |  |
| except_status | array | 否 |  | 排除标签状态 |
| except_status[] | string | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | object | 否 |  |  |
| data.HasNext | boolean | 否 |  | 是否有下一页 |
| data.Items | array | 否 |  | 商品集合 |
| data.Items[] | object | 否 |  |  |
| data.Items[].SkuSn | string | 否 |  | 唯一码(快销采购标签) |
| data.Items[].SourceType | string | 否 |  | 货源类型：0未比较；1采购；2拣货；3仓内待检 |
| data.Items[].Gifts | array | 否 |  | 赠品数据 |
| data.Items[].Gifts[] | object | 否 |  |  |
| data.Items[].Gifts[].SkuId | string | 否 |  | 商品编码 |
| data.Items[].Gifts[].Qty | number | 否 |  | 数量 |
| data.Items[].ArrivalDate | string | 否 |  | 到货时间：有到货时有值，未到货则为空 |
| data.Items[].SendDate | string | 否 |  | 发货时间：发货订单有值 取发货订单的发货时间，发货订单无值时 未发货为空 |
| data.Items[].Area | string | 否 |  | 播种区：A、B、C、D |
| data.Items[].AreaBin | string | 否 |  | 播种柜号：多件柜号如3-1 |
| data.Items[].PKey | string | 否 |  | 订单类型（单，多） |
| data.Items[].ArriveNum | string | 否 |  | 已到货数：（包含本件） |
| data.Items[].LogisticsCompany | string | 否 |  | 物流公司 |
| data.Items[].MinPurchaseDate | string | 否 |  | 初次采购日期 |
| data.Items[].IsArrive | string | 否 |  | 是否已到货 |
| data.Items[].IsCanceled | string | 否 |  | 是否作废 |
| data.Items[].SkuId | string | 否 |  | 商品编码 |
| data.Items[].Qty | number | 否 |  | 数量 |
| data.Items[].FromOId | number | 否 |  | 内部订单号 |
| data.Items[].FromOiId | number | 否 |  | 内部订单明细号 |
| data.MaxId | number | 否 |  | 当前页最大id |
| code | string | 否 |  |  |
| issuccess | string | 否 |  |  |
| msg | string | 否 |  |  |

### 请求示例

```json
{
  "start_time": "",
  "page_index": 0,
  "end_time": "",
  "last_max_id": 0,
  "from_o_id": [],
  "except_status": [
    "9"
  ],
  "page_size": 0
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": {
    "MaxId": 0,
    "Items": [
      {
        "AreaBin": "",
        "SourceType": "",
        "ArriveNum": "",
        "IsArrive": "",
        "PKey": "",
        "FromOId": 0,
        "IsCanceled": "",
        "Area": "",
        "Qty": 0,
        "FromOiId": 0,
        "MinPurchaseDate": "",
        "SkuSn": "",
        "LogisticsCompany": "",
        "SkuId": ""
      }
    ],
    "HasNext": true
  },
  "issuccess": ""
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

## 跟踪信息查询

`/open/jushuitan/skusn/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 跟踪信息查询 |
| 接口路径 | `/open/jushuitan/skusn/query` |
| docType / docId | 22 / 252 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=252 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/skusn/query` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/skusn/query` |


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
| sku_sns | array | 否 |  | 唯一码列表 |
| sku_sns[] | string | 否 |  |  |
| io_ids | array | 否 |  | 出库单Id列表 |
| io_ids[] | string | 否 |  |  |
| wave_ids | array | 否 |  | 批次Id列表 |
| wave_ids[] | string | 否 |  |  |
| pack_ids | array | 否 |  | 箱号列表 |
| pack_ids[] | string | 否 |  |  |
| bins | array | 否 |  | 仓位列表 |
| bins[] | string | 否 | "A-1-1","A-2-1" |  |
| status | array | 否 |  | Pack:入库;Out:出库;Pick:拣货;Checkout:验货出库;Seed:播种;PickReturn:拣货归还;Pick1:一单一件拣货;Pick2:一单多件拣货; PaperPick:纸质拣货;WaitConfirm:待出库;WaitPack:待入库; |
| status[] | string | 否 |  |  |
| except_statuses | array | 否 |  | 排除状态 |
| except_statuses[] | string | 否 |  |  |
| is_except_no_batch | boolean | 否 |  | 是否排除没有生产批次的记录 |
| flds | array | 否 |  | array	查询属性(返回数据属性) |
| flds[] | string | 否 |  |  |
| page_index | number | 否 |  | 第几页 |
| page_size | number | 否 |  | 每页多少条 |
| modified_begin | string | 否 |  | 修改时间起始值;当sku_sns、io_ids、wave_ids、pack_ids、bins都没值时，修改时间必填且时间范围不超过7天 |
| modified_end | string | 否 |  | 修改时间截止值;起始时间和结束时间不能同时为空 |
| date_time | number | 否 |  | 时间类型；默认0：修改时间 |
| types | array | 否 |  | 唯一码类型（psd类型默认不返回，如需返回请传该字段），1:唯一码/序列号, 3:生产批次, 4:快销 |
| types[] | string | 否 |  |  |
| sku_ids | array | 否 |  | 商品编码，与时间条件，sku_sns、io_ids、o_ids、so_ids、wave_ids、pack_ids、bins不能同时为空 |
| sku_ids[] | string | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 否 |  |  |
| issuccess | string | 否 |  |  |
| msg | string | 否 |  |  |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].sku_sn | string | 否 |  | 唯一码 |
| data[].co_id | integer | 否 |  | 公司编号 |
| data[].sku_id | string | 否 |  | 商品编码 |
| data[].status | string | 否 |  | Pack:入库;Out:出库;Pick:拣货;Checkout:验货出库;Seed:播种;PickReturn:拣货归还;Pick1:一单一件拣货;Pick2:一单多件拣货; PaperPick:纸质拣货;WaitConfirm:待出库;WaitPack:待入库; |
| data[].wave_id | string | 否 |  | 批次Id |
| data[].io_id | string | 否 |  | 出库单Id |
| data[].bin | string | 否 |  | 仓位 |
| data[].modified | string | 否 |  | 修改时间 |
| data[].pack_id | string | 否 |  | 箱号 |
| data[].i_id | string | 否 |  | 款式编码 |
| data[].lc_id | string | 否 |  | 生产批次号 |
| data[].pay_date | string | 否 |  | 支付时间 |
| data[].sku_info | string | 否 |  | 商品信息 |
| data[].supplier_name | string | 否 |  | 供应商 |
| data[].print_date | string | 否 |  | 打印日期 |
| data[].created | string | 否 |  | 创建时间 |
| data[].creator | string | 否 |  | 创建人 |
| data[].wms_co_id | string | 否 |  | 分仓编号 |
| data[].shop_id | string | 否 |  | 店铺编号 |
| data[].remark | string | 否 |  | 备注 |
| data[].total_qty | string | 否 |  | 总数量 |
| data[].io_date | string | 否 |  | 批次生产效期 |
| data[].ioitem_index | string | 否 |  |  |
| data[].p_key | string | 否 |  | 唯一码类型：单采，单留 ，多拣，多留 |
| data[].po_id | string | 否 |  | 采购单号 |
| data[].prev_status | string | 否 |  |  |
| data[].qty | string | 否 |  | 数量 |
| data[].from_co_id | string | 否 |  |  |
| data[].push_status | string | 否 |  | 推送状态 |
| data[].print_task | string | 否 |  |  |
| data[].print_index | string | 否 |  | 打印序号 |
| data[].supplier_id | string | 否 |  | 供应商编号 |
| data[].supplier_i_id | string | 否 |  | 供应商款号 |
| data[].combine_sku_id | string | 否 |  | 组合装商品编码 |
| data[].o_id | string | 否 |  | 内部单号 |
| data[].inventory_status | string | 否 |  | 库存状态 |
| data[].expiration_date | string | 否 |  | 批次有效期 |
| data[].ts | string | 否 |  | 时间戳 |
| data[].type | string | 否 |  | 类型（序列号：SerialNumber 生产批批次：ProducedBatch ，快销采购：p2d） |
| data[].batch_id | string | 否 |  | 生产批次号（唯一码页签） |
| data[].produced_date | string | 否 |  | 生产日期 |

### 请求示例

```json
{
  "io_ids": [
    5576540
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "issuccess": "",
  "data": [
    {
      "i_id": "",
      "pay_date": "",
      "lc_id": "",
      "supplier_i_id": "",
      "po_id": "",
      "bin": "",
      "p_key": "",
      "remark": "",
      "expiration_date": "",
      "type": "",
      "inventory_status": "",
      "from_co_id": "",
      "ioitem_index": "",
      "print_task": "",
      "combine_sku_id": "",
      "wave_id": "",
      "o_id": "",
      "modified": "",
      "supplier_name": "",
      "creator": "",
      "push_status": "",
      "pack_id": "",
      "sku_info": "",
      "created": "",
      "io_date": "",
      "total_qty": "",
      "co_id": 0,
      "sku_sn": "",
      "sku_id": "",
      "sort": "",
      "io_id": "",
      "shop_id": "",
      "wms_co_id": "",
      "prev_status": "",
      "qty": "",
      "supplier_id": "",
      "status": "",
      "print_date": "",
      "print_index": "",
      "ts": ""
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

## 进出仓流水

`/open/jushuitan/inout/water/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 进出仓流水 |
| 接口路径 | `/open/jushuitan/inout/water/query` |
| docType / docId | 22 / 54 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=54 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/inout/water/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/inout/water/query` |


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
| page_index | integer | 否 | 1 | 页码 最大查询800页 |
| page_size | integer | 否 | 50 | 每页数据条数最多50 |
| start_time | string | 否 | 2021-10-2717:35:00 | 开始时间 |
| end_time | string | 否 | 2021-10-2717:40:00 | 结束时间 |
| date_type | integer | 否 | 0 | 默认0,0=修改时间;1=制单日期;2=出入库时间 |
| type | string | 否 | 销售退货 | 单据类型，采购进仓，采购退货，调拨出，调拨入，加工出仓，加工进仓，盘点，销售出仓，销售退货，其它出库，其它进仓，其它退货，结算，差异 |
| wms_co_id | integer | 否 |  | 分仓编号 |
| status | string | 否 |  | 状态 |
| sku_ids | array | 否 |  | 商品编码 ，最大支持30个 |
| sku_ids[] | string | 否 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| datas | object | 否 |  |  |
| datas.co_id | integer | 否 |  | 公司编号，调拨业务时代表发起方 |
| datas.wms_co_id | integer | 否 |  | 分仓编号，调拨业务时代表接收方 |
| datas.wh_id | integer | 否 |  | 仓库编号，主仓=1，销退仓=2，进货仓=3，次品仓=4 |
| datas.link_wh_id | integer | 否 |  | 调入/出仓的仓库编号，主仓=1，销退仓=2，进货仓=3，次品仓=4调拨业务 |
| datas.link_io_id | integer | 否 |  | 调入/出仓单号，调拨业务 |
| datas.shop_id | integer | 否 |  | 店铺编号，订单业务 |
| datas.io_id | integer | 否 |  | 进出仓单号 |
| datas.o_id | integer | 否 |  | 内部单号 |
| datas.created | string | 否 |  | 创建时间 |
| datas.modified | string | 否 |  | 修改时间 |
| datas.io_date | string | 否 |  | 进出仓日期 |
| datas.supplier_id | integer | 否 |  | 供应商ID,采购相关业务 |
| datas.status | string | 否 |  | 状态 |
| datas.stock_enabled | string | 否 |  | 是否使用库存 |
| datas.weight | number | 否 |  | 预估重量 |
| datas.f_weight | number | 否 |  | 实际重量 |
| datas.drp_co_name | string | 否 |  | 出库类型，其它出入库业务 |
| datas.remark | string | 否 |  | 备注 |
| datas.items | object | 否 |  |  |
| datas.items.ioi_id | integer | 否 |  | 商品明细ID |
| datas.items.sku_id | string | 否 |  | 商品编码 |
| datas.items.qty | integer | 否 |  | 数量 |
| datas.items.properties_value | string | 否 |  | 商品属性 |
| datas.items.r_qty | integer | 否 |  | 实际数量 |
| datas.items.qty_type | integer | 否 |  | 数量加减标识+1，-1 |
| datas.type | string | 否 |  | 单据类型 |
| msg | string | 否 | 执行成功 | 提示信息 |
| issuccess | string | 否 | true | 是否查询成功 |
| code | integer | 否 | 0 | 成功码，0代表成功 |
| has_next | boolean | 否 | false | 是否有下一页 |
| page_count | integer | 否 | 1 | 总页数 |
| data_count | integer | 否 | 11 | 查询到的总数据量 |
| page_index | integer | 否 | 1 | 页码 |
| page_size | integer | 否 | 50 | 每页数据条数 |

### 请求示例

```json
{
  "start_time": "2021-10-2717:35:00",
  "date_type": 0,
  "wms_co_id": 0,
  "page_index": 1,
  "end_time": "2021-10-2717:40:00",
  "type": "销售出仓",
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
        "created": "2026-08-30 12:04:48.450",
        "io_date": "2026-09-03 03:04:44.043",
        "link_wh_id": 1000,
        "co_id": 12717198,
        "f_weight": 0,
        "weight": 0.4,
        "drp_co_name": null,
        "remark": null,
        "type": "销售出仓",
        "link_io_id": null,
        "io_id": 6433143,
        "shop_id": 11111111,
        "wms_co_id": 11111111,
        "wh_id": 1,
        "so_id": "PO471330",
        "o_id": 6937614,
        "modified": "2026-09-03 03:04:44.130",
        "stock_enabled": "on",
        "supplier_id": null,
        "items": [
          {
            "qty_type": -1,
            "properties_value": "藕色 / 0XL",
            "qty": 1,
            "sku_id": "260011",
            "r_qty": null,
            "ioi_id": 11474558
          }
        ],
        "status": "Confirmed"
      }
    ],
    "page_index": 1,
    "has_next": true,
    "data_count": 6199,
    "page_count": 6199,
    "page_size": 1
  }
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

## 快销到货

`/open/jushuitan/quicksale/arrival`

| 项 | 内容 |
|---|---|
| 接口名称 | 快销到货 |
| 接口路径 | `/open/jushuitan/quicksale/arrival` |
| docType / docId | 22 / 436 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=436 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/quicksale/arrival` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/quicksale/arrival` |


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
| sku_sn | string | 是 |  | 唯一码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 |  |  |
| issuccess | string | 是 |  |  |
| msg | string | 是 |  |  |
| data | object | 是 |  |  |
| data.Status | string | 是 |  | 标签状态：有效、作废、非快销标签 |
| data.PKey | string | 是 |  | 订单类型（单，多） |
| data.Area | string | 是 |  | 播种区：A、B、C、D |
| data.AreaBin | string | 是 |  | 播种柜号：多件柜号如3-1 |
| data.ArriveNum | number | 是 |  | 已到货数：（包含本件） |
| data.UnArriveNum | number | 是 |  | 未到货数：（有效标签未到货数） |
| data.LogisticsCompany | string | 是 |  | 物流公司 |
| data.MinPurchaseDate | string | 是 |  | 初次采购日期 |
| data.IsArrive | boolean | 是 |  | 是否已到货 |

### 请求示例

```json
{
  "sku_sn": "22042843528K"
}
```


### 响应示例

```json
{
  "data": {
    "Status": 0,
    "Area": "A",
    "AreaBin": "8-1",
    "PKey": "多",
    "ArriveNum": 3,
    "UnArriveNum": 0,
    "LogisticsCompany": "德邦快递",
    "MinPurchaseDate": null,
    "IsArrive": false
  },
  "code": 0,
  "issuccess": true,
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

## 根据箱号查询箱内商品推荐仓位

`/open/webapi/wmsapi/openskubinquery/findskubin`

| 项 | 内容 |
|---|---|
| 接口名称 | 根据箱号查询箱内商品推荐仓位 |
| 接口路径 | `/open/webapi/wmsapi/openskubinquery/findskubin` |
| docType / docId | 22 / 450 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=22&docId=450 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/openskubinquery/findskubin` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/openskubinquery/findskubin` |


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
| pack_id | string | 是 |  |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  |  |
| msg | string | 是 |  |  |
| request_id | string | 是 |  |  |
| data | array | 是 |  |  |
| data[] | object | 否 |  |  |
| data[].sku_id | string | 是 |  | 商品编码 |
| data[].bin | string | 是 |  | 仓位 |

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
