# 聚水潭开放平台 API 线下文档

本仓库**只含接口文档**，不含任何业务代码。从本 `README.md` 进入各分类即可。

> 抓取日期：2026-11-24  
> 来源：https://openweb.jushuitan.com/dev-doc  
> 共 178 个开放平台接口 + 4 个奇门自定义接口，按官方侧栏分类拆分。

## 公共协议

| 项 | 内容 |
|---|---|
| 请求方法 | **仅支持 HTTP POST** |
| Content-Type | `application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`，值为 JSON 字符串 |
| charset | 固定 `utf-8` |
| version | 固定 `2` |

公共请求参数（全部必填）：

| 参数名称 | 类型 | 说明 |
|---|---|---|
| `app_key` | String | POP 分配给应用的 app_key |
| `access_token` | String | 通过 code 获取的 access_token |
| `timestamp` | Long | UNIX 秒级时间戳，与服务器时差需在 10 分钟内 |
| `charset` | String | 固定 `utf-8` |
| `version` | String | 固定 `2` |
| `sign` | String | 数字签名 |

签名失败常见返回：

```json
{
    "code": 120,
    "msg": "验证失败!无效签名"
}
```

## 分类索引

| 分类 | 接口数 | 线下文档 | 官方入口 |
|---|---|---|---|
| 基础API | 6 | [01-基础API.md](./01-基础API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=1&docId=1) |
| 商品API | 20 | [02-商品API.md](./02-商品API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=486) |
| 库存API | 6 | [03-库存API.md](./03-库存API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=3&docId=15) |
| 订单API | 16 | [04-订单API.md](./04-订单API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=4&docId=1497) |
| 物流API | 4 | [05-物流API.md](./05-物流API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=5&docId=23) |
| 采购API | 12 | [06-采购API.md](./06-采购API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=6&docId=26) |
| 入库API | 6 | [07-入库API.md](./07-入库API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=7&docId=270) |
| 出库API | 5 | [08-出库API.md](./08-出库API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=8&docId=34) |
| 售后API | 10 | [09-售后API.md](./09-售后API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=9&docId=1443) |
| 其它出入库API | 3 | [10-其它出入库API.md](./10-其它出入库API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=10&docId=42) |
| 调拨API | 6 | [12-调拨API.md](./12-调拨API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=12&docId=47) |
| 跨境API | 10 | [44-跨境API.md](./44-跨境API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=44&docId=1144) |
| 聚财快API | 2 | [65-聚财快API.md](./65-聚财快API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=65&docId=1639) |
| 聚工单开放API | 3 | [46-聚工单开放API.md](./46-聚工单开放API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=46&docId=1011) |
| 财务API | 5 | [49-财务API.md](./49-财务API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=49&docId=1246) |
| 拣货批次API | 13 | [51-拣货批次API.md](./51-拣货批次API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=730) |
| 奇门API | 4 | [56-奇门API.md](./56-奇门API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=56) |
| 票聚API | 5 | [61-票聚API.md](./61-票聚API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=61&docId=1047) |
| 运营云仓API | 9 | [43-运营云仓API.md](./43-运营云仓API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=43&docId=340) |
| 胜算API | 20 | [36-胜算API.md](./36-胜算API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1377) |
| WMS API | 17 | [22-WMS-API.md](./22-WMS-API.md) | [打开](https://openweb.jushuitan.com/dev-doc?docType=22&docId=818) |

## 全量接口清单

### 基础API

| 接口 | 路径 | docId |
|---|---|---|
| 店铺查询 | `/open/shops/query` | 1 |
| 物流公司查询 | `/open/logisticscompany/query` | 2 |
| 仓库查询 | `/open/wms/partner/query` | 3 |
| 商家用户信息 | `/open/webapi/userapi/company/getcompanyusers` | 611 |
| 查询我的供应商列表（新） | `/open/api/drp/inneropen/partner/channel/querymysupplier` | 862 |
| 分销商查询 | `/open/api/drp/inneropen/partner/supplier/querymychannel` | 955 |

### 商品API

| 接口 | 路径 | docId |
|---|---|---|
| 商品类目上传/更新 | `/open/webapi/itemapi/category/addorupdate` | 486 |
| 商品历史成本价分页查询 | `/open/webapi/itemapi/skuhisvalues/getpagelist` | 1609 |
| 绑定/解绑商品对应关系 | `/open/webapi/itemapi/skulink/bindskulinks` | 1117 |
| 批量上传/更新普通商品资料（新版） | `/open/webapi/itemapi/itemsku/itemskubatchupload` | 1074 |
| 商品款式更新 | `/open/webapi/itemapi/itemskuim/itemupload` | 1032 |
| 商品恢复数据查询 | `/open/webapi/itemapi/itemsku/queryitemskuopshistory` | 836 |
| 更新商品库容信息 | `/open/webapi/itemapi/itemsku/setskubins` | 683 |
| 商品历史成本价上传 | `/open/jushuitan/itemsku/costprice/upload` | 600 |
| BOM信息上传 | `/open/webapi/itemapi/bom/save` | 495 |
| 普通商品资料上传/更新（旧版） | `/open/jushuitan/itemsku/upload` | 4 |
| 新增/修改商品多供应商 | `/open/webapi/itemapi/suppliersku/save` | 483 |
| 商品多供应商查询 | `/open/webapi/itemapi/suppliersku/getsupplierskulist` | 449 |
| 商品BOM信息查询 | `/open/webapi/itemapi/bom/getskubompagelist` | 358 |
| 组合装商品上传（批量上传） | `/open/item/combinesku/upload` | 65 |
| 普通商品资料查询（按sku查询） | `/open/sku/query` | 14 |
| 普通商品查询（按款查询） | `/open/mall/item/query` | 13 |
| 商品类目查询 | `/open/category/query` | 12 |
| 组合装商品查询 | `/open/combine/sku/query` | 11 |
| 店铺商品资料查询 | `/open/skumap/query` | 10 |
| 店铺商品资料上传 | `/open/jushuitan/skumap/upload` | 5 |

### 库存API

| 接口 | 路径 | docId |
|---|---|---|
| 商品库存查询 | `/open/inventory/query` | 15 |
| 库存盘点查询 | `/open/inventory/count/query` | 16 |
| 库存盘点-修改库存 | `/open/jushuitan/inventoryv2/upload` | 85 |
| 导入/更新虚拟库存 | `/open/webapi/itemapi/iteminventory/batchupdatewmsvirtualqtys` | 631 |
| 箱及仓位库存批量查询 | `/open/webapi/wmsapi/pack/pagequerypackanditems` | 1125 |
| 唯一码库存查询 | `/open/webapi/wmsapi/skusn/queryskusnstocks` | 1645 |

### 订单API

| 接口 | 路径 | docId |
|---|---|---|
| 订单反取消 | `/open/webapi/orderapi/modifyorder/uncancels` | 1497 |
| 修改自有商城订单收件人信息 | `/open/jushuitan/orderaddress/update` | 1435 |
| 修改发票信息 | `/open/webapi/orderapi/orderinvoice/saveorderinvoicev2` | 1396 |
| 修改订单快递 | `/open/webapi/orderapi/modifyorder/modifyorderlc` | 1367 |
| 修改订单卖家备注（按线上单号） | `/open/webapi/orderapi/modifyorder/saveremark` | 944 |
| 订单指定发货仓 | `/open/orders/modifywms/upload` | 362 |
| 订单上传(商家自有商城、跨境线下) | `/open/jushuitan/orders/upload` | 18 |
| 订单转异常 | `/open/webapi/orderapi/questionorder/questions` | 263 |
| 订单拆分 | `/open/jushuitan/drporder/split` | 233 |
| 修改订单备注旗帜(会同步至平台) | `/open/order/remark/flag/update` | 214 |
| 修改订单卖家备注（按内部单号） | `/open/jushuitan/order/remark/upload` | 196 |
| 通过订单号修改 便签丨线下备注 | `/open/order/node/soid/set` | 118 |
| 订单标签（新增/移除） | `/open/jushuitan/order/label/upload` | 72 |
| 订单发货-新 | `/open/order/sent/upload` | 62 |
| 订单查询 | `/open/orders/single/query` | 22 |
| 订单取消-按内部单号取消 | `/open/jushuitan/orderbyoid/cancel` | 19 |

### 物流API

| 接口 | 路径 | docId |
|---|---|---|
| 批量快递登记 | `/open/express/register/upload` | 23 |
| 称重并发货/快递分拣 | `/open/orders/weight/send/upload` | 24 |
| 发货信息查询 | `/open/logistic/query` | 25 |
| 快递登记查询 | `/open/webapi/aftersaleapi/getasexpress` | 1395 |

### 采购API

| 接口 | 路径 | docId |
|---|---|---|
| 采购单查询 | `/open/purchase/query` | 26 |
| 采购单上传 | `/open/jushuitan/purchase/upload` | 27 |
| 供应商上传 | `/open/supplier/upload` | 28 |
| 供应商查询 | `/open/supplier/query` | 29 |
| 加工单查询 | `/open/jushuitan/manufacture/query` | 52 |
| 加工单上传 | `/open/jushuitan/manufacture/upload` | 55 |
| 采购单加工单标签（新增/移除） | `/open/jushuitan/purchaselabel/upload` | 63 |
| 预约入库上传 | `/open/jushuitan/appointmentin/upload` | 92 |
| 预约入库查询列表 | `/open/jushuitan/purchasebooking/query` | 156 |
| 变更采购单状态 | `/open/jushuitan/purchase/change/status` | 193 |
| 采购单/加工单/预约入库单作废 | `/open/webapi/wmsapi/purchase/cancel` | 452 |
| 修改采购单 | `/open/webapi/wmsapi/openpurchase/editpurchase` | 698 |

### 入库API

| 接口 | 路径 | docId |
|---|---|---|
| 生成采购入库单-支持批量 | `/open/webapi/wmsapi/purchasein/createbatch` | 270 |
| 采购入库取消 | `/open/jushuitan/purchasein/cancel` | 317 |
| 批量录入唯一码 | `/open/webapi/wmsapi/skusn/batchadd/simple` | 670 |
| 批量录入箱唯一码 | `/open/webapi/wmsapi/packsn/batchadd` | 671 |
| 采购入库查询 | `/open/webapi/wmsapi/purchasein/purchaseinquery` | 901 |
| 生产批次管理创建 | `/open/webapi/wmsapi/producedbatch/createproducedbatch` | 1137 |

### 出库API

| 接口 | 路径 | docId |
|---|---|---|
| 销售出库查询 | `/open/orders/out/simple/query` | 34 |
| 出库发货 | `/open/orders/wms/sent/upload` | 35 |
| 采购退货查询 | `/open/purchaseout/query` | 36 |
| 采购退货取消 | `/open/jushuitan/purchaseout/cancel` | 93 |
| 生成采购退货单-支持批量 | `/open/webapi/wmsapi/purchaseout/createbatch` | 269 |

### 售后API

| 接口 | 路径 | docId |
|---|---|---|
| 设置售后标签 | `/open/webapi/aftersaleapi/setaslabels` | 1443 |
| 唯一码批量确认收货 | `/open/webapi/aftersaleapi/confirmgoodsbyskusns` | 743 |
| 售后单作废 | `/open/webapi/aftersaleapi/open/cancel` | 582 |
| 售后单确认 | `/open/webapi/aftersaleapi/open/confirm` | 581 |
| 售后(退货退款)查询 | `/open/refund/single/query` | 38 |
| 售后单反确认 | `/open/webapi/aftersaleapi/open/unconfirm` | 579 |
| 售后-确认收到货物（可分批确认） | `/open/webapi/aftersaleapi/confirmgoods` | 272 |
| 售后上传（无信息件) | `/open/aftersale/noinfo/upload` | 124 |
| 售后上传 | `/open/aftersale/upload` | 41 |
| 销售退仓-实际收货查询 | `/open/aftersale/received/query` | 40 |

### 其它出入库API

| 接口 | 路径 | docId |
|---|---|---|
| 其它出入库查询 | `/open/other/inout/query` | 42 |
| 新建其它出入库 | `/open/jushuitan/otherinout/upload` | 43 |
| 其它出入库状态变更 | `/open/jushuitan/otherinout/cancel` | 223 |

### 调拨API

| 接口 | 路径 | docId |
|---|---|---|
| 调拨单查询 | `/open/allocate/query` | 47 |
| 库存调拨上传（跨仓调拨） | `/open/allocate/kc/upload` | 48 |
| 库存调拨上传（仓内调拨） | `/open/jushuitan/allocate/in/upload` | 49 |
| 调拨单确认 | `/open/jushuitan/allocate/confirm` | 64 |
| 调拨单取消 | `/open/jushuitan/allocate/cancel/v2` | 266 |
| 创建调拨差异单 | `/open/jushuitan/diffallocate/create` | 357 |

### 跨境API

| 接口 | 路径 | docId |
|---|---|---|
| 获取用户启用的物流列表及渠道 | `/open/webapi/cblogisticsapi/cbchannels/getuseropenlogisticsinfo` | 1144 |
| 查询商品报关信息 | `/open/webapi/cb/cbitem/getdeclares` | 1207 |
| 查询调拨单头程费用 | `/open/webapi/wmsapi/allocate/loadallocatefeev2` | 1280 |
| 跨境售后单查询 | `/open/webapi/cb/cborder/getrefunds` | 1110 |
| 送仓包裹返回仓 | `/open/webapi/cbdtwapi/cbdtw/getpackageinfo` | 1426 |
| 尾程运费回写接口 | `/open/webapi/cblogisticsapi/cbexpressstatement/savefee` | 489 |
| 1688商品映射推送 | `/open/webapi/globalapi/skumap/mapping` | 502 |
| 更新订单跨境物流信息 | `/open/jushuitan/crossborder/forwarder/upload` | 71 |
| 创建头程单 | `/open/webapi/cb/cbfirsttrip/createfirsttrip` | 891 |
| 跨境订单查询 | `/open/webapi/cb/cborder/getorders` | 1109 |

### 聚财快API

| 接口 | 路径 | docId |
|---|---|---|
| 智能会计中心_档案数据_批量保存 | `/open/api/ckopen/sac/archivedata/batchsave` | 1639 |
| 智能会计中心_单据数据_批量保存 | `/open/api/ckopen/sac/notedata/batchsave` | 1640 |

### 聚工单开放API

| 接口 | 路径 | docId |
|---|---|---|
| 【收费】更新工单数据 | `/open/api/gd/open/workorder/updateworkorder` | 1011 |
| 【收费】添加工单数据 | `/open/api/gd/open/workorder/addworkorder` | 1127 |
| 【收费】查询所有工单类型列表 | `/open/api/gd/open/workordertype/queryallworkordertype` | 1130 |

### 财务API

| 接口 | 路径 | docId |
|---|---|---|
| 付款单列表查询 | `/open/api/fmsopen/querypayment` | 1246 |
| 应付单列表查询 | `/open/api/fmsopen/querypayable` | 1247 |
| 【收费】台账数据查询 | `/open/webapi/fms/standingbook/getlistbybatch` | 1320 |
| 业务费用列表查询 | `/open/api/fmsopen/queryoperatingfee` | 1414 |
| 费用项目查询 | `/open/api/fmsopen/queryfinanceproject` | 1437 |

### 拣货批次API

| 接口 | 路径 | docId |
|---|---|---|
| 校验播种车的状态是否可用 | `/open/jushuitan/carryid/check` | 730 |
| 绑定播种柜号和播种车 | `/open/jushuitan/binid/carryid/bind` | 729 |
| 解绑批次拣货车/播种车 | `/open/webapi/wmsapi/wave/unbindwavecarryid` | 467 |
| 播种回传（不出库） | `/open/jushuitan/seed/return` | 456 |
| 绑定播种车 | `/open/webapi/wmsapi/wave/bindbinidcarryid` | 111 |
| 根据播种车号解绑出库单 | `/open/webapi/wmsapi/wave/unbindinoutbycarryid` | 232 |
| 播种回传（出库） | `/open/jushuitan/seed/callback` | 194 |
| 获取播种批次信息（支持新版三方仓查询） | `/open/jushuitan/wave/get` | 188 |
| 更新批次拣货状态 | `/open/jushuitan/wavestatus/upload` | 180 |
| 指定机器人批次 | `/open/jushuitan/agv/wave/assign` | 172 |
| 批次预占重算 | `/open/jushuitan/prereducewave/query` | 160 |
| 机器人获取批次 | `/open/jushuitan/pickwave/query` | 159 |
| 拣货批次管理查询 | `/open/webapi/wmsapi/wavequery/loadwavesbyfilter` | 112 |

### 奇门API

走阿里奇门网关，不是开放平台 `biz` 协议。新版侧栏无接口页，详见 [56-奇门API.md](./56-奇门API.md)。

| 接口 | 路径 | docId |
|---|---|---|
| 淘系订单查询列表 | `jushuitan.order.list.query` | 2352 |
| 淘系销售出库单(列表)查询 | `jushuitan.saleout.list.query` | 2355 |
| 淘系售后单查询(列表) | `jushuitan.refund.list.query` | 2356 |
| 淘系店铺商品资料查询 | `jushuitan.itemskumapper.list.query` | 2365 |

### 票聚API

| 接口 | 路径 | docId |
|---|---|---|
| 【收费】开票结果查询-奇门 | `37zf6iaq2d.jushuitan.shengsuan.invoiceresult.query` | 1047 |
| 修改商品基本开票信息 | `/open/webapi/itemapi/invoice/openimport` | 1197 |
| 【收费】发票回调 | `/open/fms/intranet/invoice/callback` | 1261 |
| 【收费】开票结果查询 | `/open/fms/intranet/queryinvoiceinfoforopen` | 1430 |
| 【收费】导入非订单开票申请 | `/open/fms/general/apply/manual/import` | 1623 |

### 运营云仓API

| 接口 | 路径 | docId |
|---|---|---|
| 虚拟仓调拨单据分页接口 | `/open/webapi/itemapi/lockwarehouse/getlwhallocationlist` | 340 |
| 虚拟仓分配归还单据分页接口 | `/open/webapi/itemapi/lockwarehouse/getlwhoperationlist` | 341 |
| 虚拟仓调拨单创建接口 | `/open/webapi/itemapi/lockwarehouse/lwhallocationcreate` | 342 |
| 虚拟仓分配/归还单据创建接口 | `/open/webapi/itemapi/lockwarehouse/lwhoperationcreate` | 343 |
| 获取虚拟仓列表 | `/open/webapi/itemapi/lockwarehouse/getwarehouselist` | 490 |
| 虚拟仓商品库存查询 | `/open/webapi/itemapi/iteminventory/getvirtualstock` | 625 |
| 创建/更新虚拟仓采购申请 | `/open/webapi/itemapi/lockwarehouse/lockpurchase/createorupdatepurchase` | 799 |
| 查询采购申请（包含虚拟仓和非虚拟仓） | `/open/webapi/itemapi/lockwarehouse/lockpurchase/getpagelockpurchases` | 802 |
| 获取运营云仓出入库台账 | `/open/webapi/itemapi/lockwarehouse/getlwhinout` | 1648 |

### 胜算API

| 接口 | 路径 | docId |
|---|---|---|
| 上传多成本 | `/open/webapi/pfopen/dataaccess/uploadcostpricedata` | 1377 |
| 上传外采订单成本 | `/open/webapi/pfopen/dataaccess/uploadordercostpricedata` | 1378 |
| 获取上传批次号 | `/open/webapi/pfopen/dataaccess/createuploadbatchnum` | 1379 |
| 获取批次状态信息 | `/open/webapi/pfopen/dataaccess/getdataaccessjob` | 1380 |
| 批次取消 | `/open/webapi/pfopen/dataaccess/canceljob` | 1381 |
| 获取批次异常数据 | `/open/webapi/pfopen/dataaccess/geterrorrecords` | 1382 |
| 上传订单费用 | `/open/webapi/pfopen/dataaccess/uploadorderfeedata` | 1493 |
| 获取利润表项目列表 | `/open/webapi/pfopen/pfopenalifee/getcostsubgrouplist` | 1576 |
| 【胜算收费接口】获取平台汇总账单列表 | `/open/webapi/pfopen/pfopenalifee/getalipayfeelist` | 1577 |
| 【聚核账收费接口】聚核账出入库流水明细 | `/open/webapi/pfopen/inoutchecking/getinoutresultdetailopen` | 1583 |
| 【胜算/聚核账 收费接口】平台账单 | `/open/webapi/pfopen/pfopenalifee/getopenalipaylist` | 1584 |
| 【胜算/聚核账 收费接口】获取平台账单分摊后数据 | `/open/webapi/pfopen/pfopenalifee/getalipayitems` | 1596 |
| 【胜算收费接口】获取胜算店铺级推广费 | `/open/webapi/pfopen/pfopenalifee/getopenalipaypromotionfee` | 972 |
| 【聚核账收费接口】分层获取出入库明细数据 | `/open/webapi/pfapi/openinoutchecking/loadinoutresultdetaildataforlevel` | 532 |
| 【聚核账收费接口】回写出入库明细推送状态 | `/open/webapi/pfapi/openinoutchecking/writebackinoutresultdetailforpush` | 533 |
| 【聚核账收费接口】获取新出入库流水汇总数据 | `/open/webapi/pfopen/inoutchecking/getinoutgroupdetail` | 634 |
| 【聚核账收费接口】汇总推送状态回写 | `/open/webapi/pfopen/inoutchecking/pushinoutgroupdetailresult` | 635 |
| 【胜算收费接口】获取胜算日常记账数据 | `/open/webapi/pfopen/pfopenorderfee/getopenfeeflowing` | 970 |
| 【胜算收费接口】获取胜算链接级推广费数据 | `/open/webapi/pfopen/pfopenalifee/getopenpfpromotionshopitem` | 971 |
| 【胜算收费接口】获取胜算平台原始账单 | `/open/webapi/pfopen/pfopenalifee/getopenalipaybillrecords` | 973 |

### WMS API

| 接口 | 路径 | docId |
|---|---|---|
| 批量下架 | `/open/webapi/wmsapi/openoffshelve/skubatchoffshelve` | 818 |
| 批量上架 | `/open/webapi/wmsapi/openshelve/skubatchshelve` | 819 |
| 发货装箱功能 | `/open/webapi/wmsapi/shippingpack/addshippingpack` | 986 |
| 唯一码进出流水查询 | `/open/webapi/wmsapi/skusn/queryinoutitemskusns` | 996 |
| 打包机保存视频记录 | `/open/webapi/wmsapi/packageentries/saveipcvediorecord` | 1030 |
| 发货-强制审核单件商品缺货订单 | `/open/webapi/wmsapi/checkoutopen/singleorderconfirms` | 593 |
| 查询极速发货订单数V2 | `/open/webapi/wmsapi/checkout/getfastdeliveryordercountv2` | 1319 |
| 查询商品的推荐仓位 | `/open/webapi/wmsapi/openskubinquery/recommendskubin` | 1503 |
| 生成快销标签 | `/open/webapi/wmsapi/openp2dskusn/createskusn` | 322 |
| 强制审核单件商品缺货订单并入库 | `/open/jushuitan/order/single/confirm` | 73 |
| 查询WMS工作日志 | `/open/webapi/wmsapi/worklog/getworklog` | 76 |
| 工作量补入 | `/open/webapi/wmsapi/worklog/workloadappend` | 154 |
| 查询快销唯一码信息 | `/open/jushuitan/skusn/load` | 173 |
| 跟踪信息查询 | `/open/jushuitan/skusn/query` | 252 |
| 进出仓流水 | `/open/jushuitan/inout/water/query` | 54 |
| 快销到货 | `/open/jushuitan/quicksale/arrival` | 436 |
| 根据箱号查询箱内商品推荐仓位 | `/open/webapi/wmsapi/openskubinquery/findskubin` | 450 |
