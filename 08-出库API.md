# 聚水潭开放平台 · 出库API（线下版）

> 抓取日期：2026-11-23  
> 分类：出库API（docType=8）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=8&docId=34

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 销售出库查询 | `/open/orders/out/simple/query` | 34 | [打开](https://openweb.jushuitan.com/dev-doc?docType=8&docId=34) |
| 出库发货 | `/open/orders/wms/sent/upload` | 35 | [打开](https://openweb.jushuitan.com/dev-doc?docType=8&docId=35) |
| 采购退货查询 | `/open/purchaseout/query` | 36 | [打开](https://openweb.jushuitan.com/dev-doc?docType=8&docId=36) |
| 采购退货取消 | `/open/jushuitan/purchaseout/cancel` | 93 | [打开](https://openweb.jushuitan.com/dev-doc?docType=8&docId=93) |
| 生成采购退货单-支持批量 | `/open/webapi/wmsapi/purchaseout/createbatch` | 269 | [打开](https://openweb.jushuitan.com/dev-doc?docType=8&docId=269) |

## 目录

- [销售出库查询](#销售出库查询)
- [出库发货](#出库发货)
- [采购退货查询](#采购退货查询)
- [采购退货取消](#采购退货取消)
- [生成采购退货单-支持批量](#生成采购退货单-支持批量)

---

## 销售出库查询

`/open/orders/out/simple/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 销售出库查询 |
| 接口路径 | `/open/orders/out/simple/query` |
| docType / docId | 8 / 34 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=8&docId=34 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/orders/out/simple/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/orders/out/simple/query` |


### 接口说明

系统相关界面：【库存】------【销售出库单】
 此接口不包含淘系拼多多平台单据的敏感数据（如 线上单号、收件人信息、支付时间以及所有价格相关 字段等） ，其它平台的敏感信息会根据平台规则同步调整
 淘系平台包含： 淘宝天猫，天猫供销，考拉pop，考拉供应商直发，阿里巴巴，淘工厂，天猫超市，天猫国际直营，阿里健康直营，淘宝定制，淘宝采购，淘宝买菜，银泰喵街 ，饿百零售

 1.数据流向： 外部系统 获取聚水潭ERP里的销售出库单数据
 2. 如需获取淘系单据（收件人id、收件人省市区、支付时间、金额相关字段）， 需对接奇门：奇门自定义场景
 3. 如需获取拼多多单据（收件人id、支付时间、线上单号、金额等平台下载下来的相关字段），需对接方舟： 拼多多方舟 （注：只能查到近3个月的订单对应的出库单）
 3.奇门自定义接口对接步骤：1.申请奇门appkey 2.提供奇门appkey申请聚水潭customer_id（方法查阅文档） 3.按照奇门请求示例调用接口（查阅文档）
 4.如需获取ERP系统里的订单、销售出库单、售后单等单据的收件人敏感信息（淘系的只能走奇门，拼多多的对接拼多多平台，其它线上平台获取不到收件人信息（密文也不返回），商家自有商城店铺可提供明文）
 5.请求参数中start_ts的说明：使用ts的查询条件是唯一可避免分页查询过程中因数据变动而导致的漏单问题，原因是该查询条件是数据库中的时间戳，sql server中的 行版本号 。只要当前这条数据在数据库中有变化任何字段变化ts的值都会自增，全表唯一的自增值，非业务上做的时间值更新。使用ts的查询模板
 第一次请求：{" start_ts ":1," is_get_total ":false," page_index ":1," page_size ":100} //第一次请求ts从1开始
 第二次请求：{" start_ts ":传第一次返回的最大ts值," is_get_total ":false," page_index ":1," page_size ":100} //一直请求到查不到比入参ts值本身更大的数据为止。只有start_ts值是变量，其它3个参数值不变

 常见问题：
 1. 销售出库单查询不到：
 a、分销+订单不产生销售出库单（分销+订单由供销商发货，出库单在供销商侧，商家不支持获取）
 b、线上发货，是线上发货同步下来订单直接变成已发货状态，不产生销售出库单。（标记多标签有 线上发货标识）

 更多出库API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=21&currentPage=1&pageSize=20

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
| shop_id | integer | 否 |  | 店铺编码 |
| is_offline_shop | boolean | 否 |  | 是否线上店铺：shop_id为0且is_offline_shop为true查询线下店铺单据 |
| status | string | 否 |  | 单据状态 WaitConfirm=待出库;Confirmed=已出库;Delete=作废(发货前取消订单);Cancelled=取消（发货后撤销发货）;OuterConfirming外部发货中；Archive已结算 |
| modified_begin | string | 否 | 2022-12-09 00:00:06 | 起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空；tips:用时间条件查询由于查询中数据存在变动的可能会由于排序问题引发分页查询漏单的问题，建议使用ts时间戳增量查询的方式 |
| modified_end | string | 否 | 2022-12-09 10:00:06 | 结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空 |
| so_ids | array | 否 |  | 指定 线上单号 ，和时间段不能同时为空，最大50 |
| so_ids[] | string | 否 |  |  |
| page_index | integer | 否 |  | 第几页，从第一页开始，默认1 |
| page_size | integer | 否 |  | 每页多少条，默认30，最大50 |
| wms_co_id | integer | 否 |  | 出库仓编号 |
| o_ids | array | 否 |  | 内部单号 最大50条；与时间条件不能同时为空 |
| o_ids[] | number | 否 |  |  |
| l_ids | array | 否 |  | 物流单号；不超过20条 |
| l_ids[] | string | 否 |  |  |
| wave_ids | array | 否 |  | 拣货批次号；不超过50条 与时间条件不能同时为空 |
| wave_ids[] | number | 否 |  |  |
| start_ts | integer | 否 |  | 时间戳，sql server中的行版本号，该字段查询防止分页过程中漏单 |
| is_get_total | boolean | 否 |  | 是否查询总条数默认true，如果使用start_ts查询，该值默认为false不返回总条数总页数否则影响查询效率 |
| io_ids | array | 否 |  | 出库单号列表（商家维度下出库单全局唯一值），最大50 |
| io_ids[] | string | 否 |  |  |
| owner_co_id | integer | 否 | 11322398 | 货主 编码 |
| is_get_cbfinance | boolean | 否 |  | 是否获取跨境财务信息 |
| is_get_cblogistic | boolean | 否 |  | 是否获取跨境物流信息 |
| date_type | number | 否 |  | 时间类型 0:修改时间modified，2:出库时间io_date;默认0 |
| drp_co_id | number | 否 |  | 分销商编码（如使用该添加，时间查询条件限制跨度为1天） |
| inout_flds | array | 否 |  | 出库单主表自定义查询字段 |
| inout_flds[] | string | 否 | volume,package,owner_co_id,cus_id,as_id,outer_so_id,is_split,is_merge,picker_name,packer_name,checker_name,sku_bin | 体积,包材,货主编码,货通客户id,售后单号,奇门外部交易单号,是否被拆分，是否被合并,拣货员,打包员,验货员,外部云仓单号 |
| inout_item_flds | array | 否 |  | 出库单明细自定义查询字段 |
| inout_item_flds[] | string | 否 | volume,bu_id,combine_sku_qty | 体积,虚拟仓编码,组合装商品数量 |
| archive | boolean | 否 |  | 是否查询归档数据；true查询归档；false或不传默认查未归档 |

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
| data.max_ts | integer | 否 |  | 最大ts值 |
| data.datas | array | 否 |  | 数据集合 |
| data.datas[] | object | 否 |  |  |
| data.datas[].co_id | integer | 否 | 11053062 | 公司编号 |
| data.datas[].shop_id | integer | 否 | 11690153 | 店铺编码 |
| data.datas[].io_id | integer | 否 | 166 | 出库单号(商家维度下出库单全局唯一值) |
| data.datas[].o_id | integer | 否 | 36008 | 内部单号 |
| data.datas[].so_id | string | 否 | 3425786782368239 | 线上单号 |
| data.datas[].created | string | 否 | 2021-09-1614:05:07 | 创建时间 |
| data.datas[].modified | string | 否 | 2021-09-2315:07:58 | 修改时间 |
| data.datas[].status | string | 否 | Confirmed | 状态 ;WaitConfirm:待出库,Confirmed:已出库,Delete:作废（订单发货中取消订单）,OuterConfirming:外部发货中;Cancelled=取消（订单发货后撤销已发货） |
| data.datas[].order_type | string | 否 | 普通订单 | 订单类型，普通订单；补发订单；分销Plus；供销Plus；换货订单 |
| data.datas[].invoice_title | string | 否 |  | 发票抬头 |
| data.datas[].shop_buyer_id | string | 否 |  | 买家昵称/线下客户 |
| data.datas[].open_id | string | 否 |  | 平台买家唯一值，仅支持天猫，抖音，快手 |
| data.datas[].receiver_country | string | 否 |  | 国家 |
| data.datas[].receiver_state | string | 否 |  | 省 |
| data.datas[].receiver_city | string | 否 |  | 市 |
| data.datas[].receiver_district | string | 否 |  | 区 |
| data.datas[].receiver_town | string | 否 |  | 街道 |
| data.datas[].receiver_address | string | 否 |  | 地址 |
| data.datas[].receiver_name | string | 否 |  | 收件人姓名 |
| data.datas[].receiver_phone | string | 否 |  | 收件人手机 |
| data.datas[].receiver_mobile | string | 否 |  | 收件人电话 |
| data.datas[].buyer_message | string | 否 |  | 买家留言 |
| data.datas[].remark | string | 否 |  | 卖家备注 |
| data.datas[].is_cod | boolean | 否 | false | 是否货到付款 |
| data.datas[].pay_amount | number | 否 | 706.0 | 应付金额 |
| data.datas[].l_id | string | 否 | 20210923 | 物流单号 |
| data.datas[].io_date | string | 否 | 2021-09-2315:07:58 | 出库时间（跟出库状态无关单据创建后出库时间默认为创建时间，取消单据出库时间不会清除） |
| data.datas[].lc_id | string | 否 | SF | 快递公司编码 |
| data.datas[].stock_enabled | string | 否 | on | 是否启用库存管理 |
| data.datas[].drp_co_id_from | string | 否 |  | 分销商编号 |
| data.datas[].labels | string | 否 | 延时发货 | 标记\|多标签 |
| data.datas[].paid_amount | number | 否 | 706.0 | 订单支付详情中的支付金额 |
| data.datas[].free_amount | number | 否 | 0.0 | 优惠金额 |
| data.datas[].buyer_paid_amount | number | 否 |  | 买家实付（仅限订单详情营收小计能看到的数据的平台） |
| data.datas[].seller_income_amount | number | 否 |  | 卖家实收（仅限订单详情营收小计能看到的数据的平台） |
| data.datas[].f_volume | string | 否 |  | 实测体积 |
| data.datas[].freight | number | 否 | 4.0 | 买家支付运费 |
| data.datas[].first_freight | string | 否 |  | 跨境订单-头程运费 |
| data.datas[].outerwms_freight | string | 否 |  | 跨境订单-尾程运费 |
| data.datas[].weight | number | 否 | 0.0 | 预估重量 |
| data.datas[].f_weight | number | 否 |  | 实称重量 |
| data.datas[].merge_so_id | string | 否 |  | 合并订单号 |
| data.datas[].wms_co_id | integer | 否 | 11053062 | 分仓编号 |
| data.datas[].owner_oid | number | 否 |  | 三方仓模式下货主内部出库单号 |
| data.datas[].business_staff | string | 否 | 川梣 | 业务人员 |
| data.datas[].currency | string | 否 |  | 货币类型 |
| data.datas[].pay_date | string | 否 | 2019-12-1616:35:28 | 付款日期 |
| data.datas[].logistics_company | string | 否 | 顺丰速运 | 物流公司名称 |
| data.datas[].wave_id | integer | 否 |  | 拣货批次号 |
| data.datas[].seller_flag | integer | 否 |  | 旗帜(1红旗，2黄旗，3绿旗，4蓝旗，5紫旗)） |
| data.datas[].gov_supplier_name | string | 否 |  | 实际销售公司 |
| data.datas[].government_free_amount | number | 否 |  | 国补金额 |
| data.datas[].order_staff_id | integer | 否 | 12854967 | 订单业务员编号 |
| data.datas[].order_staff_name | string | 否 | 川梣 | 订单业务员名称 |
| data.datas[].node | string | 否 |  | 线下备注 |
| data.datas[].first_freight_tariff | number | 否 |  | 跨境订单-头程关税 |
| data.datas[].f_freight_other_expense | number | 否 |  | 跨境订单-头程其他费用 |
| data.datas[].items | array | 否 |  | 商品集合 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].ioi_id | integer | 否 | 198 | 子单号 |
| data.datas[].items[].pic | string | 否 |  | 图片 |
| data.datas[].items[].sku_id | string | 否 | s111001 | 商品编码 |
| data.datas[].items[].qty | integer | 否 | 1 | 数量 |
| data.datas[].items[].name | string | 否 | SKUA1 | 商品名称 |
| data.datas[].items[].properties_value | string | 否 | SKUA1 | 颜色规格 |
| data.datas[].items[].sale_price | number | 否 | 223.0 | 单价 |
| data.datas[].items[].oi_id | string | 否 |  | 订单子订单号 |
| data.datas[].items[].sale_amount | number | 否 | 223.0 | 金额 |
| data.datas[].items[].i_id | string | 否 |  | 款式编码 |
| data.datas[].items[].unit | string | 否 |  | 商品单位 |
| data.datas[].items[].sale_base_price | number | 否 | 223.0 | 原价 |
| data.datas[].items[].combine_sku_id | string | 否 |  | 组合装商品编码 |
| data.datas[].items[].is_gift | boolean | 否 | false | 是否赠品 |
| data.datas[].items[].outer_oi_id | string | 否 |  | 子订单号，商家系统订单商品明细主键,为了拆单合单时溯源，最长不超过50,保持唯一 |
| data.datas[].items[].raw_so_id | string | 否 |  | 原始线上订单号 |
| data.datas[].items[].batch_id | string | 否 |  | 批次号，获取该字段系统中相关业务项需配置 |
| data.datas[].items[].product_date | string | 否 |  | 批次日期，系统中相关业务项需配置 |
| data.datas[].items[].supplier_id | integer | 否 |  | 供应商编号，系统中相关业务项需配置 |
| data.datas[].items[].expiration_date | string | 否 |  | 有效期至，系统中相关业务项需配置 |
| data.datas[].items[].buyer_paid_amount | number | 否 |  | 买家实付 |
| data.datas[].items[].seller_income_amount | number | 否 |  | 卖家实收 |
| data.datas[].items[].total_qty | number | 否 | 1.6 | 总用量 |
| data.datas[].ClusterInfos | array | 否 |  | 子母单的子单信息 |
| data.datas[].ClusterInfos[] | object | 否 |  |  |
| data.datas[].ClusterInfos[].io_id | string | 否 |  | 出库单号 |
| data.datas[].ClusterInfos[].l_id | string | 否 |  | 物流单子单号 |
| data.datas[].ClusterInfos[].logistic_company | string | 否 |  | 物流公司名称 |
| data.datas[].ClusterInfos[].lc_id | string | 否 |  | 物流公司编码 |
| data.datas[].ClusterInfos[].f_weight | number | 否 |  | 子单号实称重量 |
| data.datas[].batchs | array | 否 |  | 生产批次集合 获取该节点系统中相关业务项需配置（对应erp基础设置开启生产批次管理 如果是分仓数据 分仓也需要开启） |
| data.datas[].batchs[] | object | 否 |  |  |
| data.datas[].batchs[].batch_no | string | 否 |  | 批次号 |
| data.datas[].batchs[].ioi_id | number | 否 |  | 出库单商品明细单号（需开启批次2.0并且统一功能配置wms.ioiid.match.skusn） |
| data.datas[].batchs[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].batchs[].qty | integer | 否 |  | 数量 |
| data.datas[].batchs[].product_date | string | 否 |  | 批次日期 |
| data.datas[].batchs[].supplier_id | integer | 否 |  | 供应商编号 |
| data.datas[].batchs[].supplier_name | string | 否 |  | 供应商名称 |
| data.datas[].batchs[].expiration_date | string | 否 |  | 有效期至 |
| data.datas[].batchs[].status | string | 否 |  | 状态 |
| data.datas[].sns | array | 否 |  | 唯一码集合 获取该节点系统中相关业务项需配置（对应erp基础设置商品唯一码开关）默认从跟踪信息唯一码界面取值，如果开启了唯一码流水读取的是唯一码流水界面的数据 |
| data.datas[].sns[] | object | 否 |  |  |
| data.datas[].sns[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].sns[].sn | string | 否 |  | 唯一码 |
| data.datas[].sns[].certificate_no | string | 否 |  | 国补IMEI辅助唯一码 |
| data.datas[].sns[].is_pack_sn | boolean | 否 |  | 是否箱唯一码，true是箱唯一码 |
| data.datas[].sns[].is_opened | boolean | 否 |  | 是否开箱，true 是开箱 |
| data.datas[].sns[].pack_sn | string | 否 |  | 箱码 |
| data.datas[].sns[].batch_id | string | 否 |  | 生产批次号（仅开启唯一码生产批次溯源流程下有效） |
| data.datas[].sns[].produced_date | string | 否 |  | 生产日期（仅开启唯一码生产批次溯源流程下有效） |
| data.datas[].sns[].expiration_date | string | 否 |  | 有效期至（仅开启唯一码生产批次溯源流程下有效） |
| data.datas[].is_print_express | boolean | 否 |  | 快递单已打印 |
| data.datas[].is_print | boolean | 否 |  | 订单已打印 |
| data.datas[].shop_name | string | 否 |  | 店铺名称 |
| data.datas[].ts | integer | 否 |  | 数据库行版本号：https://docs.microsoft.com/zh-cn/sql/t-sql/data-types/rowversion-transact-sql?view=sql-server-ver16 |
| data.datas[].shipment | string | 否 |  | 跨境订单买家指定物流（is_get_cblogistic传true返回） |
| data.datas[].deliver_name | string | 否 |  | 跨境订单物流方式（is_get_cblogistic传true返回） |
| data.datas[].channel_name  | string | 否 |  | 跨境订单渠道名称（is_get_cblogistic传true返回） |
| data.datas[].tracking_number | string | 否 |  | 跨境订单国际运单号（is_get_cblogistic传true返回） |
| data.datas[].package_no | string | 否 |  | 参考号 |
| data.datas[].warehouse_oid | string | 否 |  | 外部单据号 |
| data.datas[].cb_finances | object | 否 |  | 跨境订单财务数据（废弃） |
| data.datas[].cb_financenew | object | 否 |  | 新版跨境订单财务数据（需要开通统一功能：开放平台查询否返回新版财务信息） |
| data.datas[].cb_financenew.currency_code | string | 否 |  | 报告币种 |
| data.datas[].cb_financenew.order_currency_code | string | 否 |  | 订单币种 |
| data.datas[].cb_financenew.o_id | number | 否 |  | 内部订单号 |
| data.datas[].cb_financenew.rate | string | 否 |  | 汇率 |
| data.datas[].cb_financenew.currency_to_usd | string | 否 |  | 原币转美元汇率 |
| data.datas[].cb_financenew.currency_to_rmb | string | 否 |  | 原币转人民币汇率 |
| data.datas[].cb_financenew.rate_date | string | 否 |  | 汇率对应的日期 |
| data.datas[].cb_financenew.profit | string | 否 |  | 利润金额 |
| data.datas[].cb_financenew.profit_rate | string | 否 |  | 利润率（百分比） |
| data.datas[].cb_financenew.net_amount | string | 否 |  | 平台净额 |
| data.datas[].cb_financenew.income_group | string | 否 |  | 收入分组的费用项 |
| data.datas[].cb_financenew.income_total | string | 否 |  | 收入总额（收入总额=实收金额-退款金额合计+其他收入-分类单收入冲减） |
| data.datas[].cb_financenew.expense_group | string | 否 |  | 平台支出分组的费用项 |
| data.datas[].cb_financenew.expense_total | string | 否 |  | 平台支出总额 |
| data.datas[].cb_financenew.erp_expense_group | string | 否 |  | ERP支出分组的费用项 |
| data.datas[].cb_financenew.erp_expense_total | string | 否 |  | ERP支出总额 |
| data.datas[].cb_financenew.refund_group | string | 否 |  | 退款组的费用项 |
| data.datas[].cb_financenew.refund_total | string | 否 |  | 退款总额 |
| data.datas[].owner_co_id | number | 否 |  | 货主编码 |
| data.datas[].f_length | number | 否 |  | 长 |
| data.datas[].f_width | number | 否 |  | 宽 |
| data.datas[].f_height | number | 否 |  | 高 |

### 请求示例

```json
{
  "o_ids": [],
  "shop_id": 0,
  "so_ids": [],
  "wms_co_id": 0,
  "page_index": 0,
  "modified_begin": "",
  "modified_end": "",
  "l_ids": [],
  "is_offline_shop": true,
  "status": "",
  "page_size": 0
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
        "is_print_express": true,
        "open_id": "",
        "f_weight": 0,
        "drp_co_id_from": "",
        "business_staff": "川梣",
        "wave_id": 0,
        "modified": "2021-09-2315:07:58",
        "receiver_country": "",
        "is_print": true,
        "order_type": "普通订单",
        "order_staff_id": 12854967,
        "buyer_message": "",
        "created": "2021-09-1614:05:07",
        "weight": 0.0,
        "shop_name": "",
        "io_id": 166,
        "labels": "延时发货",
        "shop_id": 11690153,
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
        "shop_buyer_id": "",
        "wms_co_id": 11053062,
        "paid_amount": 706.0,
        "stock_enabled": "on",
        "items": [
          {
            "i_id": "",
            "properties_value": "SKUA1",
            "is_gift": false,
            "qty": 1,
            "combine_sku_id": "",
            "name": "SKUA1",
            "sku_id": "s111001",
            "sale_base_price": 223.0,
            "pic": "",
            "ioi_id": 198,
            "sale_price": 223.0,
            "sale_amount": 223.0
          }
        ],
        "status": "Confirmed",
        "pay_date": "2019-12-1616:35:28",
        "lc_id": "SF",
        "invoice_title": "",
        "receiver_city": "",
        "freight": 4.0,
        "remark": "",
        "is_cod": false,
        "receiver_state": "",
        "cb_finance": {
          "o_id": 2645610,
          "rebate_fee": null,
          "product_tax": 2.82,
          "shipping_tax": 0,
          "other_income": 0,
          "voucher_from_seller": 3.99,
          "platform_commission": 5.84,
          "transition_fee": null,
          "transaction_fee": null,
          "opaque_bagging_fee": 2.82,
          "other_expense": null
        },
        "so_id": "3425786782368239",
        "order_staff_name": "川梣",
        "o_id": 36008,
        "receiver_name": "",
        "currency": "",
        "free_amount": 0.0,
        "io_date": "2021-09-2315:07:58",
        "receiver_district": "",
        "receiver_town": "",
        "pay_amount": 706.0,
        "co_id": 11053062,
        "receiver_mobile": "",
        "seller_flag": 0,
        "merge_so_id": "",
        "receiver_address": "",
        "sns": [
          {
            "sku_id": "",
            "sn": ""
          }
        ],
        "logistics_company": "顺丰速运",
        "receiver_phone": "",
        "l_id": "20210923"
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

## 出库发货

`/open/orders/wms/sent/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 出库发货 |
| 接口路径 | `/open/orders/wms/sent/upload` |
| docType / docId | 8 / 35 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=8&docId=35 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/orders/wms/sent/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/orders/wms/sent/upload` |


### 接口说明

调用出库发货会自动同步订单线上发货信息
 调用该接口发货需要先在系统【物流(快递)公司及打印模板】页面中配置对应的物流公司及编码

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
| data | object | 否 |  | data节点返回的o_id字段对应的值为传入的出仓io_id |
| data.data | array | 否 |  |  |
| data.data[] | object | 否 |  |  |
| data.data[].msg | string | 否 |  | 执行结果 |
| data.data[].issuccess | boolean | 否 |  | 是否成功 |
| data.data[].o_id | integer | 否 |  | 出库单号 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 130 | { 	"msg": "传输数据不合规范，存在物流单号，物流公司，或者订单号为空的!", 	"code": 130, 	"requestId": "0a27aa0f17403915722187496e0045" } |  |
| 160 | { 	"msg": "执行失败", 	"code": 160, 	"data": [ 		{ 			"msg": "单据号:93784 状态对应不上[作废]!", 			"issuccess": false, 			"o_id": 93784 		} 	] } |  |
| 160 | { 	"msg": "执行失败", 	"code": 160, 	"data": [ 		{ 			"msg": "单据号:841229 未找到!", 			"issuccess": false, 			"o_id": 841229 		} 	] } |  |
| 130 | { 	"msg": "商家未配置该物流公司[DBKD]，请先进行配置后再进行发货", 	"code": 130, 	"requestId": "1a0c66d617403918943973499e0094" } |  |
| 160 | {     "code": 160,     "issuccess": false,     "msg": "执行失败",     "data": [         {             "o_id": 14806003,             "issuccess": false,             "msg": "单据号:0 以下出库单(14806003)不是本仓出库单，建议开启基础设置【发货业务支持主仓操作分仓单据】"         }     ] } |  |


### 请求示例

```json
[
    {
        "wms_co_id": 12686093,
        "lc_id": "SF",
        "l_id": "20211202-2",
        "lc_name": "顺丰快递",
        "io_id": 887,
        "items": [      --新增唯一码出库
            {
                "sku_id": "CU-6",
                "sn_list": [
                    "sn11",
                    "sn22"
                ]
            }
        ]
    }
]
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {
    "data": [
      {
        "msg": "成功",
        "issuccess": true,
        "o_id": 887
      }
    ]
  }
}
```


### 异常示例

```json
{
  "code": 160,
  "issuccess": false,
  "msg": "执行失败",
  "data": [
    {
      "o_id": 841229,
      "issuccess": false,
      "msg": "单据号:841229 未找到!"
    }
  ]
}
```


---

## 采购退货查询

`/open/purchaseout/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 采购退货查询 |
| 接口路径 | `/open/purchaseout/query` |
| docType / docId | 8 / 36 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=8&docId=36 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/purchaseout/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/purchaseout/query` |


### 接口说明

系统相关界面：【库存】------【采购退货】

 更多出库API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=21&currentPage=1&pageSize=20

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
| page_size | integer | 否 | 30 | 每页多少条，默认30，最大50 |
| modified_begin | string | 否 | 2021-12-03 00:00:00 | 起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空 |
| modified_end | string | 否 | 2021-12-10 00:00:00 | 结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与线上单号不能同时为空 |
| so_ids | array | 否 |  | 指定线上订单号，和时间段不能同时为空 |
| so_ids[] | string | 否 |  |  |
| status | string | 否 | Confirmed | 单据状态，Confirmed=生效，WaitConfirm待审核，Creating=草拟，Archive=归档，Cancelled=作废，Confirming 已确认 |
| io_ids | array | 否 |  | 采购退货单号列表,最大30 |
| io_ids[] | string | 否 |  |  |
| date_type  | number | 否 |  | 0:修改时间，modified。 2:出库时间 io_date，未传入时默认为0 |
| owner_co_id | number | 否 |  | 货主编码 （三方仓模式下仓储查询货主的单据） |

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
| data.datas[].io_id | integer | 否 | 741752 | 退货单号 |
| data.datas[].io_date | string | 否 | 2021-03-25 10:22:37 | 退货日期 |
| data.datas[].created_po_id | number | 否 |  | 返修退货关联采购单 |
| data.datas[].status | string | 否 | WaitConfirm | 状态(Confirmed:生效，WaitConfirm:待审核，Creating:草拟，Cancelled:作废,OuterConfirming:外部确认中，Delete:取消) |
| data.datas[].so_id | string | 否 |  | 线上单号 |
| data.datas[].f_status | string | 否 |  | 财务状态，WaitConfirm=待审核，Confirmed=已审核 |
| data.datas[].warehouse | string | 否 | JP主仓 | 仓库名 |
| data.datas[].receiver_name | string | 否 | 爱牙库 | 收货人名称 |
| data.datas[].receiver_mobile | string | 否 | 1 | 收货电话 |
| data.datas[].receiver_state | string | 否 |  | 收件人省 |
| data.datas[].receiver_city | string | 否 | 2 | 收件人市 |
| data.datas[].receiver_district | string | 否 |  | 收件人区 |
| data.datas[].receiver_address | string | 否 | 3 | 收件人省地址 |
| data.datas[].wh_id | integer | 否 | 1 | 仓库编号，1=主仓，2=销退仓，3=进货仓，4=次品仓 |
| data.datas[].remark | string | 否 | 质检退货 | 备注 |
| data.datas[].modified | string | 否 | 2021-03-25 15:32:36 | 修改时间 |
| data.datas[].po_id | integer | 否 | 4862 | 采购单号 |
| data.datas[].wms_co_id | string | 否 | 12252 | 分仓编号 |
| data.datas[].seller_id | integer | 否 | 245 | 供应商ID |
| data.datas[].seller_name | string | 否 |  | 供应商名称 |
| data.datas[].labels | string | 否 |  | 标记\|多标签 |
| data.datas[].wave_id | number | 否 |  | 拣货批次号 |
| data.datas[].logistics_company | string | 否 |  | 物流公司 |
| data.datas[].free_amount | number | 否 |  | 优惠金额 |
| data.datas[].lc_id | string | 否 |  | 物流公司编号 |
| data.datas[].l_id | string | 否 |  | 物流单号 |
| data.datas[].archived | string | 否 |  | 财务审核日期 |
| data.datas[].creator_name | string | 否 | 开发测试-开放平台 | 创建人 |
| data.datas[].lock_wh_id | number | 否 |  | 虚拟仓编号 |
| data.datas[].lock_wh_name | string | 否 |  | 虚拟仓名称 |
| data.datas[].out_io_id | string | 否 |  | 外部单号 |
| data.datas[].tax_rate | number | 否 |  | 税率 |
| data.datas[].items | array | 否 |  | 商品集合 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].ioi_id | integer | 否 | 350395 | 明细id |
| data.datas[].items[].sku_id | string | 否 | CU-6 | 商品编码 |
| data.datas[].items[].name | string | 否 | 1 | 商品名称 |
| data.datas[].items[].properties_value | string | 否 | 26 | 属性 |
| data.datas[].items[].tax_rate | number | 否 |  | 税率 |
| data.datas[].items[].qty | integer | 否 | 101 | 数量 |
| data.datas[].items[].cost_price | number | 否 | 10.0 | 单价 |
| data.datas[].items[].cost_amount | number | 否 | 1010.0 | 金额 |
| data.datas[].items[].i_id | string | 否 | CU-6 | 款式编码 |
| data.datas[].items[].remark | string | 否 |  | 备注 |
| data.datas[].items[].io_id | integer | 否 | 741752 | 退货单号 |
| data.datas[].items[].co_id | integer | 否 | 12252 | 公司编号 |
| data.datas[].items[].batch_no | string | 否 |  | 批次号，系统中相关业务项需配置 |
| data.datas[].batchs | array | 否 |  | 生产批次集合 ，系统中需开启相关配置(对应erp基础设置开启生产批次管理 如果是分仓数据 分仓也需要开启) |
| data.datas[].batchs[] | object | 否 |  |  |
| data.datas[].batchs[].batch_no | string | 否 |  | 批次号 |
| data.datas[].batchs[].ioi_id | string | 否 |  | 子单号 |
| data.datas[].batchs[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].batchs[].qty | integer | 否 |  | 数量 |
| data.datas[].batchs[].product_date | string | 否 |  | 批次日期 |
| data.datas[].batchs[].supplier_id | integer | 否 |  | 供应商编号 |
| data.datas[].batchs[].supplier_name | string | 否 |  | 供应商名称 |
| data.datas[].sns | array | 否 |  | 唯一码集合 ，获取该节点系统中相关业务项需配置（对应erp基础设置商品唯一码开关） |
| data.datas[].sns[] | object | 否 |  |  |
| data.datas[].sns[].sku_id | string | 否 |  | 商品编码 |
| data.datas[].sns[].sn | string | 否 |  | 唯一码 |

### 请求示例

```json
{
  "so_ids": [],
  "page_index": 1,
  "modified_begin": "2021-12-03 00:00:00",
  "modified_end": "2021-12-10 00:00:00",
  "page_size": 30,
  "status": "Confirmed",
  "io_ids": []
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
        "po_id": 4862,
        "receiver_city": "2",
        "remark": "质检退货",
        "receiver_state": "",
        "archived": "",
        "so_id": "",
        "receiver_name": "爱牙库",
        "modified": "2021-03-25 15:32:36",
        "f_status": "",
        "seller_id": 245,
        "io_date": "2021-03-25 10:22:37",
        "receiver_district": "",
        "warehouse": "JP主仓",
        "receiver_mobile": "1",
        "io_id": 741752,
        "labels": "",
        "batchs": [
          {
            "batch_no": "",
            "qty": 0,
            "sku_id": "",
            "supplier_name": "",
            "supplier_id": 0,
            "product_date": ""
          }
        ],
        "wms_co_id": "12252",
        "wh_id": 1,
        "receiver_address": "3",
        "sns": [
          {
            "sku_id": "",
            "sn": ""
          }
        ],
        "logistics_company": "",
        "creator_name": "开发测试-开放平台",
        "l_id": "",
        "items": [
          {
            "i_id": "CU-6",
            "properties_value": "26",
            "cost_amount": 1010.0,
            "qty": 101,
            "name": "1",
            "co_id": 12252,
            "sku_id": "CU-6",
            "remark": "",
            "ioi_id": 350395,
            "cost_price": 10.0,
            "io_id": 741752
          }
        ],
        "status": "WaitConfirm"
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

## 采购退货取消

`/open/jushuitan/purchaseout/cancel`

| 项 | 内容 |
|---|---|
| 接口名称 | 采购退货取消 |
| 接口路径 | `/open/jushuitan/purchaseout/cancel` |
| docType / docId | 8 / 93 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=8&docId=93 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/purchaseout/cancel` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/purchaseout/cancel` |


### 接口说明

注意：仅支持取消本仓单据 不支持取消推送到三方仓的采购退货单据

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
| io_ids[] | integer | 否 |  |  |
| so_ids | array | 否 |  | 线上单号，与出仓单号不能同时为空，两者都存在时取io_ids，最多20个 |
| so_ids[] | string | 否 |  |  |

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
  "io_ids": []
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
  "issuccess": false,
  "msg": "没有相应的单据"
}
```


---

## 生成采购退货单-支持批量

`/open/webapi/wmsapi/purchaseout/createbatch`

| 项 | 内容 |
|---|---|
| 接口名称 | 生成采购退货单-支持批量 |
| 接口路径 | `/open/webapi/wmsapi/purchaseout/createbatch` |
| docType / docId | 8 / 269 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=8&docId=269 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/purchaseout/createbatch` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/purchaseout/createbatch` |


### 接口说明

更多出库API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=21&currentPage=1&pageSize=20

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
| code | string | 否 |  | 状态码 |
| msg | string | 否 |  | 消息 |
| request_id | string | 否 |  |  |
| data | object | 否 |  |  |
| data.external_id | string | 否 |  | 外部采购退货单单号 |
| data.io_id | integer | 否 |  | 采购退货单单号 |
| data.is_success | boolean | 否 |  | 是否成功 |
| data.msg | string | 否 |  | 消息 |

### 请求示例

```json
[
  {
    "po_id": 26917,
    "receiver_city": "",
    "receiver_district": "",
    "type": 0,
    "external_id": "22320021254575881",
    "remark": "",
    "warehouse": 1,
    "receiver_mobile": 0,
    "receiver_state": "",
    "wms_co_id": 10177593,
    "is_confirm": true,
    "receiver_address": "",
    "supplier_id": 123126,
    "items": [
      {
        "batch_id": "",
        "price": 0,
        "qty": 2,
        "sku_id": "0012",
        "sku_sn": [
          "A0011204004",
          "A0011204005"
        ],
        "remark": "",
        "produced_date": ""
      }
    ]
  }
]
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": [
    {
      "msg": "",
      "external_id": "",
      "is_success": true,
      "io_id": 0
    }
  ],
  "request_id": ""
}
```


### 异常示例

_无_


---
