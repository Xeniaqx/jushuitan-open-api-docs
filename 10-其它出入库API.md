# 聚水潭开放平台 · 其它出入库API（线下版）

> 抓取日期：2026-11-23  
> 分类：其它出入库API（docType=10）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=10&docId=42

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 其它出入库查询 | `/open/other/inout/query` | 42 | [打开](https://openweb.jushuitan.com/dev-doc?docType=10&docId=42) |
| 新建其它出入库 | `/open/jushuitan/otherinout/upload` | 43 | [打开](https://openweb.jushuitan.com/dev-doc?docType=10&docId=43) |
| 其它出入库状态变更 | `/open/jushuitan/otherinout/cancel` | 223 | [打开](https://openweb.jushuitan.com/dev-doc?docType=10&docId=223) |

## 目录

- [其它出入库查询](#其它出入库查询)
- [新建其它出入库](#新建其它出入库)
- [其它出入库状态变更](#其它出入库状态变更)

---

## 其它出入库查询

`/open/other/inout/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 其它出入库查询 |
| 接口路径 | `/open/other/inout/query` |
| docType / docId | 10 / 42 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=10&docId=42 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/other/inout/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/other/inout/query` |


### 接口说明

系统相关界面：【库存】------【其它出入库(非订单)】

 请求参数中start_ts的说明 ：
 使用ts的查询条件是唯一可避免分页查询过程中因数据变动而导致的漏单问题，原因是该查询条件是数据库中的时间戳，sql server中的 行版本号 。只要当前这条数据在数据库中有变化任何字段变化ts的值都会自增，全表唯一的自增值，非业务上做的时间值更新。使用ts的查询模板
 第一次请求：{" start_ts ":1," is_get_total ":false," page_index ":1," page_size ":100} //第一次请求ts从1开始
 第二次请求：{" start_ts ":传第一次返回的最大ts值," is_get_total ":false," page_index ":1," page_size ":100} //一直请求到查不到比入参ts值本身更大的数据为止。只有start_ts值是变量，其它3个参数值不变
 更多其它出入库API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=23&currentPage=1&pageSize=20

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
| modified_begin | string | 否 | 2021-12-03 00:00:00 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空 |
| modified_end | string | 否 | 2021-12-10 00:00:00 | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空 |
| so_ids | array | 否 |  | 指定线上订单号，和时间段不能同时为空，，最多50个 |
| so_ids[] | string | 否 |  |  |
| types | array | 否 |  | 单据类型:其它退货,其它出库,其它进仓 |
| types[] | string | 否 |  |  |
| status | string | 否 |  | 单据状态，Confirmed生效，Confirming已确认，WaitConfirm待审核，OuterConfirming外部确认中，Cancelled取消（单据生效后的作废），Delete作废（单据生效前的作废） |
| page_index | integer | 否 | 1 | 第几页，从第一页开始，默认1 |
| page_size | integer | 否 | 30 | 每页多少条，默认30，最大50 |
| wms_co_id | integer | 否 |  | 分仓编号 |
| io_ids | array | 否 |  | 出仓单号列表，最多50个 |
| io_ids[] | number | 否 |  |  |
| date_type | number | 否 |  | 0:修改时间，modified。 2:出入库时间 io_date，未传入时默认为0 |
| start_ts | integer | 否 |  | 时间戳，sql server中的行版本号，该字段查询防止分页过程中漏单,如果使用时间戳查询只需要跟分页条件共用 其它条件都不传 |
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
| data.datas[].io_id | integer | 否 | 809069 | 出仓单号 |
| data.datas[].io_date | string | 否 | 2021-04-16 11:31:43 | 单据日期 |
| data.datas[].status | string | 否 | WaitConfirm | 单据状态，Confirmed生效，Confirming已确认，WaitConfirm待审核，OuterConfirming外部确认中，Cancelled取消（单据生效后的作废），Delete作废（单据生效前的作废） |
| data.datas[].so_id | string | 否 |  | 线上单号 |
| data.datas[].type | string | 否 | 其它出库 | 单据类型 |
| data.datas[].f_status | string | 否 |  | 财务状态 |
| data.datas[].warehouse | string | 否 | JP主仓 | 仓库名称 |
| data.datas[].receiver_name | string | 否 |  | 收货人 |
| data.datas[].receiver_mobile | string | 否 |  | 收货人手机 |
| data.datas[].receiver_state | string | 否 |  | 收货人省 |
| data.datas[].receiver_city | string | 否 |  | 收货人市 |
| data.datas[].receiver_district | string | 否 |  | 收货人区 |
| data.datas[].receiver_address | string | 否 |  | 收货人地址 |
| data.datas[].wh_id | integer | 否 | 1 | 仓库编号；主仓=1，销退仓=2，进货仓=3，次品仓=4，自定义1仓=6，自定义2仓=7，自定义3仓=8 |
| data.datas[].remark | string | 否 |  | 备注 |
| data.datas[].modified | string | 否 | 2021-04-16 11:31:43 | 修改时间 |
| data.datas[].created | string | 否 |  | 创建时间 |
| data.datas[].labels | string | 否 |  | 多标签 |
| data.datas[].wms_co_id | integer | 否 | 12252 | 分仓编号 |
| data.datas[].creator_name | string | 否 | 开发测试-开放平台 | 创建人 |
| data.datas[].wave_id | number | 否 |  | 拣货批次号 |
| data.datas[].drop_co_name | string | 否 |  | 出库类型 |
| data.datas[].inout_user | string | 否 |  | 其它出入库人员 |
| data.datas[].l_id | string | 否 |  | 快递单号 |
| data.datas[].lc_id | string | 否 |  | 物流公司编码 |
| data.datas[].logistics_company | string | 否 |  | 物流公司 |
| data.datas[].lock_wh_id | number | 否 |  | 虚拟仓编码 |
| data.datas[].lock_wh_name | string | 否 |  | 虚拟仓名称 |
| data.datas[].items | array | 否 |  | 商品集合 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].ioi_id | integer | 否 | 1660955 | 子单号 |
| data.datas[].items[].sku_id | string | 否 | #JLJS_107 | 商品编码 |
| data.datas[].items[].name | string | 否 | 20215088喷绘连衣裙560191-颜色:玫红;尺寸:4XL; | 商品名称 |
| data.datas[].items[].unit | string | 否 |  | 单位 |
| data.datas[].items[].properties_value | string | 否 | 颜色:玫红;尺寸:4XL; | 颜色及规格 |
| data.datas[].items[].qty | integer | 否 | 1 | 数量 |
| data.datas[].items[].cost_price | number | 否 |  | 成本单价 |
| data.datas[].items[].cost_amount | number | 否 | 0.0 | 总成本价 |
| data.datas[].items[].i_id | string | 否 | 84255818830 | 款式编码 |
| data.datas[].items[].remark | string | 否 |  | 商品备注 |
| data.datas[].items[].io_id | integer | 否 | 809069 | 出仓单号 |
| data.datas[].items[].sale_price | number | 否 | 1999.0 | 单价 |
| data.datas[].items[].sale_amount | number | 否 | 1999.0 | 金额 |
| data.datas[].items[].batch_id | string | 否 |  | 批次号，需开启相关业务配置 |
| data.datas[].items[].product_date | string | 否 |  | 批次日期，需开启相关业务配置 |
| data.datas[].items[].supplier_id | integer | 否 |  | 供应商编号，需开启相关业务配置 |
| data.datas[].items[].expiration_date | string | 否 |  | 有效期至，需开启相关业务配置 |
| data.datas[].batchs | array | 否 |  | 批次集合，获取该节点系统中相关业务项需配置（对应erp基础设置开启生产批次管理 如果是分仓数据 分仓也需要开启） |
| data.datas[].batchs[] | object | 否 |  |  |
| data.datas[].batchs[].batch_no | string | 否 |  | 批次号 |
| data.datas[].batchs[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].batchs[].qty | integer | 否 |  | 数量 |
| data.datas[].batchs[].product_date | string | 否 |  | 批次日期 |
| data.datas[].batchs[].supplier_id | integer | 否 |  | 供应商编号 |
| data.datas[].batchs[].supplier_name | string | 否 |  | 供应商名称 |
| data.datas[].batchs[].ioi_id | string | 否 |  | 子单号 |
| data.datas[].sns | array | 否 |  | 唯一码集合，获取该节点系统中相关业务项需配置（对应erp基础设置商品唯一码开关） |
| data.datas[].sns[] | object | 否 |  |  |
| data.datas[].sns[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].sns[].sn | string | 否 |  | SN码 |
| data.datas[].ts | integer | 否 |  | 时间戳 |

### 请求示例

```json
{
  "modified_begin": "2022-06-22 09:20:47",
  "modified_end": "2022-06-22 21:20:47",
  "types": [
    "其它进仓",
    "其它退货"
  ],
  "page_index": 1,
  "page_size": 1
}
```


### 响应示例

```json
{
  "page_size": 1,
  "page_index": 1,
  "data_count": 16,
  "page_count": 16,
  "has_next": true,
  "datas": [
    {
      "supplier_id": null,
      "io_id": 3492802,
      "io_date": "2022-06-22 09:23:08",
      "status": "Confirmed",
      "so_id": null,
      "type": "其它退货",
      "f_status": null,
      "warehouse": "GOTO陈萱主仓",
      "receiver_name": null,
      "receiver_mobile": null,
      "receiver_state": null,
      "receiver_city": null,
      "receiver_district": null,
      "receiver_address": null,
      "wh_id": 1,
      "remark": "成品入仓",
      "modified": "2022-06-22 09:23:08",
      "po_id": null,
      "labels": null,
      "wms_co_id": 10768327,
      "drop_co_name": "成品入库",
      "creator_name": "黄淑娟",
      "inout_user": "黄淑娟",
      "l_id": null,
      "lc_id": null,
      "logistics_company": null,
      "wave_id": null,
      "created": "2022-06-22 09:15:58",
      "items": [
        {
          "ioi_id": 4070389,
          "sku_id": "6972098820071",
          "name": "星云拖卡其42-43",
          "properties_value": "星云拖卡其42-43",
          "qty": 80,
          "cost_price": 70.28,
          "cost_amount": 5622.4,
          "i_id": "6972098820071",
          "remark": null,
          "io_id": 3492802,
          "sale_price": null,
          "sale_amount": 0
        },
        {
          "ioi_id": 4070391,
          "sku_id": "6975049913996",
          "name": "黑洞拖深灰色40-41码",
          "properties_value": "黑洞拖深灰色40-41码",
          "qty": 5,
          "cost_price": 32,
          "cost_amount": 160,
          "i_id": "6975049913996",
          "remark": "",
          "io_id": 3492802,
          "sale_price": null,
          "sale_amount": 0
        },
        {
          "ioi_id": 4070392,
          "sku_id": "6975049913997",
          "name": "黑洞拖深灰色42码",
          "properties_value": "黑洞拖深灰色42码",
          "qty": 7,
          "cost_price": 32,
          "cost_amount": 224,
          "i_id": "6975049913997",
          "remark": null,
          "io_id": 3492802,
          "sale_price": null,
          "sale_amount": 0
        },
        {
          "ioi_id": 4070393,
          "sku_id": "6975049913998",
          "name": "黑洞拖深灰色43码",
          "properties_value": "黑洞拖深灰色43码",
          "qty": 3,
          "cost_price": 32,
          "cost_amount": 96,
          "i_id": "6975049913998",
          "remark": "",
          "io_id": 3492802,
          "sale_price": null,
          "sale_amount": 0
        },
        {
          "ioi_id": 4070394,
          "sku_id": "6975049913999",
          "name": "黑洞拖深灰色44码",
          "properties_value": "黑洞拖深灰色44码",
          "qty": 8,
          "cost_price": 32,
          "cost_amount": 256,
          "i_id": "6975049913999",
          "remark": null,
          "io_id": 3492802,
          "sale_price": null,
          "sale_amount": 0
        },
        {
          "ioi_id": 4070395,
          "sku_id": "6975049914000",
          "name": "黑洞拖深灰色45-46码",
          "properties_value": "黑洞拖深灰色45-46码",
          "qty": 10,
          "cost_price": 32,
          "cost_amount": 320,
          "i_id": "6975049914000",
          "remark": "",
          "io_id": 3492802,
          "sale_price": null,
          "sale_amount": 0
        },
        {
          "ioi_id": 4070398,
          "sku_id": "'6975049914012",
          "name": "黑洞拖深灰色38-39码",
          "properties_value": "黑洞拖深灰色38-39码",
          "qty": 10,
          "cost_price": 32,
          "cost_amount": 320,
          "i_id": "'6975049914012",
          "remark": "",
          "io_id": 3492802,
          "sale_price": null,
          "sale_amount": 0
        }
      ]
    }
  ],
  "code": 0,
  "issuccess": true,
  "msg": "执行成功",
  "requestId": null
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

## 新建其它出入库

`/open/jushuitan/otherinout/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 新建其它出入库 |
| 接口路径 | `/open/jushuitan/otherinout/upload` |
| docType / docId | 10 / 43 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=10&docId=43 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/otherinout/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/otherinout/upload` |


### 接口说明

系统相关界面：【库存】------【其它出入库(非订单)】

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
| is_confirm | boolean | 是 | true | 是否确认单据；默认false |
| excute_confirming | boolean | 否 |  | 是否审核单据；默认false |
| wms_co_id | integer | 否 | 0 | 分仓编号或者三方仓编码 |
| type | string | 是 | in | 出入库类型:in是入库（其它退货）out是出库（其它出库）type：in且is_return：false为其它进仓 |
| external_id | string | 是 | 202003251816 | 外部单号（单据上传成功之后对应页面线上单号） |
| warehouse | integer | 否 | 1 | 默认1 ，主仓=1，销退仓=2，进货仓=3，次品仓=4，自定义1仓=6，自定义2仓=7，自定义3仓=8，自定义4仓=9，自定义5仓=10，自定义6仓=11，自定义7仓=12，自定义8仓=13，自定义9仓=14，自定义10仓=15（对应ERP仓库资料设定页面） |
| remark | string | 否 | 测试 | 备注，不能传空值 |
| drp_co_name | string | 否 | 测试 | 出库类型 |
| items | array | 是 |  | 商品列表 |
| items[] | object | 否 |  | 最大支持上传1000条 |
| items[].sku_id | string | 是 | CU-6 | 商品编码 |
| items[].sku_sns | array | 否 |  | 唯一码集合（如需使用请在基础设置开启唯一码和序列号） |
| items[].sku_sns[] | string | 否 |  |  |
| items[].qty | integer | 是 | 10 | 数量（必须大于0） |
| items[].supplier_id | number | 否 |  | 内部供应商编码 |
| items[].batch_id | string | 否 |  | 批次单号，系统中需开启相关配置（对应erp基础设置开启生产批次管理 如果是分仓数据 分仓也需要开启） |
| items[].produced_date | string | 否 |  | 生产日期，系统中需开启相关配置（对应erp基础设置开启生产批次管理 如果是分仓数据 分仓也需要开启） |
| items[].expiration_date | string | 否 |  | 有效期至，系统中需开启相关配置（对应erp基础设置开启生产批次管理 如果是分仓数据 分仓也需要开启） |
| items[].remark | string | 否 |  | 备注 |
| items[].sale_price | number | 否 |  | 商品单价 |
| items[].cost_price | number | 否 |  | 成本价（最大4位小数，四舍五入，数值传空时，不传默认取商品资料成本价，最大值不得超过99999999） |
| receiver_name | string | 否 |  | 收件人姓名 |
| receiver_mobile | string | 否 |  | 收件人手机号 |
| receiver_state | string | 否 |  | 收件地址省 |
| receiver_city | string | 否 |  | 收件地址市 |
| receiver_district | string | 否 |  | 收件地址区\|县 |
| receiver_address | string | 否 |  | 收件详细地址 |
| labels | array | 否 |  | 标记｜多标签（总length不能超过200） |
| labels[] | string | 否 |  |  |
| lock_wh_id | integer | 否 |  | 虚拟仓编号(对应虚拟仓设置页面虚拟仓编号):传ID取ID，传名称取名称，二者皆传以ID为准 |
| lock_wh_name | string | 否 |  | 虚拟仓名称 |
| lc_id | string | 否 |  | 物流公司编码 |
| l_id | string | 否 |  | 物流单号 |
| logistics_company | string | 否 |  | 物流公司名称 |
| is_return | boolean | 否 | true | 默认是true，只有当type为in的时候生效（is_return为true时表示是其它退货，为false时表示其它进仓） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 |  | 错误描述 |
| data | object | 否 |  |  |
| data.data | object | 否 |  |  |
| data.data.external_id | string | 否 | 202003251816 | 外部单号（单据上传成功之后对应页面线上单号） |
| data.data.io_id | integer | 否 | 327084 | 系统内部单号（单据上传成功之后对应页面出仓单号） |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 130 |  "msg": "通用暂存位中不存在商品；不允许移出或移入负数" |  |
| 130 |  "msg": "选择的商品编码[10076080]在商品资料库中不存在" |  |
| 130 | "msg":"已经开通了精细仓位库存管理，当前功能禁用，请使用手持模块进行相应操作" |  |


### 请求示例

```json
{
  "is_confirm": true,
  "external_id": "66666666",
  "type": "in",
  "items": [
    {
      "batch_id": "250201",
      "qty": 20,
      "sku_id": "SP2737",
      "expiration_date": "2028-02-12",
      "produced_date": "2025-02-13"
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
      "external_id": "66666666",
      "io_id": 327084
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

## 其它出入库状态变更

`/open/jushuitan/otherinout/cancel`

| 项 | 内容 |
|---|---|
| 接口名称 | 其它出入库状态变更 |
| 接口路径 | `/open/jushuitan/otherinout/cancel` |
| docType / docId | 10 / 223 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=10&docId=223 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/otherinout/cancel` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/otherinout/cancel` |


### 接口说明

注意：仅支持操作本仓单据
 不支持操作推送到三方仓的其它出入库单据状态变更
 不支持开了奇门云仓配置的商家单据状态变更

 请谨慎操作！

 更多其它出入库API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=23&currentPage=1&pageSize=20

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
| io_ids | array | 否 |  | 出仓单号，与线上单号不能同时为空，两者都存在时取io_ids，最多20个 |
| io_ids[] | string | 否 |  |  |
| so_ids | array | 否 |  | 线上单号，与出仓单号不能同时为空，两者都存在时取io_ids，最多20个 |
| so_ids[] | string | 否 |  |  |
| wms_co_id | number | 否 |  | 分仓单据需传入分仓编号 |
| operate_type | string | 否 | 3 | 操作 1:审核 2:取消审核 3:作废 4:确认生效（如果不传默认3作废操作） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 |  | 错误码 |
| issuccess | boolean | 否 |  | true 代表成功 |
| msg | string | 否 |  | 执行描述 |

### 请求示例

```json
{
  "so_ids": [],
  "wms_co_id": ,
  "io_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
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
