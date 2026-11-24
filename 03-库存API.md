# 聚水潭开放平台 · 库存API（线下版）

> 抓取日期：2026-11-23  
> 分类：库存API（docType=3）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=3&docId=15

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 商品库存查询 | `/open/inventory/query` | 15 | [打开](https://openweb.jushuitan.com/dev-doc?docType=3&docId=15) |
| 库存盘点查询 | `/open/inventory/count/query` | 16 | [打开](https://openweb.jushuitan.com/dev-doc?docType=3&docId=16) |
| 库存盘点-修改库存 | `/open/jushuitan/inventoryv2/upload` | 85 | [打开](https://openweb.jushuitan.com/dev-doc?docType=3&docId=85) |
| 导入/更新虚拟库存 | `/open/webapi/itemapi/iteminventory/batchupdatewmsvirtualqtys` | 631 | [打开](https://openweb.jushuitan.com/dev-doc?docType=3&docId=631) |
| 箱及仓位库存批量查询 | `/open/webapi/wmsapi/pack/pagequerypackanditems` | 1125 | [打开](https://openweb.jushuitan.com/dev-doc?docType=3&docId=1125) |
| 唯一码库存查询 | `/open/webapi/wmsapi/skusn/queryskusnstocks` | 1645 | [打开](https://openweb.jushuitan.com/dev-doc?docType=3&docId=1645) |

## 目录

- [商品库存查询](#商品库存查询)
- [库存盘点查询](#库存盘点查询)
- [库存盘点-修改库存](#库存盘点-修改库存)
- [导入/更新虚拟库存](#导入更新虚拟库存)
- [箱及仓位库存批量查询](#箱及仓位库存批量查询)
- [唯一码库存查询](#唯一码库存查询)

---

## 商品库存查询

`/open/inventory/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 商品库存查询 |
| 接口路径 | `/open/inventory/query` |
| docType / docId | 3 / 15 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=3&docId=15 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/inventory/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/inventory/query` |


### 接口说明

系统相关界面：【库存】------【商品库存】
按照 修改时间，商品编码 升序输出

 关于商品库存各库存数含义解释：
 主仓实际库存： 商品在仓库中的实物库存数量（可以用于发货的数量）
 库存锁定数： 可以把库存锁定给对应的店铺或者链接使用
 订单占有数： 当客户下订单后，客户订单锁定的商品库存数量
 安全库存： 客户设置安全库存数量（可以用于库存提醒和计划采购）
 仓库待发数： 订单审核通过在发货中的数量
 采购在途数： 采购单生效的商品还没有入库的商品数量
 虚拟库存： 可以正负,用于虚加库存用来同步线上或锁定一部分库存不同步线上.实际同步线上库存数=主仓实际库存-订单占有数+虚拟库存
 可用数： 可用数[同步线上的库存数]=主仓实际库存-订单占有数+虚拟库存数+采购在途(业务设置)+进货仓(业务设置)+销退仓库存(业务设置)
 订单可配货数： 可配货库存=主仓实际库存-仓库待发数
 公有可用数： 主仓实际库存-订单占有数-库存锁定数+虚拟库存(业务配置)-虚拟仓可用数=公有可用数
 说明： 如果在开通分仓的情况下分仓的主仓库存会同时显示在主仓的商品库存界面，主仓实际库存=分仓库存+主仓库存（如果需要分开查看可以去商品库存（分仓）查看）
 更多库存api相关问题参见常见问题文档： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=16&currentPage=1&pageSize=20

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
| wms_co_id | integer | 否 | 0 | 分仓公司编号，值不传或为0查询所有仓的总库存，传值为指定仓的库存即为库存查询（分仓）界面的数据；编号查询：https://openweb.jushuitan.com/dev-doc?docType=1&docId=3 |
| page_index | integer | 是 | 1 | 第几页，从1开始 |
| page_size | integer | 是 | 30 | 默认30，最大不超过100 |
| modified_begin | string | 否 | 2021-12-02 00:00:06 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天 |
| modified_end | string | 否 | 2021-12-09 00:00:06 | 修改结束时间，和结束时间必须同时存在，时间间隔不能超过七天 |
| sku_ids | string | 否 | JST20211111003ABC,100890 | 商品编码 多个用逗号分隔，与修改时间不能同时为空,最大不超过100个 |
| has_lock_qty | boolean | 否 |  | 是否查询库存锁定数 |
| names | string | 否 | A1,A2,A3 | 商品名称 最多100个，多个商品名称用逗号隔开 |
| i_ids | string | 否 | A1,A2,A3 | 款式编码 |
| ts | integer | 否 |  | 时间戳，防漏单，如果用ts查询不需要传时间查询条件 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  |  |
| data.page_size | integer | 否 | 2 | 每页多少条 |
| data.page_index | integer | 否 | 1 | 第几页 |
| data.has_next | boolean | 否 | false | 是否有下一页（如果按ts查询数据 不做汇总并且has_nest=false，需要通过data节点的数据最大ts值判断是否需要继续请求下一页） |
| data.inventorys | array | 否 |  | 数据集合 |
| data.inventorys[] | object | 否 |  |  |
| data.inventorys[].sku_id | string | 是 | 1000000000202 | 商品编码 |
| data.inventorys[].ts | integer | 是 |  | 时间戳 |
| data.inventorys[].i_id | string | 否 | 1000000000202 | 款式编码 |
| data.inventorys[].qty | integer | 否 | 313 | 主仓实际库存 |
| data.inventorys[].order_lock | integer | 否 | 309 | 订单占有数 |
| data.inventorys[].pick_lock | integer | 否 |  | 仓库待发数 |
| data.inventorys[].virtual_qty | integer | 否 | 0 | 虚拟库存 |
| data.inventorys[].purchase_qty | integer | 否 | 0 | 采购在途数 |
| data.inventorys[].return_qty | integer | 否 |  | 销退仓库存 |
| data.inventorys[].in_qty | integer | 否 |  | 进货仓库存 |
| data.inventorys[].defective_qty | integer | 否 |  | 次品库存（如需次品库存变更时修改时间同时更新需联系客服开通基数设置开关：次品仓、自定义仓库存变动修改商品库存修改时间） |
| data.inventorys[].modified | string | 否 | 2016-11-09 08:50:54 | 修改时间,用此时间作为下一次查询的起始时间 |
| data.inventorys[].min_qty | integer | 否 | 3 | 安全库存下限 |
| data.inventorys[].max_qty | integer | 否 | 10 | 安全库存上限 |
| data.inventorys[].lock_qty | integer | 否 |  | 库存锁定数（是否返回取决于入参时has_lock_qty字段） |
| data.inventorys[].name | string | 否 |  | 商品名称 |
| data.inventorys[].customize_qty_1 | integer | 否 |  | 自定义仓1（如需自定义仓库存变更时修改时间同时更新需联系客服开通基数设置开关：次品仓、自定义仓库存变动修改商品库存修改时间） |
| data.inventorys[].customize_qty_2 | integer | 否 |  | 自定义仓2（如需自定义仓库存变更时修改时间同时更新需联系客服开通基数设置开关：次品仓、自定义仓库存变动修改商品库存修改时间） |
| data.inventorys[].customize_qty_3 | integer | 否 |  | 自定义仓3（如需自定义仓库存变更时修改时间同时更新需联系客服开通基数设置开关：次品仓、自定义仓库存变动修改商品库存修改时间） |
| data.inventorys[].allocate_qty | integer | 否 |  | 调拨在途数 |
| data.inventorys[].sale_refund_qty | number | 否 |  | 销退在途数（默认不返回需要联系我们开配置） |

### 请求示例

```json
{
  "wms_co_id": 0,
  "sku_ids": "JST20211111003ABC,100890",
  "names": "A1,A2,A3",
  "page_index": 1,
  "modified_begin": "2021-12-02 00:00:06",
  "modified_end": "2021-12-09 00:00:06",
  "has_lock_qty": true,
  "page_size": 30
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {
    "inventorys": [
      {
        "i_id": "1000000000202",
        "purchase_qty": 0,
        "min_qty": 3,
        "allocate_qty": 0,
        "sku_id": "1000000000202",
        "virtual_qty": 0,
        "customize_qty_3": 0,
        "order_lock": 309,
        "max_qty": 10,
        "customize_qty_1": 0,
        "customize_qty_2": 0,
        "pick_lock": 0,
        "lock_qty": 0,
        "qty": 313,
        "name": "",
        "modified": "2016-11-09 08:50:54",
        "sale_refund_qty": 0,
        "in_qty": 0,
        "defective_qty": 0,
        "return_qty": 0,
        "ts": 0
      }
    ],
    "page_index": 1,
    "has_next": false,
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

## 库存盘点查询

`/open/inventory/count/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 库存盘点查询 |
| 接口路径 | `/open/inventory/count/query` |
| docType / docId | 3 / 16 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=3&docId=16 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/inventory/count/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/inventory/count/query` |


### 接口说明

系统相关界面：【库存】------【库存盘点】

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
| page_index | integer | 否 | 1 | 第几页，从第一页开始，默认1 |
| page_size | integer | 否 | 30 | 每页多少条，默认30，最大50。不要大于50，如果超过了虽然请求不会报错，但是会影响返回的page_count，导致数据查询不全。 |
| modified_begin | string | 否 | 2021-12-02 00:00:00 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与盘点单号不能同时为空 |
| modified_end | string | 否 | 2021-12-09 00:00:00 | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与盘点单号不能同时为空 |
| io_ids | string | 否 | 3535290,3539256 | 指定盘点单号 多个用逗号分隔，最多50，和时间段不能同时为空 |
| status | string | 否 | Confirmed | 状态;WaitConfirm:待确认,Confirmed:生效,Archive:归档,Cancelled:取消,Delete:作废 |
| owner_co_id | integer | 否 |  | 货主编码（三方仓商家不传货主默认查自身数据，若查所有货主需传值：2147483647） |

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
| data.datas[].type | string | 否 | 盘点 | 单据类型 |
| data.datas[].io_id | integer | 否 | 805097 | 盘点单号 |
| data.datas[].io_date | string | 否 | 2021-04-1313:52:54 | 单据日期 |
| data.datas[].status | string | 否 | Confirmed | 状态;WaitConfirm:待确认,Confirmed:生效,Archive:归档,Cancelled:取消,Delete:作废 |
| data.datas[].warehouse | string | 否 | JP主仓 | 仓库名称 |
| data.datas[].creator_name | string | 否 | 开发测试-开放平台 | 创建人 |
| data.datas[].remark | string | 否 |  | 备注 |
| data.datas[].wh_id | integer | 否 | 1 | 仓库编号，主仓=1，销退仓=2，进货仓=3，次品仓=4 |
| data.datas[].wms_co_id | integer | 否 | 12252 | 分仓编号 |
| data.datas[].modified | string | 否 | 2021-04-1313:52:54 | 修改时间 |
| data.datas[].items | array | 否 |  | 商品集合 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].io_id | integer | 否 | 805097 | 盘点单号 |
| data.datas[].items[].ioi_id | integer | 否 | 1649226 | 子单号 |
| data.datas[].items[].sku_id | string | 否 | #JLJS_100 | 商品编码 |
| data.datas[].items[].i_id | string | 否 |  | 款式编码 |
| data.datas[].items[].name | string | 否 | 20215088喷绘连衣裙560191-颜色:绿色;尺寸:XL; | 商品名称 |
| data.datas[].items[].properties_value | string | 否 | 颜色:绿色;尺寸:XL; | 颜色及规格 |
| data.datas[].items[].r_qty | integer | 否 | 20 | 盘点后数量 |
| data.datas[].items[].qty | integer | 否 | 10 | 盈亏数量 |
| data.datas[].items[].batch_id | string | 否 | 20211103 | 批次号，等于batch_no，获取该字段系统中相关业务项需配置 |
| data.datas[].items[].product_date | string | 否 | 2021-11-03 00:00:00 | 批次日期，系统中相关业务项需配置 |
| data.datas[].items[].supplier_id | integer | 否 | 4761453 | 供应商编号，系统中相关业务项需配置 |
| data.datas[].items[].expiration_date | string | 否 | 2021-11-30 00:00:00 | 有效期至，系统中相关业务项需配置 |
| data.datas[].batchs | array | 否 |  | 批次集合，获取该节点系统中相关业务项需配置 |
| data.datas[].batchs[] | object | 否 |  |  |
| data.datas[].batchs[].batch_no | string | 否 |  | 批次号 |
| data.datas[].batchs[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].batchs[].qty | integer | 否 |  | 数量 |
| data.datas[].batchs[].product_date | string | 否 |  | 批次日期 |
| data.datas[].batchs[].supplier_id | integer | 否 |  | 供应商编号 |
| data.datas[].batchs[].supplier_name | string | 否 |  | 供应商名称 |
| data.datas[].batchs[].expiration_date | string | 否 |  | 有效期至 |
| data.datas[].batchs[].ioi_id | string | 否 |  | 子单号 |
| data.datas[].sns | array | 否 |  | 唯一码集合，获取该节点系统中相关业务项需配置 |
| data.datas[].sns[] | object | 否 |  |  |
| data.datas[].sns[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].sns[].sn | string | 否 |  | 唯一码 |
| data.datas[].sns[].qty | number | 否 |  | 盈亏数 |
| data.datas[].f_status | string | 否 |  | 财审状态，WaitConfirm=待审核;Confirmed=已审核 |
| data.datas[].lock_wh_id | number | 否 |  | 虚拟仓编码 |
| data.datas[].lock_wh_name | string | 否 |  | 虚拟仓名称 |
| data.datas[].labels | string | 否 |  | 标记\|多标签 |

### 请求示例

```json
{
  "page_index": 1,
  "modified_begin": "2021-12-02 00:00:00",
  "modified_end": "2021-12-09 00:00:00",
  "io_ids": "3535290,3539256",
  "page_size": 30,
  "status": "Confirmed"
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
        "batchs": [
          {
            "batch_no": "",
            "qty": 0,
            "sku_id": "",
            "supplier_name": "",
            "expiration_date": "",
            "supplier_id": 0,
            "product_date": ""
          }
        ],
        "wms_co_id": 12252,
        "wh_id": 1,
        "io_date": "2021-04-1313:52:54",
        "modified": "2021-04-1313:52:54",
        "creator_name": "开发测试-开放平台",
        "remark": "",
        "type": "盘点",
        "warehouse": "JP主仓",
        "items": [
          {
            "properties_value": "颜色:绿色;尺寸:XL;",
            "qty": 10,
            "name": "20215088喷绘连衣裙560191-颜色:绿色;尺寸:XL;",
            "sku_id": "#JLJS_100",
            "r_qty": 20,
            "ioi_id": 1649226,
            "io_id": 805097
          }
        ],
        "io_id": 805097,
        "status": "Confirmed"
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

## 库存盘点-修改库存

`/open/jushuitan/inventoryv2/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 库存盘点-修改库存 |
| 接口路径 | `/open/jushuitan/inventoryv2/upload` |
| docType / docId | 3 / 85 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=3&docId=85 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/inventoryv2/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/inventoryv2/upload` |


### 接口说明

系统相关界面：【库存】------【库存盘点】
 注意点：
 1.获取分仓编码可以通过该接口查询  https://open.jushuitan.com/document/2064.html
 2.当商品库存没有变动传入时，会校验盘点商品的差异商品量，如果盘点商品数量与原商品数量没有差异时，则不创建盘点记录
 3.接口batch_id批次号字段支持/,@,.,-,汉字格式 这些特殊字符
 更多库存api相关问题参见常见问题文档： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=16&currentPage=1&pageSize=20

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
| wms_co_id | integer | 否 | 10158015 | 仓库编码，不填写默认主仓 |
| type | string | 否 | check | 盘点类型 :非精细化盘点 ，全量:check （覆盖，传哪个商品覆盖哪个商品库存，没有传的商品库存不变）;增量:adjust(默认adjust，在原基础数量上增加) ；精细化仓位盘点，type=check，为全量盘点，仓位上未传的商品库存盘为0；type=adjust，为增量盘点，未传的商品库存不盘点，传的数量做增量盘点，如盘前库存=10，传参数量=2，则盘点后库存为10+2=12 |
| is_confirm | boolean | 否 |  | 是否自动确认单据；默认false |
| so_id | string | 是 | 20220617 | 外部单号 （自定义传唯一值不可重复传，以第一次传成功的结果为准） |
| warehouse | string | 是 | 1 | 仓库;主仓=1，销退仓=2， 进货仓=3，次品仓 = 4,自定义1仓=6，自定义2仓=7，自定义3仓=8 |
| lock_wh_id | number | 否 |  | 运营云仓编码 |
| lock_wh_name | string | 否 |  | 运营云仓名称 |
| remark | string | 否 |  | 备注 |
| bin | string | 否 | A-1-1 | 仓位(开启精细化管理有效且必填） |
| default_type | string | 否 |  | 暂存位类型（开启精细化管理有效且必填可传值Default（暂存位），Pick（拣货暂存位）,None） |
| items | array | 是 |  | 商品明细，最大500 |
| items[] | object | 否 |  |  |
| items[].qty | integer | 是 |  | 数量 |
| items[].sku_sns | array | 否 |  | 唯一码集合,如果type = adjust 不支持传sn会报错增量盘点不支持传唯一码 |
| items[].sku_sns[] | string | 否 |  |  |
| items[].sku_id | string | 是 | 001 | 商品编码 |
| items[].supplier_id | number | 否 |  | 供应商编码 |
| items[].batch_id | string | 否 |  | 批次号；如果开启商品批次开关，批次信息必填 |
| items[].produced_date | string | 否 |  | 生产日期（时间范围1970-01-01 00:00:00-3000-01-01 00:00:00） |
| items[].expiration_date | string | 否 |  | 有效期（时间范围1970-01-01 00:00:00-3000-01-01 00:00:00） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 状态码；0表示成功 |
| issuccess | boolean | 否 |  | 执行结果 |
| msg | string | 是 | 执行成功 | 执行结果描述信息 |
| data | object | 是 |  |  |
| data.data | object | 是 |  |  |
| data.data.msg | string | 是 |  | 执行结果 |
| data.data.so_id | string | 是 |  | 外部单号 |
| data.data.io_id | number | 是 |  | 盘点单号 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 130 | "msg": "批次号格式不正确" |  |
| 150 | "msg": "内部异常：Transaction (Process ID 364) was deadlocked on lock resources  with another process and has been chosen as the deadlock victim. Rerun the transaction." |  |
| 140 | "msg": "验证失败！appkey无效" |  |


### 请求示例

```json
{
  "wms_co_id": 10158015,
  "is_confirm": true,
  "so_id": "20220617",
  "bin": "A-1-1",
  "default_type": "",
  "remark": "",
  "type": "check",
  "warehouse": "1",
  "items": [
    {
      "batch_id": "",
      "sku_sns": [],
      "qty": 0,
      "sku_id": "001",
      "expiration_date": "",
      "supplier_id": 0,
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
  "issuccess": true,
  "data": {
    "data": {
      "msg": "",
      "so_id": "",
      "io_id": 0
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

## 导入/更新虚拟库存

`/open/webapi/itemapi/iteminventory/batchupdatewmsvirtualqtys`

| 项 | 内容 |
|---|---|
| 接口名称 | 导入/更新虚拟库存 |
| 接口路径 | `/open/webapi/itemapi/iteminventory/batchupdatewmsvirtualqtys` |
| docType / docId | 3 / 631 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=3&docId=631 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/iteminventory/batchupdatewmsvirtualqtys` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/iteminventory/batchupdatewmsvirtualqtys` |


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
| wms_co_id | number | 是 | 10160280 | 分仓编码 |
| sku_and_qty | array | 是 |  |  |
| sku_and_qty[] | object | 否 |  | 最多1000条商品明细 |
| sku_and_qty[].sku_id | string | 是 |  | 商品编码 |
| sku_and_qty[].qty | number | 是 |  | 商品数量 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 |  |  |
| msg | string | 是 |  |  |
| data | string | 是 |  |  |

### 请求示例

```json
{
  "wms_co_id": 10160280,
  "sku_and_qty": [
    {
      "qty": 0,
      "sku_id": ""
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": ""
}
```


### 异常示例

_无_


---

## 箱及仓位库存批量查询

`/open/webapi/wmsapi/pack/pagequerypackanditems`

| 项 | 内容 |
|---|---|
| 接口名称 | 箱及仓位库存批量查询 |
| 接口路径 | `/open/webapi/wmsapi/pack/pagequerypackanditems` |
| docType / docId | 3 / 1125 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=3&docId=1125 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/pack/pagequerypackanditems` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/pack/pagequerypackanditems` |


### 接口说明

（ 移货、盘点、下架这三个操作产生的0库存数据记录，系统中会直接删除 ）
 全量拉取数据----pack_item_id_begin的用法示例：
 第一次请求：入参pack_item_id_begin：1；page_size:100
 第二次请求：入参pack_item_id_begin：（第一次请求返回的最大pack_item_id_begin值(最后一个)）；page_size:100
 第三次请求：入参pack_item_id_begin：（第二次请求返回的最大pack_item_id_begin值(最后一个)）；page_size:100
 以此类推..请求到接口只返回一条数据且该数据的pack_item_id和入参pack_item_id_begin一致（请求到接口不返回数据代表全部获取完毕）
 该字段用于全量拉取数据使用不支持搭配时间参数以及其他参数条件入参，只需要搭配page_size字段请求即可

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
| page_index | integer | 否 | @integer | 页码，默认第一页 |
| page_size | integer | 否 | @integer | 单页条数，最多500 |
| sku_ids | array | 否 |  | 商品编码（与修改时间，pack_item_id_begin 不能同时为空） |
| sku_ids[] | string | 否 | @string |  |
| wms_co_id | integer | 否 | @integer | 仓储方，默认为授权账号 |
| owner_co_id | integer | 否 | @integer | 货主 |
| pack_type | string | 否 | @string | 仓位类型。 Bin=仓位库存，DefaultPack=暂存位 Pack=装箱库存 |
| modified_begin | string | 否 |  | 开始修改时间（与pack_item_id_begin，sku_ids能不能同时为空） |
| modified_end | string | 否 |  | 结束修改时间（与pack_item_id_begin，sku_ids能不能同时为空） |
| is_load_all_wms  | boolean | 否 |  | 是否查询全仓，如false,wms_co_id返回null |
| pack_item_id_begin | number | 否 |  | 自增序列号（用于全量拉取数据使用，不支持结合时间条件使用，与修改时间，sku_ids能不能同时为空） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.page_index | number | 否 | @integer | 当前页码 |
| data.page_size | number | 否 | @integer | 当前单页大小 |
| data.data_count | number | 否 | @integer | 数据总条数 |
| data.page_count | number | 否 | @integer | 总页数 |
| data.has_next | boolean | 否 | @boolean | 是否有下一页 |
| data.data | array | 否 |  | 数据 |
| data.data[] | object | 否 |  |  |
| data.data[].pack_id | string | 是 |  | 箱号 |
| data.data[].pack_item_id | number | 是 |  | 自增序列号 |
| data.data[].wh_id | number | 是 |  | 仓库 |
| data.data[].pack_type | string | 是 |  | 仓位类型 |
| data.data[].bin | string | 是 |  | 仓位 |
| data.data[].bin_group | null | 是 |  | 仓位分组 |
| data.data[].sku_id | string | 是 |  | 商品编码 |
| data.data[].qty | number | 是 |  | 数量 |
| data.data[].batch_id | string | 是 |  | 生产批次号 |
| data.data[].supplier_id | number | 是 |  | 供应商 |
| data.data[].produced_date | null | 是 |  | 生产日期 |
| data.data[].expiration_date | null | 是 |  | 到期日 |
| data.data[].wms_co_id | number | 是 |  | 分仓编码 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "pack_type": "@string",
  "sku_ids": [],
  "page_index": "@integer",
  "owner_co_id": "@integer",
  "wms_co_id": "@integer",
  "page_size": "@integer"
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
        "pack_type": "",
        "pack_id": "",
        "batch_id": "",
        "bin": "",
        "qty": 0,
        "wh_id": 0,
        "sku_id": "",
        "expiration_date": "",
        "supplier_id": 0,
        "bin_group": "",
        "produced_date": ""
      }
    ],
    "page_index": "@integer",
    "has_next": "@boolean",
    "data_count": "@integer",
    "page_count": "@integer",
    "page_size": "@integer"
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 唯一码库存查询

`/open/webapi/wmsapi/skusn/queryskusnstocks`

| 项 | 内容 |
|---|---|
| 接口名称 | 唯一码库存查询 |
| 接口路径 | `/open/webapi/wmsapi/skusn/queryskusnstocks` |
| docType / docId | 3 / 1645 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=3&docId=1645 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/skusn/queryskusnstocks` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/skusn/queryskusnstocks` |


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
| page_index | number | 否 | 1 |  |
| page_size | number | 否 | 500 |  |
| sku_ids | array | 否 |  | 商品编码 最多200个 |
| sku_ids[] | string | 否 | @string |  |
| sku_sns | array | 否 |  | 唯一码 最多1000个 |
| sku_sns[] | string | 否 | @string |  |
| supplier_names | array | 否 |  | 供应商 最多50个 |
| supplier_names[] | string | 否 | @string |  |
| wms_co_ids | array | 否 |  | 仓储方 最多50个 |
| wms_co_ids[] | integer | 否 | @natural |  |
| created_begin | string | 否 | @datetime | 创建开始时间 |
| created_end | string | 否 | @datetime | 创建结束时间 |
| modified_begin | string | 否 | @datetime | 修改开始时间 |
| modified_end | string | 否 | @datetime | 修改结束时间 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| act | number | 否 |  |  |
| data | object | 否 |  |  |
| data.page_index | number | 否 |  |  |
| data.page_size | number | 否 |  |  |
| data.has_next | boolean | 否 |  | 是否有下一页 |
| data.last_sku_sn | string | 否 |  | 上一页最后的唯一码 |
| data.datas | array | 否 |  |  |
| data.datas[] | object | 否 |  |  |
| data.datas[].sku_id | string | 是 |  | 商品编码 |
| data.datas[].sku_name | string | 是 |  | 商品名称 |
| data.datas[].properties_value | string | 是 |  | 颜色规格 |
| data.datas[].i_id | string | 是 |  | 款式编码 |
| data.datas[].category_name | string | 是 |  | 分类 |
| data.datas[].sku_sn | string | 是 |  | 唯一码 |
| data.datas[].qty | number | 是 |  | 数量 |
| data.datas[].remark | string | 是 |  | 备注 |
| data.datas[].in_remark | string | 是 |  | 原始入库备注 |
| data.datas[].supplier_id | integer | 是 |  | 供应商ID |
| data.datas[].supplier_name | string | 是 |  | 供应商 |
| data.datas[].wms_co_id | number | 是 |  | 仓储方id |
| data.datas[].wms_co_name | string | 是 |  | 仓储方 |
| data.datas[].wh_id | integer | 是 |  | 仓库id |
| data.datas[].wh_name | string | 是 |  | 仓库 |
| data.datas[].bin | string | 是 |  | 仓位 |
| data.datas[].created | string | 是 |  | 创建时间 |
| data.datas[].modified | string | 是 |  | 结束时间 |
| msg | null | 否 |  |  |
| msg_type | string | 否 |  |  |
| request_id | null | 否 |  |  |
| cookie | null | 否 |  |  |

### 请求示例

```json
{
  "wms_co_ids": [],
  "created_end": "@datetime",
  "sku_ids": [],
  "sku_sns": [],
  "page_index": 1,
  "modified_begin": "@datetime",
  "supplier_names": [],
  "modified_end": "@datetime",
  "created_begin": "@datetime",
  "page_size": 500
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "act": 0,
  "data": {
    "datas": [
      {
        "i_id": "",
        "category_name": "",
        "bin": "",
        "created": "",
        "sku_id": "",
        "sku_sn": "",
        "remark": "",
        "wh_name": "",
        "properties_value": "",
        "wms_co_id": 0,
        "wh_id": 0,
        "qty": 0,
        "in_remark": "",
        "modified": "",
        "sku_name": "",
        "supplier_name": "",
        "supplier_id": 0,
        "wms_co_name": ""
      }
    ],
    "page_index": 0,
    "has_next": true,
    "last_sku_sn": "",
    "page_size": 0
  },
  "cookie": "",
  "msg_type": "",
  "request_id": ""
}
```


### 异常示例

_无_


---
