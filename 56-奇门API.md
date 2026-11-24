# 聚水潭开放平台 · 奇门 API（线下版）

> 抓取日期：2026-11-24  
> 分类：奇门 API（docType=56）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=56

说明：新版开放平台「奇门 API」侧栏（`getApiList` docType=56）**当前没有接口页**。奇门走阿里网关，不走 `openapi.jushuitan.com` 的 `biz` 协议。以下整理自官方说明文档和旧版接口页。

## 公共约定（奇门自定义）

| 项 | 内容 |
|---|---|
| 协议 | 阿里奇门 / TOP，不是开放平台 `app_key + biz + sign(v2)` |
| 网关 | `http://a1q40taq0j.api.taobao.com/router/qm` |
| `target_app_key` | 固定 `23060081` |
| `customer_id` | 必填路由参数；在 ERP【基础设置】→【开放平台】→【奇门自定义场景授权&配置】获取 |
| 限频 | **QPS 不能超过 10** |
| AppKey | 需奇门 WMS / POS / CRM / 线下 ERP **任一场景**资质；四类 AppKey **互不相通**，但都可以调自定义接口 |
| 数据范围 | 自定义接口**只能查淘系**；**不返回收件人信息** |
| 签名 | 按奇门/TOP 规则：https://open.taobao.com/doc.htm?docId=101617&docType=1 |
| 调用示例 | https://open.taobao.com/docV3.htm?docId=112&docType=1 |

`start_ts` 增量查询（与开放平台出库/订单查询相同口径）：

1. 第一次：`{"start_ts":1,"is_get_total":false,"page_index":1,"page_size":100}`
2. 之后把上次返回的最大 `ts` 作为新的 `start_ts`，其它三个参数不变，直到没有更大的 `ts`。

---

## 奇门场景说明

来源：https://openweb.jushuitan.com/doc?docId=27

淘系订单/出库/售后的敏感数据不能从开放平台直接透出，必须走奇门网关。

适用：

1. 聚水潭里的淘系订单要给其它 WMS 发货
2. 淘系销售出库单要给财务系统做账
3. 淘系订单/出库单/售后单要给自研系统做统计

需要全平台出库单 **且要收件人信息** 的，目前只有奇门 POS 支持；**POS 资质奇门已不再颁发**（历史已申请的仍可用）。

### 奇门 WMS（全平台待出库/出库单）

聚水潭作为 OMS 或作为 WMS，二者只能选其一，不能双向。

- 场景一：聚水潭作 OMS，对接系统作 WMS。聚水潭推送销售出库单（加密收件人），WMS 发货后回传。
- 场景二：对接系统作 OMS，聚水潭作 WMS。OMS 推送销售出库单，聚水潭发货后回传。

WMS 接口本身在阿里奇门文档：https://open.taobao.com/v2/doc#/abilityToOpen?treeId=780&docType=1&docId=109580

### 奇门 POS

获取聚水潭含淘系平台的销售出库单，且要求加密收件人。  
POS 接口文档：https://bigdata.taobao.com/api.htm?docId=29896&docType=2

### 奇门自定义接口

任意一个奇门场景 AppKey 都可以调自定义接口。上线流程见 https://openweb.jushuitan.com/doc?docId=250 ：

ERP【基础设置】→【开放平台】→【奇门自定义场景授权&配置】→ 得到 `customer_id`。

完整流程：向奇门申请资质拿到 AppKey → 按上线流程拿 `customer_id` → 调下面四个业务接口。

申请资质材料：系统界面说明书、软著登记表、源码不少于 6000 行。产品说明书模板：https://jushuitan.yuque.com/cscvxv/al2cbn/afc9bw （密码 `tyuy`）

---

## 本分类接口目录

| 接口 | method | 旧版文档 |
|---|---|---|
| 淘系订单查询列表 | `jushuitan.order.list.query` | [2352](https://open.jushuitan.com/document.aspx?doc_id=2352) |
| 淘系销售出库单(列表)查询 | `jushuitan.saleout.list.query` | [2355](https://open.jushuitan.com/document.aspx?doc_id=2355) |
| 淘系售后单查询(列表) | `jushuitan.refund.list.query` | [2356](https://open.jushuitan.com/document.aspx?doc_id=2356) |
| 淘系店铺商品资料查询 | `jushuitan.itemskumapper.list.query` | [2365](https://open.jushuitan.com/document.aspx?doc_id=2365) |

## 目录

- [淘系订单查询列表](#淘系订单查询列表)
- [淘系销售出库单列表查询](#淘系销售出库单列表查询)
- [淘系售后单查询列表](#淘系售后单查询列表)
- [淘系店铺商品资料查询](#淘系店铺商品资料查询)

---

## 淘系订单查询列表

`jushuitan.order.list.query`

| 项 | 内容 |
|---|---|
| 接口名称 | 淘系订单查询列表【奇门自定义接口】 |
| method | `jushuitan.order.list.query` |
| 旧版文档 | https://open.jushuitan.com/document.aspx?doc_id=2352 |
| 网关 | `http://a1q40taq0j.api.taobao.com/router/qm` |
| target_app_key | `23060081` |
| 限频 | QPS ≤ 10 |

### 接口说明

淘系订单查询列表【奇门自定义接口】
奇门申请地址：
https://open.taobao.com/docV3.htm?docId=118393&docType=1&source=search#ss13
奇门系统参数的
target_app_key
给
23060081
奇门接口路由参数:
接口需要额外带上
customer_id
,传不同的customer_id来路由不同的商家链接, 具体的值需要在进行授权的时候向聚水潭获取
customer_id获取方法
：文档中的上线流程  https://openweb.jushuitan.com/doc?docId=250
奇门API调用示例：
https://open.taobao.com/docV3.htm?spm=a219a.7386797.0.0.759a669a4Kh2yK&source=search&docId=112&docType=1
奇门调用签名sign生成文档：
https://open.taobao.com/doc.htm?docId=101617&docType=1
接口限频：qps 10
平台订单shop_status字段枚举：
淘宝天猫：
TRADE_NO_CREATE_PAY(没有创建支付宝交易)
WAIT_BUYER_PAY(等待买家付款)
SELLER_CONSIGNED_PART(卖家部分发货)
WAIT_SELLER_SEND_GOODS(等待卖家发货,即:买家已付款)
WAIT_BUYER_CONFIRM_GOODS(等待买家确认收货,即:卖家已发货)
TRADE_BUYER_SIGNED(买家已签收,货到付款专用)
TRADE_FINISHED(交易成功)
TRADE_CLOSED(付款以后用户退款成功，交易自动关闭)
TRADE_CLOSED_BY_TAOBAO(付款以前，卖家或买家主动关闭交易)
PAY_PENDING(国际信用卡支付付款确认中)
WAIT_PRE_AUTH_CONFIRM(0元购合约中)
PAID_FORBID_CONSIGN(拼团中订单或者发货强管控的订单，已付款但禁止发货)
抖音：
1 待确认/待支付（订单创建完毕）
103 部分支付
105 已支付
2 备货中
101 部分发货
3 已发货（全部发货）
4 已取消
5 已完成（已收货）
21 发货前退款完结
22 发货后退款完结
39 收货后退款完结
美团闪购：
1-用户已提交订单
2-向商家推送订单
4-商家已确认
8-订单已完成
9-订单已取消
拼多多：
1：待发货
2：已发货待签收
3：已签收
京东：
WAIT_SELLER_STOCK_OUT 等待出库
WAIT_GOODS_RECEIVE_CONFIRM 等待确认收货
WAIT_SELLER_DELIVERY等待发货（只适用于海外购商家，含义为“等待境内发货”标签下的订单,非海外购商家无需使用
PAUSE 暂停（loc订单可通过此状态获取）
FINISHED_L 完成
TRADE_CANCELED 取消
LOCKED 已锁定
POP_ORDER_PAUSE pop业务暂停，如3c号卡/履约/黄金的业务，可传此状态
有赞：
WAIT_BUYER_PAY：等待买家付款，定金预售描述：定金待付、等待尾款支付开始、尾款待付
TRADE_PAID：订单已支付 ，该状态仅代表当前订单已支付成功，表示瞬时状态，稍后会自动修改成后面的状态。如果不关心此状态请再次请求详情接口获取下一个状态
WAIT_CONFIRM：待确认，包含待成团、待接单等等。即：买家已付款，等待成团或等待接单
WAIT_SELLER_SEND_GOODS：等待卖家发货，即：买家已付款
WAIT_BUYER_CONFIRM_GOODS 等待买家确认收货，即：卖家已发货
TRADE_SUCCESS：买家已签收以及订单成功
TRADE_CLOSED：交易关闭
微盟微商城
0-待支付
1-待发货
2-已发货/已备货
3-已完成/已核销
4-已取消
5-已评论
6-已支付但不可发货（需外部审核）
饿了么：
1：待确认
2：已确认
7：骑士已接单
8：骑士已取餐
9：已完成
10：已取消
天猫国际直营、天猫国际、阿里健康、猫享没有枚举值 都是已付款订单
请求参数中start_ts的说明：
使用ts的查询条件是唯一可避免分页查询过程中因数据变动而导致的漏单问题，原因是该查询条件是数据库中的时间戳，sql server中的行版本号。只要当前这条数据在数据库中有变化任何字段变化ts的值都会自增，全表唯一的自增值，非业务上做的时间值更新。使用ts的查询模板
第一次请求：{"start_ts":1."is_get_total":false,"page_index":1."page_size":100} //第一次请求ts从1开始
第二次请求：{"start_ts":传第一次返回的最大ts值."is_get_total":false,"page_index":1."page_size":100} //一直请求到查不到比入参ts值本身更大的数据为止
奇门自定义调用示例代码
C#
版本：主要是附加
customer_id
和
target_app_key
两个参数
其他语言如java，php请参考奇门官方示例代码请点击“
奇门官方示例代码及SDK (https://open.taobao.com/docV3.htm?spm=a219a.7386797.0.0.759a669a4Kh2yK&source=search&docId=112&docType=1)
”

### 公共参数

请求地址：

| 环境 | HTTPS请求地址 |
|---|---|
| 正式环境 | http://a1q40taq0j.api.taobao.com/router/qm? |
| 沙箱环境 | 无 |


系统参数：

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| method | string |  |  | 接口名称:jushuitan.order.list.query |

---

### 请求参数

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| page_index | int | 是 | 1 | 页码 |
| page_size | int | 是 | 25 | 页数，最大100 |
| start_time | string |  | 2019-01-02 00:00:00 | 开始时间 |
| end_time | string |  | 2019-01-02 00:00:00 | 结束时间 |
| date_type | int |  | 0 | 0:修改时间modified，2:订单日期order_date，3:发货时间send_date；非必填，默认0 |
| wms_co_id | int |  | 11322398 | 发货仓编号 |
| shop_id | int |  | 12159435 | 店铺编号 |
| status | string |  | Sent | ERP订单状态：待付款：WaitPay；发货中：Delivering；被合并：Merged；异常：Question；被拆分：Split；等供销商\|外仓发货：WaitOuterSent；已付款待审核：WaitConfirm；已客审待财审：WaitFConfirm；已发货：Sent；取消：Cancelled |
| not_status | string |  | Sent | 不等于此状态 |
| is_paid | bool |  | true | 付款状态 |
| has_invoice | bool |  | true | 是否获取专票信息 |
| so_ids | string |  | "123,232" | 线上单号列表，多个线上单号以逗号分开 |
| o_ids | int |  |  | 内部订单号列表 |
| is_valid_pay | bool |  | true | 查出无效支付信息 |
| start_ts | int |  | long类型 | 开始时间戳，sql server中的行版本号，该字段查询防止分页过程中漏单 |
| is_get_total | bool |  |  | 是否查询总条数，默认true |
| archive | bool |  | true | 是否查归档订单 |
| order_types | string |  |  | 订单类型（普通订单,补发订单,换货订单,天猫分销,天猫供销,协同订单,亚马逊货件单,唯品会JITX订单,唯品会JITX待寻仓订单,送仓订单, 普通订单-分销Plus,补发订单-分销Plus,换货订单-分销Plus,天猫供销-分销Plus,协同订单-分销Plus,亚马逊货件单-分销Plus,唯品会JITX订单-分销Plus,唯品会JITX待寻仓订单-分销Plus,送仓订单-分销Plus, 普通订单-供销Plus,补发订单-供销Plus,换货订单-供销Plus,天猫供销-供销Plus,协同订单-供销Plus,亚马逊货件单-供销Plus,唯品会JITX订单-供销Plus,唯品会JITX待寻仓订单-供销Plus,送仓订单-供销Plus, 普通订单-分销Plus-供销Plus,补发订单-分销Plus-供销Plus,换货订单-分销Plus-供销Plus,天猫供销-分销Plus-供销Plus,协同订单-分销Plus-供销Plus,亚马逊货件单-分销Plus-供销Plus,唯品会JITX订单-分销Plus-供销Plus,唯品会JITX待寻仓订单-分销Plus-供销Plus,送仓订单-分销Plus-供销Plus） |
| order_item_flds | string |  | "src_combine_sku_id,presale_date" | 订单明细自定义查询字段：原组合商品编码,计划发货时间 |
| return_all_orderitems | bool |  |  | 是否返回删除的商品，默认为true |

---

### 响应参数

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| page_size | int |  | 1 | 页大小 |
| page_index | int |  | 25 | 页索引 |
| data_count | int |  | 100 | 数据重量 |
| page_count | int |  | 4 | 页数 |
| has_next | bool |  | true | 是否有下一页 |
| orders | list |  |  | 订单列表 |

---

### 请求示例

```json
{
  "o_ids":  0,
  "start_ts": 0,
  "date_type": 1,
  "is_valid_pay": true,
  "end_time": "2019-01-02 00:00:00",
  "has_invoice": true,
  "archive": false,
  "start_time": "2019-01-02 00:00:00",
  "shop_id": 11,
  "wms_co_id": 2,
  "so_ids":  "null",
  "end_ts": 0,
  "is_get_supplier": false,
  "page_index": 1,
  "is_get_total": true,
  "is_paid": true,
  "not_status": "Sent",
  "page_size": 10,
  "status": "WaitPay"
}
```

---

### 响应示例

```json
{
  "page_size": 1,
  "page_index": 1,
  "data_count": 1,
  "page_count": 1,
  "has_next": 1,
  "orders": [
    {
      "order_date": "2019-10-29 10:26:30",
      "shop_status": "null",
      "question_type": "null",
      "shop_id": 1,
      "question_desc": "null",
      "so_id": "2222",
      "status": "null",
      "receiver_state": "null",
      "receiver_city": "null",
      "receiver_district": "null",
      "send_date": "2019-10-29 10:26:30",
      "plan_delivery_date": "2019-10-29 10:26:30",
      "creator_name": "null",
      "buyer_tax_no": "null",
      "invoice_type": "null",
      "pay_amount": "null",
      "freight": "null",
      "buyer_message": "null",
      "remark": "null",
      "invoice_title": "null",
      "is_cod": true,
      "type": "null",
      "paid_amount": "0",
      "pay_date": "2019-10-29 10:26:30",
      "modified": "2019-10-29 10:26:30",
      "order_from": "null",
      "l_id": "null",
      "shop_name": "null",
      "wms_co_id": null,
      "logistics_company": "null",
      "free_amount": "0",
      "co_id": null,
      "pays": [
        {
          "status": "null",
          "outer_pay_id": "null",
          "pay_date": "null",
          "amount": "0",
          "payment": "null",
          "buyer_account": "null",
          "is_order_pay": true,
          "pay_id": "null"
        }
      ],
      "drp_co_id_to": "null",
      "end_time": "null",
      "referrer_id": "null",
      "invoice_data": "null",
      "drp_info": "null",
      "shop_buyer_id": "null",
      "seller_flag": "null",
      "invoice_amount": "null",
      "oaid": "null",
      "open_id": "null",
      "node": "null",
      "referrer_name": "null",
      "shop_site": "null",
      "drp_co_id_from": "null",
      "un_lid": "null",
      "receiver_zip": "null",
      "receiver_email": "null",
      "f_freight": "null",
      "created": "null",
      "receiver_country": "null",
      "ts": null,
      "buyer_paid_amount": null,
      "skus": "null",
      "link_o_id": "null",
      "seller_income_amount": null,
      "merge_so_id": "null",
      "shipment": "null",
      "weight": "null",
      "sign_time": "null",
      "f_weight": "null",
      "is_split": null,
      "is_merge": null,
      "o_id": 0,
      "items": [
        {
          "buyer_paid_amount": null,
          "seller_income_amount": null,
          "batch_id": "null",
          "produced_date": "null",
          "referrer_id": "null",
          "item_ext_data": "null",
          "src_combine_sku_id": "null",
          "pic": "null",
          "sku_type": "null",
          "item_pay_amount": "null",
          "remark": "null",
          "price": "0",
          "outer_oi_id": "null",
          "is_gift": "null",
          "refund_status": "null",
          "refund_id": "null",
          "item_status": "null",
          "i_id": "null",
          "shop_i_id": "null",
          "raw_so_id": "null",
          "is_presale": true,
          "oi_id": "null",
          "properties_value": "null",
          "amount": "0",
          "base_price": "0",
          "qty": 0,
          "name": "null",
          "sku_id": "null",
          "shop_sku_id": "null"
        }
      ],
      "labels": "null",
      "currency": "null",
      "lc_id": "null"
    }
  ]
}
```

---

## 淘系销售出库单(列表)查询

`jushuitan.saleout.list.query`

| 项 | 内容 |
|---|---|
| 接口名称 | 淘系销售出库单(列表)查询【奇门自定义接口】 |
| method | `jushuitan.saleout.list.query` |
| 旧版文档 | https://open.jushuitan.com/document.aspx?doc_id=2355 |
| 网关 | `http://a1q40taq0j.api.taobao.com/router/qm` |
| target_app_key | `23060081` |
| 限频 | QPS ≤ 10 |

### 接口说明

淘系销售出库单(列表)查询【奇门自定义接口】
奇门申请地址：
https://open.taobao.com/docV3.htm?docId=118393&docType=1&source=search#ss13
奇门系统参数的
target_app_key
给
23060081
接口限频：qps 10
奇门接口路由参数:
接口需要额外带上
customer_id
,传不同的customer_id来路由不同的商家链接, 具体的值需要在进行授权的时候向聚水潭获取
customer_id获取方法
：文档中的上线流程  https://openweb.jushuitan.com/doc?docId=250
奇门API调用示例：
https://open.taobao.com/docV3.htm?spm=a219a.7386797.0.0.759a669a4Kh2yK&source=search&docId=112&docType=1
奇门调用签名sign生成文档：
https://open.taobao.com/doc.htm?docId=101617&docType=1
请求参数中start_ts的说明：
使用ts的查询条件是唯一可避免分页查询过程中因数据变动而导致的漏单问题，原因是该查询条件是数据库中的时间戳，sql server中的行版本号。只要当前这条数据在数据库中有变化任何字段变化ts的值都会自增，全表唯一的自增值，非业务上做的时间值更新。使用ts的查询模板
第一次请求：{"start_ts":1."is_get_total":false,"page_index":1."page_size":100} //第一次请求ts从1开始
第二次请求：{"start_ts":传第一次返回的最大ts值."is_get_total":false,"page_index":1."page_size":100} //一直请求到查不到比入参ts值本身更大的数据为止
奇门自定义调用示例代码C#版本：请参考奇门自定义订单查询文档有完整示例代码“
订单查询示例代码 (https://open.jushuitan.com/document.aspx?doc_id=2352)
”，参考示例代码时请更换对应的
method
接口名
其他语言如java，php请参考奇门官方示例代码请点击“
奇门官方示例代码及SDK (https://open.taobao.com/docV3.htm?spm=a219a.7386797.0.0.759a669a4Kh2yK&source=search&docId=112&docType=1)
”

### 公共参数

请求地址：

| 环境 | HTTPS请求地址 |
|---|---|
| 正式环境 | http://a1q40taq0j.api.taobao.com/router/qm? |
| 沙箱环境 | 无 |


系统参数：

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| method | string | 是 |  | 接口名称:jushuitan.saleout.list.query |

---

### 请求参数

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| page_index | int | 是 |  | 页索引 |
| page_size | int | 是 |  | 页长度，最大100 |
| start_time | string |  |  | 开始时间 |
| end_time | string |  |  | 结束时间 |
| status | string |  |  | 出库单状态：Archive:归档,WaitConfirm:待出库,Confirmed:已出库,Cancelled:取消,Delete:作废,OuterConfirming:外部发货中 |
| wms_co_id | int |  |  | 分仓编号 |
| shop_id | int |  |  | 店铺编号 |
| so_ids | string |  | "111,222,333" | 线上单号列表，多个线上单号以逗号分开 |
| o_ids | int |  |  | 内部单号列表 |
| io_ids | int |  |  | 销售出库单号列表 |
| date_type | int |  |  | 时间类型 0:修改时间modified，2:出库时间io_date;默认0 |
| is_get_supplier | bool |  |  | 是否获取天猫分销信息 |
| is_get_total | bool |  |  | 是否查询总条数 |
| start_ts | int |  |  | 开始时间戳，sql server中的行版本号，该字段查询防止分页过程中漏单 |
| wave_ids | list |  |  | 拣货批次号 |
| archive | bool |  | true | 是否查归档订单 |
| is_get_cbfinance | bool |  |  | 是否获取跨境财务信息 |
| owner_co_id | int |  |  | 货主id |
| l_ids | string |  |  | 物流单号列表 |

---

### 响应参数

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| page_size | int |  |  | 页大小 |
| page_index | int |  |  | 页索引 |
| data_count | int |  |  | 数据总数 |
| page_count | int |  |  | 总页数 |
| has_next | bool |  |  | 是否有下一页 |
| datas | list |  |  | 数据列表 |

---

### 请求示例

```json
{
  "o_ids": [
    0
  ],
  "start_ts": 0,
  "date_type": 1,
  "end_time": "2019-01-02 00:00:00",
  "io_ids": [
    123
  ],
  "archive": false,
  "start_time": "2019-01-02 00:00:00",
  "shop_id": 12252,
  "wms_co_id": 12252,
  "so_ids": "null" ,
  "is_get_supplier": false,
  "page_index": 1,
  "is_get_total": true,
  "page_size": 20,
  "status": "WaitConfirm"
}
```

---

### 响应示例

```json
{
  "page_size": 1,
  "page_index": 20,
  "data_count": 1,
  "page_count": 1,
  "has_next": true,
  "datas": [
    {
      "co_id": 1,
      "shop_id": 1,
      "io_id": 1,
      "o_id": null,
      "so_id": "null",
      "created": "null",
      "modified": "null",
      "status": "null",
      "invoice_title": "null",
      "shop_buyer_id": "null",
      "receiver_country": "null",
      "receiver_state": "null",
      "receiver_city": "null",
      "receiver_district": "null",
      "buyer_message": "null",
      "remark": "null",
      "is_cod": null,
      "pay_amount": "null",
      "l_id": "null",
      "io_date": "null",
      "lc_id": "null",
      "stock_enabled": "null",
      "labels": "null",
      "paid_amount": "null",
      "free_amount": "null",
      "freight": "null",
      "weight": "null",
      "warehouse": "null",
      "drp_co_id_from": "null",
      "f_weight": "null",
      "order_type": "null",
      "batchs": [
        {
          "batch_no": "null",
          "sku_id": "null",
          "qty": null,
          "product_date": "null",
          "supplier_id": null,
          "supplier_name": "null",
          "expiration_date": "null"
        }
      ],
      "open_id": "null",
      "is_print_express": "null",
      "is_print": "null",
      "drp_info": "null",
      "buyer_tax_no": "null",
      "logistics_company": "null",
      "sns": [
        {
          "sku_id": "null",
          "sn": "null"
        }
      ],
      "merge_so_id": "null",
      "wms_co_id": null,
      "items": [
        {
          "i_id": "null",
          "sale_base_price": "null",
          "is_gift": null,
          "oi_id": null,
          "outer_oi_id": "null",
          "raw_so_id": "null",
          "pay_amount": "null",
          "combine_sku_id": "null",
          "ioi_id": null,
          "pic": "null",
          "sku_id": "null",
          "qty": null,
          "name": "null",
          "properties_value": "null",
          "sale_price": "null",
          "sale_amount": "null"
        }
      ]
    }
  ]
}
```

---

## 淘系售后单查询(列表)

`jushuitan.refund.list.query`

| 项 | 内容 |
|---|---|
| 接口名称 | 淘系售后单查询(列表)【奇门自定义接口】 |
| method | `jushuitan.refund.list.query` |
| 旧版文档 | https://open.jushuitan.com/document.aspx?doc_id=2356 |
| 网关 | `http://a1q40taq0j.api.taobao.com/router/qm` |
| target_app_key | `23060081` |
| 限频 | QPS ≤ 10 |

### 接口说明

淘系售后单查询(列表)【奇门自定义接口】
奇门申请地址：
https://open.taobao.com/docV3.htm?docId=118393&docType=1&source=search#ss13
奇门系统参数的
target_app_key
给
23060081
接口限频：qps 10
奇门接口路由参数:
接口需要额外带上
customer_id
,传不同的customer_id来路由不同的商家链接, 具体的值需要在进行授权的时候向聚水潭获取
customer_id获取方法
：文档中的上线流程  https://openweb.jushuitan.com/doc?docId=250
奇门API调用示例：
https://open.taobao.com/docV3.htm?spm=a219a.7386797.0.0.759a669a4Kh2yK&source=search&docId=112&docType=1
1.实退金额计算规则：实退金额 = 商品应退金额 + 应退运费 - 优惠/差额 + 卖家应补 - 换货金额 - 买家应补
接口字段计算：实退金额=freight+refund-payment-free_amount
2.请求参数中start_ts的说明：
使用ts的查询条件是唯一可避免分页查询过程中因数据变动而导致的漏单问题，原因是该查询条件是数据库中的时间戳，sql server中的行版本号。只要当前这条数据在数据库中有变化任何字段变化ts的值都会自增，全表唯一的自增值，非业务上做的时间值更新。使用ts的查询模板
第一次请求：{"start_ts":1."is_get_total":false,"page_index":1."page_size":100} //第一次请求ts从1开始
第二次请求：{"start_ts":传第一次返回的最大ts值."is_get_total":false,"page_index":1."page_size":100} //一直请求到查不到比入参ts值本身更大的数据为止
奇门自定义调用示例代码C#版本：请参考奇门自定义订单查询文档有完整示例代码“
订单查询示例代码 (https://open.jushuitan.com/document.aspx?doc_id=2352)
”，参考示例代码时请更换对应的method接口名
其他语言如java，php请参考奇门官方示例代码请点击“
奇门官方示例代码及SDK (https://open.taobao.com/docV3.htm?spm=a219a.7386797.0.0.759a669a4Kh2yK&source=search&docId=112&docType=1)
”

### 公共参数

请求地址：

| 环境 | HTTPS请求地址 |
|---|---|
| 正式环境 | http://a1q40taq0j.api.taobao.com/router/qm? |
| 沙箱环境 | 无 |


系统参数：

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| method | string | 是 |  | 接口名称:jushuitan.refund.list.query |

---

### 请求参数

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| page_index | int | 是 |  | 页索引 |
| page_size | int | 是 |  | 页大小，最大100 |
| start_time | string |  |  | 开始时间 |
| end_time | string |  |  | 结束时间 |
| date_type | int |  |  | 时间类型 0:修改时间modified;1:创建时间created;2:确认时间confirm_date;非必填,默认0 |
| wms_co_id | int |  |  | 分仓id |
| shop_id | int |  |  | 店铺id |
| as_ids | int |  |  | 售后单号列表 |
| so_ids | string |  | "111,222,333" | 线上单号列表,多个线上单号以逗号隔开 |
| is_get_total | bool |  |  | 是否查询总条数 |
| start_ts | int |  |  | ts开始时间 |
| end_ts | string |  |  | ts结束时间 |
| is_offline_shop | bool |  |  | shop_id为0且is_offline_shop为true查询线下店铺单据 |
| o_ids | string |  | "111,222,333" | 内部单号列表 |
| status | string |  |  | 售后单状态（WaitConfirm:待确认,Confirmed:已确认,Cancelled:作废,Merged:被合并，Split：被拆分） |
| good_status | string |  |  | 货物状态（BUYER_NOT_RECEIVED:买家未收到货,BUYER_RECEIVED:买家已收到货,BUYER_RETURNED_GOODS:买家已退货,SELLER_RECEIVED:卖家已收到退货 |
| type | string |  |  | 售后类型，普通退货，其它，拒收退货，仅退款，投诉，补发，换货，维修 |
| archive | bool |  | true | 是否查归档订单 |
| order_types | string |  | "普通订单,补发订单,换货订单" | 原订单类型（普通订单,补发订单,换货订单,天猫分销,天猫供销,协同订单,亚马逊货件单,唯品会JITX订单,唯品会JITX待寻仓订单,送仓订单, 普通订单-分销Plus,补发订单-分销Plus,换货订单-分销Plus,天猫供销-分销Plus,协同订单-分销Plus,亚马逊货件单-分销Plus,唯品会JITX订单-分销Plus,唯品会JITX待寻仓订单-分销Plus,送仓订单-分销Plus, 普通订单-供销Plus,补发订单-供销Plus,换货订单-供销Plus,天猫供销-供销Plus,协同订单-供销Plus,亚马逊货件单-供销Plus,唯品会JITX订单-供销Plus,唯品会JITX待寻仓订单-供销Plus,送仓订单-供销Plus, 普通订单-分销Plus-供销Plus,补发订单-分销Plus-供销Plus,换货订单-分销Plus-供销Plus,天猫供销-分销Plus-供销Plus,协同订单-分销Plus-供销Plus,亚马逊货件单-分销Plus-供销Plus,唯品会JITX订单-分销Plus-供销Plus,唯品会JITX待寻仓订单-分销Plus-供销Plus,送仓订单-分销Plus-供销Plus） |
| owner_co_id | int |  |  | 货主编码 |
| is_get_promotion | bool |  |  | 是否查询售后营收小计金额，默认false |

---

### 响应参数

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| page_size | int |  |  | 页大小 |
| page_index | int |  |  | 页索引 |
| data_count | int |  |  | 数据总行数 |
| page_count | int |  |  | 页数 |
| has_next | bool |  |  | 是否有下一页 |
| datas | list |  |  | 数据列表 |

---

### 请求示例

```json
{
  "start_ts": 0,
  "o_ids":"111,222,333" ,
  "date_type": 0,
  "end_time": "null",
  "as_ids": "111,222,333",
  "type": "null",
  "good_status": "null",
  "start_time": "null",
  "shop_id": 0,
  "wms_co_id": 0,
  "so_ids": "111,222,333",
  "end_ts": 0,
  "page_index": 0,
  "is_get_total": true,
  "is_offline_shop": false,
  "page_size": 0,
  "status": "null"
}
```

---

### 响应示例

```json
{
    "page_size":null,
    "page_index":null,
    "data_count":null,
    "page_count":null,
    "has_next":null,
    "datas":[
        {
                "as_id":null,
                "as_date":"null",
                "outer_as_id":"null",
                "so_id":"null",
                "type":"null",
                "modified":"null",
                "status":"null",
                "remark":"null",
                "question_type":"null",
                "warehouse":"null",
                "refund":"null",
                "payment":"null",
                "good_status":"null",
                "shop_buyer_id":"null",
                "shop_id":"null",
                "logistics_company":"null",
                "l_id":"null",
                "o_id":0,
                "order_status":"null",
                "drp_co_id_to":"null",
                "wh_id":null,
                "drp_co_id_from":"null",
                "node":"null",
                "wms_co_id":null,
                "shop_status":"null",
                "freight":"null",
                "batchs":[
                    {
                            "batch_no":"null",
                            "sku_id":"null",
                            "qty":null,
                            "product_date":"null",
                            "supplier_id":null,
                            "supplier_name":"null",
                            "expiration_date":"null"
                    }
                ],
                "created":"null",
                "order_label":"null",
                "ts":"null",
                "labels":"null",
                "refund_version":"null",
                "sns":[
                    {
                            "sku_id":"null",
                            "sn":"null"
                    }
                ],
                "order_type":"null",
                "confirm_date":"null",
                "items":[
                    {
                            "sku_type":"null",
                            "shop_sku_id":"null",
                            "defective_qty":null,
                            "outer_oi_id":"null",
                            "receive_date":"null",
                            "i_id":"null",
                            "combine_sku_id":"null",
                            "asi_id":null,
                            "sku_id":"null",
                            "qty":null,
                            "price":"null",
                            "amount":"null",
                            "name":"null",
                            "pic":"null",
                            "type":"null",
                            "properties_value":"null",
                            "r_qty":null
                    }
                ]
        }
    ]
}
```

---

## 淘系店铺商品资料查询

`jushuitan.itemskumapper.list.query`

| 项 | 内容 |
|---|---|
| 接口名称 | 淘系店铺商品资料查询【奇门自定义接口】 |
| method | `jushuitan.itemskumapper.list.query` |
| 旧版文档 | https://open.jushuitan.com/document.aspx?doc_id=2365 |
| 网关 | `http://a1q40taq0j.api.taobao.com/router/qm` |
| target_app_key | `23060081` |
| 限频 | QPS ≤ 10 |

### 接口说明

淘系店铺商品资料查询【奇门自定义接口】
系统参数沿用奇门接口的系统参数
奇门系统参数的target_app_key  给 23060081
接口限频：qps 10
奇门接口路由参数:
接口需要额外带上customer_id,传不同的customer_id来路由不同的商家链接, 具体的值需要在进行授权的时候向聚水潭获取.
customer_id获取方法
：文档中的上线流程  https://openweb.jushuitan.com/doc?docId=250

### 公共参数

请求地址：

| 环境 | HTTPS请求地址 |
|---|---|
| 正式环境 | http://a1q40taq0j.api.taobao.com/router/qm? |
| 沙箱环境 |  |


系统参数：

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| method | string | 是 |  | 接口名称:jushuitan.itemskumapper.list.query |

---

### 请求参数

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| page_index | int |  | 1 | 第几页，从第一页开始，默认1 |
| page_size | int |  | 50 | 每页多少条，默认30，最大50 |
| modified_begin | string |  | 2021-12-01 13:58:41 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与商品编码不能同时为空 |
| modified_end | string |  | 2021-12-01 13:58:41 | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与商品编码不能同时为空 |
| link_modified_begin | string |  | 2021-12-01 13:58:41 | 商品对应关系修改起始时间 |
| link_modified_end | string |  | 2021-12-01 13:58:41 | 商品对应关系修改结束时间 |
| sku_ids | string |  | lyyi001,lyyi002 | 商品编码（线上商品编码），与修改时间不能同时为空，最多20 |
| shop_id | int |  | 10208692 | 店铺编号 |
| created_begin | string |  | 2021-12-01 13:58:41 | 创建开始时间，与结束时间不能同时为空 |
| created_end | string |  | 2021-12-01 13:58:41 | 创建结束时间，和开始时间不能同时为空 |

---

### 响应参数

| 名称 | 类型 | 是否必须 | 示例值 | 描述 |
|---|---|---|---|---|
| page_size | int |  |  | 每页多少条 |
| page_index | int |  |  | 第几页 |
| data_count | int |  |  | 总条数 |
| page_count | int |  |  | 总页数 |
| has_next | bool |  |  | 是否有下一页 |
| datas | list |  |  |  |

---

### 请求示例

```json
{
    "page_index": 1,
    "page_size": 50,
    "modified_begin": "2024-01-16 09:30:00",
    "modified_end": "2024-01-16 10:00:00"
}
```

---

### 响应示例

```json
{
    "page_size":50,
    "page_index":1,
    "data_count":1,
    "page_count":1,
    "has_next":false,
    "datas":[
        {
            "co_id":13093720,
            "shop_id":15006839,
            "channel":"KWaiShop",
            "i_id":"21083024474734",
            "sku_id":"010614006257006",
            "shop_i_id":"21083024474734",
            "shop_sku_id":"92242470839734",
            "modified":"2024-01-16 09:37:14.733",
            "enabled":true,
            "c_id":1624,
            "shop_qty":0,
            "type":0,
            "created":"2023-08-31 19:15:10.450",
            "pull_off_time":null,
            "outer_sku_code":null,
            "sale_price_max":null,
            "sale_price_min":null,
            "properties_value":"黑色;M【100-115斤/155-160CM】",
            "pic":"https://u1-203.ecukwai.com/bs2/image-kwaishop-product/SKU_IMAGE-3680093734-41d576d8717f446a8528c4d032609555.jpg",
            "link_sku_id":"",
            "link_modified":null,
            "raw_sku_id":"010614006257006",
            "name":"ZMOR+ 凯特大衣高克重羊毛羊绒立体剪裁大衣外套W23DC301001"
        }
    ]
}
```

---
