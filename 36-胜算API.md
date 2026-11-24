# 聚水潭开放平台 · 胜算API（线下版）

> 抓取日期：2026-11-23  
> 分类：胜算API（docType=36）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=36&docId=1377

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 上传多成本 | `/open/webapi/pfopen/dataaccess/uploadcostpricedata` | 1377 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1377) |
| 上传外采订单成本 | `/open/webapi/pfopen/dataaccess/uploadordercostpricedata` | 1378 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1378) |
| 获取上传批次号 | `/open/webapi/pfopen/dataaccess/createuploadbatchnum` | 1379 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1379) |
| 获取批次状态信息 | `/open/webapi/pfopen/dataaccess/getdataaccessjob` | 1380 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1380) |
| 批次取消 | `/open/webapi/pfopen/dataaccess/canceljob` | 1381 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1381) |
| 获取批次异常数据 | `/open/webapi/pfopen/dataaccess/geterrorrecords` | 1382 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1382) |
| 上传订单费用 | `/open/webapi/pfopen/dataaccess/uploadorderfeedata` | 1493 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1493) |
| 获取利润表项目列表 | `/open/webapi/pfopen/pfopenalifee/getcostsubgrouplist` | 1576 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1576) |
| 【胜算收费接口】获取平台汇总账单列表 | `/open/webapi/pfopen/pfopenalifee/getalipayfeelist` | 1577 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1577) |
| 【聚核账收费接口】聚核账出入库流水明细 | `/open/webapi/pfopen/inoutchecking/getinoutresultdetailopen` | 1583 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1583) |
| 【胜算/聚核账 收费接口】平台账单 | `/open/webapi/pfopen/pfopenalifee/getopenalipaylist` | 1584 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1584) |
| 【胜算/聚核账 收费接口】获取平台账单分摊后数据 | `/open/webapi/pfopen/pfopenalifee/getalipayitems` | 1596 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=1596) |
| 【胜算收费接口】获取胜算店铺级推广费 | `/open/webapi/pfopen/pfopenalifee/getopenalipaypromotionfee` | 972 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=972) |
| 【聚核账收费接口】分层获取出入库明细数据 | `/open/webapi/pfapi/openinoutchecking/loadinoutresultdetaildataforlevel` | 532 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=532) |
| 【聚核账收费接口】回写出入库明细推送状态 | `/open/webapi/pfapi/openinoutchecking/writebackinoutresultdetailforpush` | 533 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=533) |
| 【聚核账收费接口】获取新出入库流水汇总数据 | `/open/webapi/pfopen/inoutchecking/getinoutgroupdetail` | 634 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=634) |
| 【聚核账收费接口】汇总推送状态回写 | `/open/webapi/pfopen/inoutchecking/pushinoutgroupdetailresult` | 635 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=635) |
| 【胜算收费接口】获取胜算日常记账数据 | `/open/webapi/pfopen/pfopenorderfee/getopenfeeflowing` | 970 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=970) |
| 【胜算收费接口】获取胜算链接级推广费数据 | `/open/webapi/pfopen/pfopenalifee/getopenpfpromotionshopitem` | 971 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=971) |
| 【胜算收费接口】获取胜算平台原始账单 | `/open/webapi/pfopen/pfopenalifee/getopenalipaybillrecords` | 973 | [打开](https://openweb.jushuitan.com/dev-doc?docType=36&docId=973) |

## 目录

- [上传多成本](#上传多成本)
- [上传外采订单成本](#上传外采订单成本)
- [获取上传批次号](#获取上传批次号)
- [获取批次状态信息](#获取批次状态信息)
- [批次取消](#批次取消)
- [获取批次异常数据](#获取批次异常数据)
- [上传订单费用](#上传订单费用)
- [获取利润表项目列表](#获取利润表项目列表)
- [【胜算收费接口】获取平台汇总账单列表](#胜算收费接口获取平台汇总账单列表)
- [【聚核账收费接口】聚核账出入库流水明细](#聚核账收费接口聚核账出入库流水明细)
- [【胜算/聚核账 收费接口】平台账单](#胜算聚核账-收费接口平台账单)
- [【胜算/聚核账 收费接口】获取平台账单分摊后数据](#胜算聚核账-收费接口获取平台账单分摊后数据)
- [【胜算收费接口】获取胜算店铺级推广费](#胜算收费接口获取胜算店铺级推广费)
- [【聚核账收费接口】分层获取出入库明细数据](#聚核账收费接口分层获取出入库明细数据)
- [【聚核账收费接口】回写出入库明细推送状态](#聚核账收费接口回写出入库明细推送状态)
- [【聚核账收费接口】获取新出入库流水汇总数据](#聚核账收费接口获取新出入库流水汇总数据)
- [【聚核账收费接口】汇总推送状态回写](#聚核账收费接口汇总推送状态回写)
- [【胜算收费接口】获取胜算日常记账数据](#胜算收费接口获取胜算日常记账数据)
- [【胜算收费接口】获取胜算链接级推广费数据](#胜算收费接口获取胜算链接级推广费数据)
- [【胜算收费接口】获取胜算平台原始账单](#胜算收费接口获取胜算平台原始账单)

---

## 上传多成本

`/open/webapi/pfopen/dataaccess/uploadcostpricedata`

| 项 | 内容 |
|---|---|
| 接口名称 | 上传多成本 |
| 接口路径 | `/open/webapi/pfopen/dataaccess/uploadcostpricedata` |
| docType / docId | 36 / 1377 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1377 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/dataaccess/uploadcostpricedata` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/dataaccess/uploadcostpricedata` |


### 接口说明

调用流程
 step1：调用 &#x27;获取上传批次号&#x27; 接口获取批次号(/open/webapi/pfopen/dataaccess/createuploadbatchnum)。
 step2：联同上步返回的批次号，调用本接口上传多成本，分页传，每页最多500条数据，当本批次上传任务结束时 is_completed赋true，表示本批次上传结束。
 step3：上传完成之后，可通过 &#x27;获取批次状态信息&#x27; 接口查看批次执行状态(/open/webapi/pfopen/dataaccess/getdataaccessjob)；
 如果批次执行状态显示成功后，等待半小时，可到 设置>成本维护>多成本 页面查看上传的数据。
 如果显示失败， 可通过 ‘获取批次异常数据’接口查看并下载异常数据（/open/webapi/pfopen/dataaccess/geterrorrecords） 。本批次数据不入库，可调整后重新上传。

 另外，如果批次上传过程中如需取消整个批次，可通过‘批次取消’接口传入需要取消的批次号即可（/open/webapi/pfopen/dataaccess/canceljob） ； 上传完成后就不允许再取消。如需对已上传数据进行更新，查看下方“数据更新逻辑”。

 数据更新逻辑
 本接口默认是覆盖逻辑，相同的数据如果之前已经存在，会进行覆盖，以最新上传的数据为准。所以如果之前的值有误，修改正确后重新上传即可。除非上传时请求参数“ override_type”填写的是“skip”，则不更新。

 业务校验
 上传的数据会进行校验，如需了解上传数据的要求可至 设置>成本维护>多成本 页面中的导入模板中查看。

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
| task_id | string | 是 | 2000000000010830518 | 批次号 |
| is_completed | boolean | 是 | false | 结束上传标识，本批次结束时，请上传true。 |
| override_type | string | 否 | overrideold | 数据覆盖方式：日期和商品相同需要覆盖原有值的填overrideold；日期和商品相同需要忽略的填skip |
| id_type | string | 否 | SkuId | 编码类型 商品编码 SkuId；店铺商品编码：ShopSkuId |
| wms_co_id | string | 否 | 10423611 | 分仓Id，如果为空则导入至本公司 |
| cost_price_type | string | 否 | User1 | 成本价方案类型：共有4套多成本，第一套多成本填User1；第二套多成本填User2；第三套多成本填User3；第四套多成本填User4；具体用哪套请咨询财务人员。 |
| is_excduplicate | boolean | 否 | false | 是否去除重复(根据bizId去重，默认false不去重) |
| upload_datas | array | 是 |  | 上传数据列表 |
| upload_datas[] | object | 否 |  |  |
| upload_datas[].biz_id | string | 否 |  | 业务键，如果需要去重请传入业务键，系统会根据上传的业务键进行去重 |
| upload_datas[].upload_data | object | 是 |  | 上传的数据对象 |
| upload_datas[].upload_data.sku_id | string | 是 | a01 | 商品的编码 |
| upload_datas[].upload_data.cost_price | number | 否 | 3 | 商品成本价 |
| upload_datas[].upload_data.shop_name | string | 否 | 小红书第5店铺 | 店铺名称 |
| upload_datas[].upload_data.shop_id | integer | 否 | 10407999 | 店铺编码。如果需要限定此多成本仅适用于此店铺时，可输入店铺id |
| upload_datas[].upload_data.his_price | number | 否 | 3 | 历史成本价：如果填写此字段，则必须填写截止日期 |
| upload_datas[].upload_data.cost_date | string | 否 | 2026-01-05 | 截止日期：如果填写此字段，则必须填写历史成本价 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | object | 是 |  |  |
| data.task_id | string | 是 |  | 批次号id |
| data.task_detail_id | string | 是 |  | 批次子任务id |

### 请求示例

```json
{
  "is_excduplicate": true,
  "override_type": "overrideold",
  "wms_co_id": "",
  "cost_price_type": "",
  "upload_datas": [
    {
      "upload_data": {
        "cost_date": "2026-01-05",
        "shop_id": 10407999,
        "sku_id": "1222221214",
        "shop_name": "小红书第5店铺",
        "his_price": 3,
        "cost_price": 
      },
      {
      "upload_data": {
        "cost_date": "",
        "shop_id": ,
        "sku_id": "1222221214",
        "shop_name": "小红书第5店铺",
        "his_price": ,
        "cost_price": 3
      },
      "biz_id": ""
    }
  ],
  "task_id": "2000000000010830518",
  "id_type": "_sku_id",
  "is_completed": "false"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "task_detail_id": "",
    "task_id": ""
  }
}
```


### 异常示例

_无_


---

## 上传外采订单成本

`/open/webapi/pfopen/dataaccess/uploadordercostpricedata`

| 项 | 内容 |
|---|---|
| 接口名称 | 上传外采订单成本 |
| 接口路径 | `/open/webapi/pfopen/dataaccess/uploadordercostpricedata` |
| docType / docId | 36 / 1378 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1378 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/dataaccess/uploadordercostpricedata` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/dataaccess/uploadordercostpricedata` |


### 接口说明

调用流程
 step1：调用 &#x27;获取上传批次号&#x27; 接口获取批次号(/open/webapi/pfopen/dataaccess/createuploadbatchnum)。
 step2：联同上步返回的批次号，调用本接口上传多成本，分页传，每页最多500条数据，当本批次上传任务结束时 is_completed赋true，表示本批次上传结束。
 step3：上传完成之后，可通过 &#x27;获取批次状态信息&#x27; 接口查看批次执行状态(/open/webapi/pfopen/dataaccess/getdataaccessjob)；
 如果批次执行状态显示成功后，等待半小时，可到 设置>成本维护>常规成本>外采订单成本 页面查看上传的数据。
 如果显示失败， 可通过 ‘获取批次异常数据’接口查看并下载异常数据（/open/webapi/pfopen/dataaccess/geterrorrecords） 。本批次数据不入库，可调整后重新上传。
 另外，如果批次上传过程中如需取消整个批次，可通过‘批次取消’接口传入需要取消的批次号即可（/open/webapi/pfopen/dataaccess/canceljob） ； 上传完成后就不允许再取消。如需对已上传数据进行更新，查看下方“数据更新逻辑”。

 数据更新逻辑
 本接口是覆盖逻辑，相同的数据如果之前已经存在，会进行覆盖，以最新上传的数据为准。所以如果之前的值有误，修改正确后重新上传即可。

 业务校验
 上传的数据会进行校验，如需了解上传数据的要求可至 设置>成本维护>常规成本> 外采订单成本 页面中的导入模板中查看。

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
| task_id | string | 是 | 2000000000010825910 | 批次号 |
| is_completed | boolean | 是 | false | 结束上传标识，本批次结束时，请上传true。 |
| is_excduplicate | string | 是 | false | 是否去除重复(根据bizId去重，默认false不去重) |
| upload_datas | array | 是 |  | 上传数据列表 |
| upload_datas[] | object | 否 |  |  |
| upload_datas[].biz_id | string | 否 |  | 业务键，如果需要去重请传入业务键，系统会根据上传的业务键进行去重 |
| upload_datas[].upload_data | object | 是 |  | 上传的数据对象 |
| upload_datas[].upload_data.freight | number | 否 | 0 | 运费支出 |
| upload_datas[].upload_data.so_id | string | 否 | 12222212124 | 线上订单号，与内部订单号必填写其一 |
| upload_datas[].upload_data.o_id | string | 否 | 12222212124 | 内部订单号，与线上订单号必填写其一 |
| upload_datas[].upload_data.cost_price | number | 是 | 12.33 | 商品的成本价 |
| upload_datas[].upload_data.sku_name | string | 否 | 12222212124商品 | 商品名称 |
| upload_datas[].upload_data.sku_id | string | 是 | 12222212124 | 商品编码 |
| upload_datas[].upload_data.unitSkuLength | string | 否 | 10.11 | 单个商品的长（如果用不到此字段则不需要传） |
| upload_datas[].upload_data.unitSkuWidth | string | 否 | 10.11 | 单个商品的宽（如果用不到此字段则不需要传） |
| upload_datas[].upload_data.unitSkuHeight | string | 否 | 10.11 | 单个商品的高（如果用不到此字段则不需要传） |
| upload_datas[].upload_data.unitSkuVolume | string | 否 | 1033.3643 | 单个商品的体积（长*宽*高） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | object | 是 |  |  |
| data.task_id | string | 是 |  | 批次号id |
| data.task_detail_id | string | 是 |  | 批次子任务id |

### 请求示例

```json
{
  "is_excduplicate": "",
  "upload_datas": [
    {
      "upload_data": {
        "so_id": "12222212124",
        "freight": 0,
        "o_id": "12222212124",
        "sku_name": "款式成本2",
        "sku_id": "12222212124",
        "cost_price": 12
      },
      "biz_id": ""
    }
  ],
  "task_id": "2000000000010825910",
  "is_completed": "false"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "task_detail_id": "",
    "task_id": ""
  }
}
```


### 异常示例

_无_


---

## 获取上传批次号

`/open/webapi/pfopen/dataaccess/createuploadbatchnum`

| 项 | 内容 |
|---|---|
| 接口名称 | 获取上传批次号 |
| 接口路径 | `/open/webapi/pfopen/dataaccess/createuploadbatchnum` |
| docType / docId | 36 / 1379 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1379 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/dataaccess/createuploadbatchnum` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/dataaccess/createuploadbatchnum` |


### 接口说明

所有胜算上传的接口都需要先通过此接口获取上传的批次号；获取到批次号之后连同业务数据一起上传。

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
| shop_id | string | 否 |  | 店铺ID，可空 |
| task_type | string | 是 | 1 | 上传数据的类型：1 上传多成本，2 上传订单自定义成本，7 订单费 |
| run_type | integer | 是 | 0 | 执行方式： 默认传0，上传多成本时传1 |
| data_count | string | 是 | 100 | 本批次上传数据条数（一个批次最大支持10万条，支持分多次上传，本批次上传完成后 is_completed写true，则系统开始处理本批次数据） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | string | 是 |  | 批次号 |

### 请求示例

```json
{
  "shop_id": "",
  "run_type": 0,
  "task_type": "1",
  "data_count": "100"
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

## 获取批次状态信息

`/open/webapi/pfopen/dataaccess/getdataaccessjob`

| 项 | 内容 |
|---|---|
| 接口名称 | 获取批次状态信息 |
| 接口路径 | `/open/webapi/pfopen/dataaccess/getdataaccessjob` |
| docType / docId | 36 / 1380 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1380 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/dataaccess/getdataaccessjob` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/dataaccess/getdataaccessjob` |


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
| task_id | string | 是 | 2000000000010825912 | 任务处理批次号 |
| task_type | integer | 是 | 2 | 任务类型：1 多成本，2 订单自定义成本，3 分销成本，4 款式编码成本 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | object | 是 |  |  |
| data.task_id | string | 是 |  | 任务处理批次号 |
| data.name | string | 是 |  | 任务名 |
| data.co_id | integer | 是 |  | 商家ID |
| data.upload_start_time | string | 是 |  | 开始上传时间 |
| data.upload_end_time | string | 是 |  | 结束上传时间 |
| data.status | string | 是 |  | 执行状态：待上传,待执行,执行中,失败,成功,部分成功,作废 |
| data.err_msg | string | 是 |  | 错误信息 |
| data.task_detail_list | array | 是 |  | 任务明细列表 |
| data.task_detail_list[] | object | 否 |  |  |
| data.task_detail_list[].task_detail_id | string | 是 |  | 批次子任务id |
| data.task_detail_list[].co_id | string | 是 |  | 商家ID |
| data.task_detail_list[].status | string | 是 |  | 执行状态：待上传,待执行,执行中,失败,成功,部分成功,作废 |
| data.task_detail_list[].err_msg | string | 是 |  | 错误信息 |

### 请求示例

```json
{
  "task_id": "2000000000010825912",
  "task_type": 2
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "err_msg": "",
    "name": "",
    "co_id": 0,
    "task_id": "",
    "upload_start_time": "",
    "task_detail_list": [
      {
        "task_detail_id": "",
        "err_msg": "",
        "co_id": "",
        "status": ""
      }
    ],
    "upload_end_time": "",
    "status": ""
  }
}
```


### 异常示例

_无_


---

## 批次取消

`/open/webapi/pfopen/dataaccess/canceljob`

| 项 | 内容 |
|---|---|
| 接口名称 | 批次取消 |
| 接口路径 | `/open/webapi/pfopen/dataaccess/canceljob` |
| docType / docId | 36 / 1381 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1381 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/dataaccess/canceljob` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/dataaccess/canceljob` |


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
| task_id | string | 是 | 2000000000010825936 | 任务批次号 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | boolean | 是 |  | true 成功 false 失败 |

### 请求示例

```json
{
  "task_id": "2000000000010825936"
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

## 获取批次异常数据

`/open/webapi/pfopen/dataaccess/geterrorrecords`

| 项 | 内容 |
|---|---|
| 接口名称 | 获取批次异常数据 |
| 接口路径 | `/open/webapi/pfopen/dataaccess/geterrorrecords` |
| docType / docId | 36 / 1382 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1382 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/dataaccess/geterrorrecords` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/dataaccess/geterrorrecords` |


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
| task_id | string | 是 | 2000000000010825940 | 批次id |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | object | 是 |  |  |
| data.task_id | string | 是 |  | 批次id |
| data.status | string | 是 |  | 执行状态：待上传,待执行,执行中,失败,成功,部分成功,作废 |
| data.err_msg | string | 是 |  | 错误信息 |
| data.error_url | string | 是 |  | 错误明细下载url(excel格式) |

### 请求示例

```json
{
  "task_id": "2000000000010825940"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "error_url": "",
    "err_msg": "",
    "task_id": "",
    "status": ""
  }
}
```


### 异常示例

_无_


---

## 上传订单费用

`/open/webapi/pfopen/dataaccess/uploadorderfeedata`

| 项 | 内容 |
|---|---|
| 接口名称 | 上传订单费用 |
| 接口路径 | `/open/webapi/pfopen/dataaccess/uploadorderfeedata` |
| docType / docId | 36 / 1493 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1493 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/dataaccess/uploadorderfeedata` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/dataaccess/uploadorderfeedata` |


### 接口说明

调用流程
 step1：调用 &#x27;获取上传批次号&#x27; 接口获取批次号(/open/webapi/pfopen/dataaccess/createuploadbatchnum)。
 step2：联同上步返回的批次号，调用本接口上传多成本，分页传，每页最多500条数据，当本批次上传任务结束时 is_completed赋true，表示本批次上传结束。
 step3：上传完成之后，可通过 &#x27;获取批次状态信息&#x27; 接口查看批次执行状态(/open/webapi/pfopen/dataaccess/getdataaccessjob)；
 如果批次执行状态显示成功后，等待半小时，可到 报表 >订单利润>维护订单费用 页面查看上传的数据。
 如果显示失败， 可通过 ‘获取批次异常数据’接口查看并下载异常数据（/open/webapi/pfopen/dataaccess/geterrorrecords） 。本批次数据不入库，可调整后重新上传。
 另外，如果批次上传过程中如需取消整个批次，可通过‘批次取消’接口传入需要取消的批次号即可（/open/webapi/pfopen/dataaccess/canceljob） ； 上传完成后就不允许再取消。如需取消，需到胜算页面上手动去删除。

 数据更新逻辑
 本接口是追加逻辑，相同单号多次上传则数值会累加；所以上传之前请确认后再上传。如果之前上传的数值有问题， 需到胜算页面上手动去删除，然后在重新上传。

 业务校验
 上传的数据会进行校验，如需了解上传数据的要求可至 报表>订单利润>导入费用 页面中的导入模板中查看。

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
| task_id | string | 是 | 2000000000011033743 | 批次号 |
| is_completed | boolean | 是 | @boolean | 结束上传标识 |
| sku_amount_type | string | 是 | 0 | 商品间金额统计方式 ：按商品金额分摊： 0，按商品行记录计费 ：1；默认填0 |
| account | string | 否 | 10000001 | 资金账户 |
| remark | string | 否 | 1 | 备注 |
| upload_datas | array | 是 |  | 上传数据列表 |
| upload_datas[] | object | 否 |  |  |
| upload_datas[].biz_id | string | 否 |  | 业务键 |
| upload_datas[].upload_data | object | 是 |  | 上传的数据对象(允许上传的数据字段参考【获取允许上传的数据字段】接口返回) |
| upload_datas[].upload_data.o_id | string | 否 | 12222212124 | 内部订单号 |
| upload_datas[].upload_data.so_id | string | 否 | SO1001 | 线上订单号 |
| upload_datas[].upload_data.i_id | string | 否 | 12222212124 | 快递单号 |
| upload_datas[].upload_data.sku_id | string | 否 | a01 | 商品编码 |
| upload_datas[].upload_data.csg_id | string | 是 | 6003 | 利润表项目编码 |
| upload_datas[].upload_data.date | string | 否 | 2025-11-09 | 费用日期 |
| upload_datas[].upload_data.amount | number | 是 | 2.2 | 金额 |
| upload_datas[].upload_data.remark | string | 否 | 订单费 | 备注 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| act | string | 是 |  |  |
| data | object | 是 |  |  |
| data.task_id | string | 是 |  | 任务id，即批次号 |
| data.task_detail_id | string | 是 |  | 当前上传明细id |

### 请求示例

```json
{
  "upload_datas": [
    {
      "upload_data": {
        "date": "2025-11-09",
        "i_id": "12222212124",
        "amount": 2.2,
        "so_id": "SO1001",
        "csg_id": "6003",
        "o_id": "12222212124",
        "sku_id": "12222212124",
        "remark": "订单费"
      },
      "biz_id": ""
    }
  ],
  "task_id": "2000000000011033743",
  "sku_amount_type": "0",
  "remark": "1",
  "is_completed": "@boolean",
  "account": "10000001"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "act": "",
  "data": {
    "task_detail_id": "",
    "task_id": ""
  }
}
```


### 异常示例

_无_


---

## 获取利润表项目列表

`/open/webapi/pfopen/pfopenalifee/getcostsubgrouplist`

| 项 | 内容 |
|---|---|
| 接口名称 | 获取利润表项目列表 |
| 接口路径 | `/open/webapi/pfopen/pfopenalifee/getcostsubgrouplist` |
| docType / docId | 36 / 1576 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1576 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/pfopenalifee/getcostsubgrouplist` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/pfopenalifee/getcostsubgrouplist` |


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
| code | number | 否 |  | 0表示正常 |
| data | object | 否 |  | 费用明细数据集合 |
| data.trance_id | string | 否 |  | 链路id |
| data.has_next | boolean | 否 |  | 是否有下一页 |
| data.datas | array | 否 |  |  |
| data.datas[] | object | 否 |  |  |
| data.datas[].csg_id | string | 否 |  | 利润表项目ID |
| data.datas[].actual_shop | string | 否 |  | 利润表项目名称 |
| data.datas[].csg_code | string | 否 |  | 利润表项目编码 |

### 请求示例

```json
null
```


### 响应示例

```json
{
  "code": 0,
  "data": {
    "trance_id": "",
    "datas": [
      {
        "actual_shop": "",
        "csg_id": "",
        "csg_code": ""
      }
    ],
    "has_next": true
  }
}
```


### 异常示例

_无_


---

## 【胜算收费接口】获取平台汇总账单列表

`/open/webapi/pfopen/pfopenalifee/getalipayfeelist`

| 项 | 内容 |
|---|---|
| 接口名称 | 【胜算收费接口】获取平台汇总账单列表 |
| 接口路径 | `/open/webapi/pfopen/pfopenalifee/getalipayfeelist` |
| docType / docId | 36 / 1577 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1577 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/pfopenalifee/getalipayfeelist` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/pfopenalifee/getalipayfeelist` |


### 接口说明

此接口是根据费用发生时间请求账单数据，可以参考“平台费用”菜单，如果之前发生的费用有变化，需要重新请求获取最新数据。

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
| start_time | string | 是 | 2025/5/27 | 开始时间 |
| end_time | string | 是 | 2025/5/28 | 结束时间 |
| original_shops | array | 是 |  | 原始店铺（可选） |
| original_shops[] | string | 否 |  |  |
| actual_shops | array | 否 |  | 店铺id列表，示例：[10156284,10040204] |
| actual_shops[] | string | 否 |  | 店铺id |
| page_size | number | 否 | 50 | 页大小，默认50 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 0表示正常 |
| data | object | 否 |  | 费用明细数据集合 |
| data.trance_id | string | 否 |  | 链路id |
| data.has_next | boolean | 否 |  | 是否有下一页 |
| data.data | array | 否 |  |  |
| data.data[] | object | 否 |  |  |
| data.data[].original_shop | string | 否 |  | 原始店铺 |
| data.data[].actual_shop | string | 否 |  | 实际店铺 |
| data.data[].fee_date | string | 否 |  | 费用日期 |
| data.data[].fee_id | string | 否 |  | 账单项目编码 |
| data.data[].fee_name | string | 否 |  | 账单项目名称 |
| data.data[].income_amount | number | 否 |  | 收入金额 |
| data.data[].expense_amount | string | 否 |  | 支出金额 |
| data.data[].subtotal | string | 否 |  | 小计 = 收入 - 支出 |
| data.data[].csg_name | string | 否 |  | 对应利润表项目名称 |

### 请求示例

```json
{
  "start_time": "2025/5/27",
  "end_time": "2025/5/28",
  "original_shops": [],
  "actual_shops": [],
  "page_size": 50
}
```


### 响应示例

```json
{
  "code": 0,
  "data": {
    "trance_id": "",
    "data": [
      {
        "fee_name": "",
        "csg_name": "",
        "original_shop": "",
        "expense_amount": "",
        "actual_shop": "",
        "subtotal": "",
        "fee_date": "",
        "fee_id": "",
        "income_amount": 0
      }
    ],
    "has_next": true
  }
}
```


### 异常示例

_无_


---

## 【聚核账收费接口】聚核账出入库流水明细

`/open/webapi/pfopen/inoutchecking/getinoutresultdetailopen`

| 项 | 内容 |
|---|---|
| 接口名称 | 【聚核账收费接口】聚核账出入库流水明细 |
| 接口路径 | `/open/webapi/pfopen/inoutchecking/getinoutresultdetailopen` |
| docType / docId | 36 / 1583 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1583 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/inoutchecking/getinoutresultdetailopen` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/inoutchecking/getinoutresultdetailopen` |


### 接口说明

本接口不含淘系数据：淘宝天猫，天猫供销，考拉pop，考拉供应商直发，阿里巴巴，淘工厂，天猫超市，天猫国际直营，阿里健康直营，淘宝定制，淘宝采购，淘宝买菜，银泰喵街。如有相关平台需走奇门接口：https://open.jushuitan.com/document.aspx?doc_id=2372

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
| page_size | integer | 是 | 20 | 页大小（1-500） |
| id | integer | 是 | 1 | id必传。第一次查询时，如果不知道最小id是多少，可传0，获取第一批数据。后续查询，id=前一批数据最后一条数据的id+1，通过该新id查询接口，获取到新一批数据 |
| time_type | integer | 是 | 0 | 时间类型。单据时间 0； 更新时间 1; 金额核销时间：2； 金额核销系统时间：bc_operate_date 3; 数量核销时间：4； 数量核销系统时间：qty_check_operate_date 5；记账时间：amountcheck_accounting_date 6 ;妥投记账时间 7 |
| begin_date | string | 是 | 2026-06-01 | 开始时间 数据 >= 平台端给的部分账单数据时分秒后面带微秒（2026-05-04 23:59:59.879），所以传入时分秒包含不到这条数据，可以传入第二天零点获取 如果出现极端边界情况，恰好有数据是整点 可以根据id去重 |
| end_date | string | 是 | 2026-07-01 | 结束时间 数据 <= 平台端给的部分账单数据时分秒后面带微秒（2026-05-04 23:59:59.879），所以传入时分秒包含不到这条数据，可以传入第二天零点获取 如果出现极端边界情况，恰好有数据是整点 可以根据id去重 |
| shop_id | string | 否 | 111,222 | 店铺。如果想按分销商查询数据，可将分销商商家编码*（-1）作为店铺入参。多个值逗号分隔 |
| code | string | 否 | 111,222 | 单号。多个值逗号分隔 |
| code_type | string | 否 | item_so_id | 单号类型。时间戳：id（page_index始终传1）; 原始线上单号：item_so_id ;出入库单号：io_id; 出入库子单号：ioi_id ;售后单号：as_id |
| bill_type | string | 否 | 实际出入库,虚拟 | 单据来源：（可传多个） 实际出入库、虚拟、核销、销售出仓、调整数量、调整发出余额、销售退货、无出入库单出库、无出入库单退货、无出入库单换货、手动调整-调整数量、手动调整-调整发出余额、手动调整-核销、销售退款、换货。 |
| bill_detail_type | string | 否 | 销售出仓,销售退货 | 单据类型：销售出仓、销售退货、销售退款、换货、无出入库单出库、无出入库单退货、无出入库单换货、无信息件、自动调整、手动调整、收款（仅到账版有）、妥投（仅妥投版有）。多个值逗号分隔 |
| bill_flag | string | 否 | 0,1 | 单据属性： 正常单据：0 ； 历史单据：1 ； 正常单据结账后变更单据：2 ； 历史单据结账后变更单据：3 ； 全部：null。多个值逗号分隔 |
| situation | string | 否 |  | 特殊标签 |
| check_way | string | 否 | 0,1 | 金额核销方式，自动核销（有账单）：AutoCheck：0；手工核销（有账单）：UserCheck：1；手工调整（无账单）：UserAdjustment：2，未核销Null：3;无明细核销（有账单）：4；强制核销：5）收入调整-有货款核销：6，收入调整-无货款有应收核销：7，收入调整-无货款无明细核销：8；自动调整9；多个值逗号分隔 |
| qty_check_way | string | 否 | 0,1 | 数量核销方式：自动核销：0；手动核销：1；未核销：2。多个值逗号分隔 |
| sentgoods_check_way | string | 否 | 0,1 | 发出商品核销方式：自动核销：0；手动核销：1；未核销：2。多个值逗号分隔 |
| is_settle | integer | 否 | 1 | 结账状态：未结账：0；已结账：1；全部：null |
| del_flag | string | 否 | 0,1 | 删除标识：未删除：0；已删除：1；不传默认为0。多个值逗号分隔 |
| is_check_washfinished | boolean | 否 | False | 是否查询洗数完成：true：是；false：否；不传默认为false（传 true时：先校验洗数状态，如果当天洗数未完成，直接抛异常 "当天洗数未完成！"，不返回数据； 传 false或不传：跳过校验，直接查询返回数据，不管洗数有没有完成） |
| onlyrefund_approve_result | string | 否 | 仅退款 | 仅退款调整结果：用户在仅退款追踪表调整反写的标签；涉及：仅退款、待退货、快递赔付、用户自定义标签等； |
| onlyrefund_approve_date | string | 否 | 2026-05-04 12:30:00.123 | 仅退款调整时间：用户在仅退款追踪表调整时反写的时间 |
| combine_sku_id | string | 否 | SKU001 | 组合装商品编码 |
| delivered_status | integer | 否 | 1 | 妥投状态(仅妥投版有该字段)：未妥投0，已妥投1,全部null |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 | 0 | 0表示正常 |
| data | object | 否 |  | 费用明细数据集合 |
| data.data | array | 否 |  | 明细数据列表 |
| data.data[] | object | 否 |  |  |
| data.data[].id | integer | 否 | 10001 | 编号ID，数据唯一键 |
| data.data[].bc_no | string | 否 | BC20260708001 | 业务主键（如果已结账，后续生成结账后变更，bc_no可能重复） |
| data.data[].actual_id | integer | 否 | 50023 | 单据号 |
| data.data[].actual_detail_id | integer | 否 | 1200045 | 子单据号 |
| data.data[].current_bill_period | string | 否 | 202607 | 会计区间 |
| data.data[].dw_fc_bill_date | string | 否 | 2026-07-08 10:20:30.123 | 单据时间 |
| data.data[].dw_created | string | 否 | 2026-07-08 10:20:30.123 | 创建时间 |
| data.data[].cdc_ts | string | 否 | 2026-07-08 10:25:10.456 | 更新时间 |
| data.data[].bill_type | string | 否 | 销售出仓 | 单据来源:实际出入库，虚拟，核销，调整数量，调整发出余额 |
| data.data[].bill_detail_type | string | 否 | 销售出仓 | 单据类型：销售出仓、销售退货、销售退款、换货、无出入库单出库、无出入库单退货、无出入库单换货、无信息件、自动调整、手动调整、收款（仅到账版有） |
| data.data[].bill_flag_nm | string | 否 | 0 | 单据属性： 正常单据：0； 历史单据：1；正常单据结账后变更单据：2 ； 历史单据结账后变更单据：3 ； 全部：null |
| data.data[].situation | string | 否 |  | 特殊标签 |
| data.data[].is_settle_nm | string | 否 | 未结账 | 结账状态： 已结账；未结账 |
| data.data[].io_date | string | 否 | 2026-07-08 09:10:00.000 | 出入库时间 |
| data.data[].io_type | string | 否 | 出库 | 出入库方向 |
| data.data[].io_id | integer | 否 | 80012 | 出入库内部单号 |
| data.data[].ioi_id | integer | 否 | 150034 | 出入库内部子单号 |
| data.data[].red_blue_flag | integer | 否 | 1 | 红蓝字（1是蓝字，-1是红字） |
| data.data[].shop_id | integer | 否 | 111 | 店铺编码 |
| data.data[].shop_name | string | 否 | 官方旗舰店 | 店铺名称 |
| data.data[].wms_co_id | integer | 否 | 201 | 分仓编码 |
| data.data[].wms_co_name | string | 否 | 华东分仓 | 分仓名称 |
| data.data[].wh_id | integer | 否 | 5 | 仓库编码 |
| data.data[].wh_name | string | 否 | 上海总仓 | 仓库名称 |
| data.data[].drp_co_id_to | integer | 否 | 3002 | 供销商编码 |
| data.data[].drp_co_id_to_name | string | 否 | XX供应链 | 供销商名称 |
| data.data[].drp_co_id_from | integer | 否 | 4001 | 分销商编码 |
| data.data[].drp_co_id_from_name | string | 否 | 线下分销A店 | 分销商名称 |
| data.data[].inout_labels | string | 否 | 直播单,预售 | 出入库标签 |
| data.data[].inout_stock_enabled | string | 否 | on | 是否扣库存。 对应ERP销售出库单的使用库存。 on是使用库存，off不使用库存。 |
| data.data[].sent_qty | integer | 否 | 2 | 出入库数量(实发) |
| data.data[].sku_id | string | 否 | SKU001001 | 商品编码 |
| data.data[].sku_name | string | 否 | 夏季纯棉T恤 | 商品名称 |
| data.data[].i_id | string | 否 | SP202605 | 商品款号 |
| data.data[].brand | string | 否 | 自有品牌 | 商品品牌 |
| data.data[].category | string | 否 | 服饰上衣 | 商品大类 |
| data.data[].properties_value | string | 否 | M,白色 | 商品属性 |
| data.data[].vc_name | string | 否 | 日常穿搭 | 虚拟分类 |
| data.data[].color | string | 否 | 白色 | 颜色规格 |
| data.data[].is_gift_str | string | 否 | 否 | 是否赠品:是;否 |
| data.data[].o_id | integer | 否 | 90056 | 内部单号 |
| data.data[].oi_id | integer | 否 | 200145 | 内部子单号（订单明细行） |
| data.data[].so_id | string | 否 | SO202607080001 | 线上单号 |
| data.data[].item_so_id | string | 否 | 1234567890123 | 原始线上单号 |
| data.data[].outer_oi_id | string | 否 | 6543210987654 | 原始线上子单号 |
| data.data[].bc_amount | string | 否 | 199.00 | 实收/实退金额 |
| data.data[].freight | string | 否 | 10.00 | 其中运费收入 |
| data.data[].free_amount | string | 否 | 20.00 | 商家优惠 |
| data.data[].amount | string | 否 | 179.00 | 商品金额 |
| data.data[].send_date | string | 否 | 2026-07-08 14:30:00.000 | 发货时间 |
| data.data[].order_labels | string | 否 | 极速发货,会员单 | 订单标签 |
| data.data[].order_type | string | 否 | 正常销售 | 订单类型 |
| data.data[].cost_price | string | 否 | 60.00 | 成本单价 |
| data.data[].cost_amount | string | 否 | 120.00 | 成本金额 |
| data.data[].order_qty | integer | 否 | 2 | 订单/售后商品数量 |
| data.data[].l_id | string | 否 | SF1234567890 | 快递单号 |
| data.data[].lc_id | string | 否 | SF | 快递公司编码 |
| data.data[].order_creator | integer | 否 | 10086 | 业务员编号 |
| data.data[].creator_name | string | 否 | 张三 | 业务员 |
| data.data[].currency | string | 否 | CNY | 币种 |
| data.data[].currency_to_rmb | string | 否 | 1.0000 | 兑人民币汇率(原币) |
| data.data[].oid_count | integer | 否 | 1 | 订单明细总数 |
| data.data[].as_id | integer | 否 | 0 | 售后单号 |
| data.data[].asi_id | integer | 否 | 0 | 售后单子单号 |
| data.data[].aftersale_type | string | 否 |  | 售后类型 |
| data.data[].aftersale_confirm_date | string | 否 |  | 售后确认时间 |
| data.data[].aftersale_labels | string | 否 |  | 售后标签 |
| data.data[].aftersale_question_type | string | 否 |  | 售后问题类型 |
| data.data[].dw_fc_goods_qty | string | 否 | 2 | 商品数量 |
| data.data[].dw_fc_sales_income | integer | 否 | 179 | 销售收入 |
| data.data[].income_ajustment_amount | string | 否 | 0.00 | 收入调整项 |
| data.data[].dw_fc_sales_cost | string | 否 | 120.00 | 销售成本 |
| data.data[].dw_fc_paid_amount | string | 否 | 179.00 | 应收账款 |
| data.data[].dw_fc_amount_loss | string | 否 | 0.00 | 资产减值损失 |
| data.data[].dw_fc_sent_goods_amount | string | 否 | 120.00 | 发出商品 |
| data.data[].dw_fc_stock_goods_amount | string | 否 | 0.00 | 库存商品 |
| data.data[].dw_fc_sent_goods_qty | integer | 否 | 2 | 发出商品数量 |
| data.data[].dw_fc_stock_goods_qty | integer | 否 | 0 | 库存商品数量 |
| data.data[].dw_fc_nodeal_amount | string | 否 | 0.00 | 未处理 |
| data.data[].dw_check_goods_qty | integer | 否 | 2 | 核销用商品数量 |
| data.data[].dw_check_stock_goods_qty | integer | 否 | 0 | 核销用库存商品数量 |
| data.data[].dw_check_paid_amount | string | 否 | 179.00 | 核销用应收账款 |
| data.data[].bc_result_amount | string | 否 | 179.00 | 到账金额=平台补贴到账+买家实付到账 注意：当存在手工核销时，单据的账单金额=到账金额+调整金额 |
| data.data[].platform_subsidy | string | 否 | 10.00 | 平台补贴到账 |
| data.data[].buyer_pay_amount | string | 否 | 169.00 | 买家实付到账 |
| data.data[].bc_date | string | 否 | 2026-07-09 08:30:00.000 | 到账时间 |
| data.data[].bc_operate_date | string | 否 | 2026-07-09 08:30:00.000 | 核销系统时间 |
| data.data[].check_no | string | 否 | CHECK20260709001 | 核销单号 |
| data.data[].check_way | string | 否 | 自动核销（有账单） | 核销方式： 自动核销（有账单）； 手工核销（有账单）； 手工调整（无账单）； |
| data.data[].check_user | string | 否 | system | 操作用户（手动核销、手动调整等的操作账号） |
| data.data[].check_amount_split_type | string | 否 | Auto | 用户选择的金额分摊方式（系统分摊：Auto手工输入User |
| data.data[].bc_adjustment_amount | string | 否 | 0.00 | 调整金额（客户手工核销时产生的调整差额）=平台补贴调整+买家实付调整 |
| data.data[].adjustment_platform_subsidy | string | 否 | 0.00 | 平台补贴调整 |
| data.data[].adjustment_buyer_pay_amount | string | 否 | 0.00 | 买家实付调整 |
| data.data[].bc_remark | string | 否 | 正常自动核销 | 核销备注（用户输入的备注） |
| data.data[].qty_check_operate_date | string | 否 | 2026-07-08 15:00:00.000 | 数量核销系统时间 |
| data.data[].qty_check_date | string | 否 | 2026-07-08 15:00:00.000 | 数量核销时间 |
| data.data[].qty_check_way | string | 否 | 自动核销 | 数量核销方式： 自动核销; 手动核销; 未核销 |
| data.data[].qty_check_no | string | 否 | QTYCHECK20260708001 | 数量核销单号 |
| data.data[].sentgoods_check_operate_date | string | 否 | 2026-07-08 15:00:00.000 | 发出商品核销系统时间 |
| data.data[].sentgoods_check_date | string | 否 | 2026-07-08 15:00:00.000 | 发出商品核销时间 |
| data.data[].sentgoods_check_way | string | 否 | 自动核销 | 发出商品核销方式：自动核销; 手动核销; 未核销 |
| data.data[].sentgoods_check_no | string | 否 | SENTCHECK20260708001 | 发出商品核销单号 |
| data.data[].traceid | string | 否 | trace-123456789abcdef | 调用链 |
| data.data[].message | string | 否 |  | 异常信息 |
| data.data[].cursor | string | 否 | 10001 | 游标 |
| data.data[].is_success | boolean | 否 | True | 是否成功 |
| data.data[].onlyrefund_approve_result | string | 否 |  | 仅退款调整结果：用户在仅退款追踪表调整反写的标签；涉及：仅退款、待退货、快递赔付、用户自定义标签等； |
| data.data[].onlyrefund_approve_date | string | 否 |  | 仅退款调整时间：用户在仅退款追踪表调整时反写的时间 |
| data.data[].combine_sku_id | string | 否 |  | 组合装商品编码 |
| data.data[].shop_buyer_id_en | string | 否 | buyer_001 | 买家账号 |
| data.data[].amountcheck_accounting_date | string | 否 | 2026-07-09 09:00:00.000 | 金额核销记账时间 |
| data.data[].batchs | array | 否 |  | 批次对象 |
| data.data[].batchs[] | object | 否 |  |  |
| data.data[].batchs[].batch_no | string | 否 | B20260708 | 批次号 |
| data.data[].batchs[].sku_id | string | 否 | SKU001001 | 商品编码 |
| data.data[].batchs[].qty | integer | 否 | 2 | 本批次数量 |
| data.data[].batchs[].product_date | string | 否 | 2026-07-01 | 批次生产日期 |
| data.data[].batchs[].supplier_id | integer | 否 | 10086 | 供应商编号 |
| data.data[].batchs[].expiration_date | string | 否 | 2028-07-01 | 批次有效期至 |
| data.data[].batchs[].supplier_name | string | 否 | XX食品厂 | 供应商名称 |
| data.data[].sns | array | 否 |  | 唯一码集合(仅当商家erp基础设置开启了商品唯一码才可获取) |
| data.data[].sns[] | object | 否 |  |  |
| data.data[].sns[].sn | string | 否 | SN2026070800001 | 唯一码 |
| data.data[].order_remark | string | 否 | 请尽快发货 | 卖家备注 |
| data.data[].bu_id | string | 否 | VIRT001 | 虚拟仓ID |
| data.data[].out_ioi_id | integer | 否 | 150034 | 销售出仓出入库子单号 |
| data.data[].delivered_status | string | 否 | 已妥投 | 枚举值：未妥投，已妥投 |
| data.data[].delivered_accounting_time | string | 否 | 2026-07-09 10:00:00.000 | 妥投记账时间(仅妥投版有该字段)：妥投时间和生成妥投原单单据时间的较大值。 |
| data.data[].delivered_time | string | 否 | 2026-07-09 09:30:00.000 | 妥投时间(仅妥投版有该字段) |
| data.data[].customize_labels | string | 否 | 活动款,主推 | 自定义标签 |
| data.data[].receiver_state | string | 否 | 江苏省 | 省 |
| data.data[].receiver_city | string | 否 | 苏州市 | 市 |
| data.data[].receiver_district | string | 否 | 工业园区 | 区 |
| data.data[].referrer_id | string | 否 | Daren001 | 达人id |
| data.data[].referrer_name | string | 否 | 带货达人A | 达人名称 |

### 请求示例

```json
{
  "end_date": "2026-07-01",
  "bill_flag": "",
  "del_flag": "",
  "time_type": 0,
  "code": "",
  "begin_date": "2026-06-01",
  "onlyrefund_approve_result": "",
  "is_settle": 0,
  "sentgoods_check_way": "",
  "onlyrefund_approve_date": "",
  "shop_id": "",
  "is_check_washfinished": true,
  "delivered_status": 0,
  "combine_sku_id": "",
  "bill_detail_type": "",
  "bill_type": "",
  "qty_check_way": "",
  "id": 1,
  "situation": "",
  "page_size": 20,
  "code_type": "",
  "check_way": ""
}
```


### 响应示例

```json
{
  "code": 0,
  "data": {
    "data": [
      {
        "qty_check_no": "",
        "shop_buyer_id_en": "",
        "dw_check_stock_goods_qty": 0,
        "order_labels": "",
        "aftersale_confirm_date": "",
        "platform_subsidy": "",
        "dw_fc_amount_loss": "",
        "item_so_id": "",
        "bill_type": "",
        "sku_name": "",
        "id": 0,
        "current_bill_period": "",
        "bu_id": "",
        "brand": "",
        "order_remark": "",
        "aftersale_labels": "",
        "cdc_ts": "",
        "check_amount_split_type": "",
        "adjustment_platform_subsidy": "",
        "amountcheck_accounting_date": "",
        "sku_id": "",
        "io_id": 0,
        "shop_id": 0,
        "properties_value": "",
        "cost_amount": "",
        "drp_co_id_to": 0,
        "bc_adjustment_amount": "",
        "red_blue_flag": 0,
        "dw_fc_nodeal_amount": "",
        "bc_remark": "",
        "drp_co_id_to_name": "",
        "traceid": "",
        "dw_check_goods_qty": 0,
        "dw_fc_sales_cost": "",
        "freight": "",
        "onlyrefund_approve_result": "",
        "dw_fc_sent_goods_amount": "",
        "dw_fc_paid_amount": "",
        "income_ajustment_amount": "",
        "onlyrefund_approve_date": "",
        "receiver_state": "",
        "dw_check_paid_amount": "",
        "so_id": "",
        "bill_detail_type": "",
        "currency": "",
        "dw_fc_bill_date": "",
        "situation": "",
        "wms_co_name": "",
        "outer_oi_id": "",
        "free_amount": "",
        "cost_price": "",
        "dw_created": "",
        "io_date": "",
        "bc_amount": "",
        "receiver_district": "",
        "sentgoods_check_way": "",
        "aftersale_type": "",
        "sns": [
          {
            "sn": ""
          }
        ],
        "dw_fc_goods_qty": "",
        "inout_labels": "",
        "i_id": "",
        "qty_check_date": "",
        "dw_fc_stock_goods_amount": "",
        "referrer_id": "",
        "sentgoods_check_operate_date": "",
        "dw_fc_sales_income": 0,
        "is_settle_nm": "",
        "drp_co_id_from": 0,
        "bc_date": "",
        "customize_labels": "",
        "bc_operate_date": "",
        "send_date": "",
        "combine_sku_id": "",
        "qty_check_way": "",
        "order_type": "",
        "buyer_pay_amount": "",
        "vc_name": "",
        "adjustment_buyer_pay_amount": "",
        "inout_stock_enabled": "",
        "actual_detail_id": 0,
        "order_creator": 0,
        "shop_name": "",
        "qty_check_operate_date": "",
        "ioi_id": 0,
        "batchs": [
          {
            "batch_no": "",
            "qty": 0,
            "sku_id": "",
            "expiration_date": "",
            "supplier_name": "",
            "supplier_id": 0,
            "product_date": ""
          }
        ],
        "wms_co_id": 0,
        "currency_to_rmb": "",
        "sentgoods_check_no": "",
        "delivered_time": "",
        "dw_fc_stock_goods_qty": 0,
        "referrer_name": "",
        "check_user": "",
        "dw_fc_sent_goods_qty": 0,
        "cursor": "",
        "is_gift_str": "",
        "lc_id": "",
        "check_no": "",
        "color": "",
        "as_id": 0,
        "receiver_city": "",
        "delivered_accounting_time": "",
        "is_success": true,
        "sent_qty": 0,
        "wh_name": "",
        "delivered_status": "",
        "aftersale_question_type": "",
        "o_id": 0,
        "sentgoods_check_date": "",
        "oid_count": 0,
        "amount": "",
        "asi_id": 0,
        "actual_id": 0,
        "drp_co_id_from_name": "",
        "order_qty": 0,
        "bc_no": "",
        "message": "",
        "oi_id": 0,
        "bc_result_amount": "",
        "wh_id": 0,
        "out_ioi_id": 0,
        "io_type": "",
        "creator_name": "",
        "bill_flag_nm": "",
        "category": "",
        "l_id": "",
        "check_way": ""
      }
    ]
  }
}
```


### 异常示例

_无_


---

## 【胜算/聚核账 收费接口】平台账单

`/open/webapi/pfopen/pfopenalifee/getopenalipaylist`

| 项 | 内容 |
|---|---|
| 接口名称 | 【胜算/聚核账 收费接口】平台账单 |
| 接口路径 | `/open/webapi/pfopen/pfopenalifee/getopenalipaylist` |
| docType / docId | 36 / 1584 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1584 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/pfopenalifee/getopenalipaylist` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/pfopenalifee/getopenalipaylist` |


### 接口说明

本接口不含淘系数据：淘宝天猫，天猫供销，考拉pop，考拉供应商直发，阿里巴巴，淘工厂，天猫超市，天猫国际直营，阿里健康直营，淘宝定制，淘宝采购，淘宝买菜，银泰喵街。如有相关平台需走奇门接口：https://open.jushuitan.com/document.aspx?doc_id=2373

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
| time_type | string | 是 | fee_time | fee_time： 费用发生时间； modified：更新时间； |
| start_time | string | 是 | 2026-06-01 | 起始时间，闭区间 |
| end_time | string | 是 | 2026-07-01 | 结束时间，开区间；查询时间最大范围1个月 |
| cursor | integer | 是 | 1 | 游标（ long类型，第一页从0开始，接口会返回是否有下一页（has_next），第二页开始传上一次返回的游标值） |
| shop_ids | string | 否 | 111,222 | 店铺编号，多店铺逗号分隔 |
| page_size | integer | 是 | 20 | 每页多少条（默认50条，最大500条） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 0表示正常 |
| data | array | 否 |  | 费用明细数组 |
| data[] | object | 否 |  |  |
| data[].shop_id | integer | 否 | 111 | 店铺编码 |
| data[].so_id | string | 否 | SO202607080001 | 线上单号 |
| data[].auto_id | string | 否 |  | 记录流水号 |
| data[].amount | number | 否 | 99.5 | 金额 |
| data[].fee_time | string | 否 | 2026-07-08 14:30:00.000 | 费用发生时间 |
| data[].fee_id | integer | 否 | 201 | 费用项目编码 |
| data[].fee_name | string | 否 | 平台服务费 | 费用项目名称 |
| data[].channel | string | 否 | 抖音 | 数据来源渠道，对应枚举：https://www.erp321.com/app/support/document.html#page=7274 |
| data[].csg_code | string | 否 | CSG001 | 利润表项目编码 |
| data[].csg_name | string | 否 | 平台佣金支出 | 利润表项目名称 |
| data[].opt_user_name | string | 否 | 支付宝商家账号 | 支付宝平台为对方账号;对于抖音、快手等平台为资金渠道名称 |
| data[].oc_amount | string | 否 | 99.50 | 原币金额 |
| data[].currency | string | 否 | CNY | 原币币种的代码，可到ERP的“汇率管理”菜单中查看币种名称 |
| data[].inout_type | string | 否 | -1 | 收支方向:-1则表示支出，1则表示收入 |
| data[].del_flag | integer | 否 | 0 | 是否被删除：0表示有效数据，大于0表示已被删除 |
| data[].alipay_order_no | string | 否 | 202607082200140498141234 | 业务流水号 |
| data[].primary_key | string | 否 | PK100001 | 主键，可通过此字段来更新数据 |
| data[].shop_id_old | integer | 否 | 111 | 原始店铺编码，订单号对应的原始店铺；多数场景下无需使用此字段。 |

### 请求示例

```json
{
  "cursor": 1,
  "start_time": "2026-06-01",
  "time_type": "fee_time",
  "end_time": "2026-07-01",
  "shop_ids": "",
  "page_size": 20
}
```


### 响应示例

```json
{
  "code": 0,
  "data": [
    {
      "shop_id_old": 0,
      "csg_name": "",
      "del_flag": 0,
      "amount": 0,
      "channel": "",
      "oc_amount": "",
      "primary_key": "",
      "fee_name": "",
      "shop_id": 0,
      "auto_id": 0,
      "fee_time": "",
      "so_id": "",
      "inout_type": "",
      "opt_user_name": "",
      "fee_id": 0,
      "csg_code": "",
      "alipay_order_no": "",
      "currency": ""
    }
  ]
}
```


### 异常示例

_无_


---

## 【胜算/聚核账 收费接口】获取平台账单分摊后数据

`/open/webapi/pfopen/pfopenalifee/getalipayitems`

| 项 | 内容 |
|---|---|
| 接口名称 | 【胜算/聚核账 收费接口】获取平台账单分摊后数据 |
| 接口路径 | `/open/webapi/pfopen/pfopenalifee/getalipayitems` |
| docType / docId | 36 / 1596 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=1596 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/pfopenalifee/getalipayitems` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/pfopenalifee/getalipayitems` |


### 接口说明

本接口不含淘系数据：淘宝天猫，天猫供销，考拉pop，考拉供应商直发，阿里巴巴，淘工厂，天猫超市，天猫国际直营，阿里健康直营，淘宝定制，淘宝采购，淘宝买菜，银泰喵街。如有相关平台需走奇门接口：
 https://open.jushuitan.com/document.aspx?doc_id=2367

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
| start_time | string | 是 | 2025/5/27 | 起始时间，闭区间 |
| end_time | string | 是 | 2025/5/28 | 结束时间，开区间；时间范围不超过30天 |
| cursor | number | 是 | @integer | 游标（ long类型，第一页从0开始，接口会返回是否有下一页（has_next），第二页开始传上一次返回的游标值） |
| shop_ids | string | 否 |  | 店铺编号（多个用逗号分隔） |
| split_combine | string | 否 |  | 是否拆分组合装，0-全部；1-拆分组合装数据；2-不拆分组合装数据； |
| page_size | number | 是 | 50 | 每页多少条（默认50条，最大500条） |
| time_type | string | 是 | modified | fee_time：费用发生时间； modified：更新时间； |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 0表示正常 |
| data | object | 否 |  | 费用明细数据集合 |
| data.trance_id | string | 否 |  | 链路id |
| data.message | string | 否 |  | 异常信息 |
| data.cursor | string | 否 |  |  |
| data.page_size | string | 是 |  |  |
| data.has_next | boolean | 否 |  | 是否有下一页 |
| data.datas | array | 否 |  |  |
| data.datas[] | object | 否 |  |  |
| data.datas[].auto_id | string | 是 |  | 明细记录流水号 |
| data.datas[].primary_key | string | 是 |  | 主键，可通过此字段来更新数据 |
| data.datas[].modified | string | 是 |  | 修改时间 |
| data.datas[].inout_type | string | 是 |  | 金额正负向 |
| data.datas[].p_auto_id | string | 是 |  | 主记录流水号 |
| data.datas[].shop_id | string | 是 |  | 店铺编码 |
| data.datas[].so_id | string | 是 |  | 线上单号 |
| data.datas[].amount | string | 是 |  | 费用金额 |
| data.datas[].fee_time | string | 是 |  | 费用发生时间 |
| data.datas[].fee_name | string | 是 |  | 费用项目名称 |
| data.datas[].sku_id | string | 是 |  | 商品编码 |
| data.datas[].combine_type | string | 是 |  | 商品类型，枚举如下：combine：组合装，single：子商品，double：常规商品。 |
| data.datas[].shop_sku_id | string | 是 |  | 店铺商品编码 |
| data.datas[].shop_i_id | string | 是 |  | 店铺款式编码 |
| data.datas[].channel | string | 是 |  | 数据来源渠道，对应枚举：https://www.erp321.com/app/support/document.html#page=7274 |
| data.datas[].oc_amount | string | 是 |  | 原币金额 |
| data.datas[].currency | string | 是 |  | 原币币种的代码，可到ERP的“汇率管理”菜单中查看币种名称 |
| data.datas[].del_flag | string | 是 |  | 是否被删除：0表示有效数据，大于0表示已被删除 |

### 请求示例

```json
{
  "cursor": "@integer",
  "start_time": "2025/5/27",
  "time_type": "modified",
  "end_time": "2025/5/28",
  "split_combine": "",
  "shop_ids": "",
  "page_size": 50
}
```


### 响应示例

```json
{
  "code": 0,
  "data": {
    "cursor": "",
    "trance_id": "",
    "datas": [
      {
        "del_flag": "",
        "amount": "",
        "p_auto_id": "",
        "channel": "",
        "oc_amount": "",
        "sku_id": "",
        "shop_i_id": "",
        "primary_key": "",
        "shop_sku_id": "",
        "fee_name": "",
        "auto_id": "",
        "shop_id": "",
        "fee_time": "",
        "inout_type": "",
        "so_id": "",
        "modified": "",
        "currency": "",
        "combine_type": ""
      }
    ],
    "has_next": true,
    "message": "",
    "page_size": ""
  }
}
```


### 异常示例

_无_


---

## 【胜算收费接口】获取胜算店铺级推广费

`/open/webapi/pfopen/pfopenalifee/getopenalipaypromotionfee`

| 项 | 内容 |
|---|---|
| 接口名称 | 【胜算收费接口】获取胜算店铺级推广费 |
| 接口路径 | `/open/webapi/pfopen/pfopenalifee/getopenalipaypromotionfee` |
| docType / docId | 36 / 972 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=972 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/pfopenalifee/getopenalipaypromotionfee` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/pfopenalifee/getopenalipaypromotionfee` |


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
| time_type | string | 是 | modified | 时间类型：modified：修改时间；fee_time：费用发生时间 |
| start_time | string | 是 | 2024-05-28 | 开始时间，闭区间 |
| end_time | string | 是 | 2024-06-28 | 结束时间，开区间 |
| cursor | number | 是 | 1 | 游标（ long类型，第一页从0开始，接口会返回是否有下一页（has_next），第二页开始传上一次返回的游标值） |
| shop_ids | string | 否 | 10156284,10040204 | 店铺id列表多个都好隔开10156284,10040204 |
| page_size | number | 否 | 10 | 页大小 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 0表示正常 |
| msg | string | 否 |  | 错误提示文案 |
| data | object | 否 |  | 胜算日常记账集合 |
| data.trance_id | string | 否 |  | 链路id |
| data.cursor | number | 否 |  | 游标 |
| data.has_next | boolean | 否 |  | 是否有下一页 |
| data.data | array | 否 |  |  |
| data.data[] | object | 否 |  |  |
| data.data[].auto_id | number | 否 |  | 记录流水号 |
| data.data[].shop_id | number | 否 |  | 店铺编码 |
| data.data[].fee_time | string | 否 |  | 费用发生时间 |
| data.data[].amount | number | 否 |  | 费用金额 |
| data.data[].fee_name | string | 否 |  | 费用名称 |
| data.data[].channel | string | 否 |  | 平台类型，枚举：https://www.erp321.com/app/support/document.html#page=7491 |
| data.data[].csg_code | string | 否 |  | 利润表项目编码 |
| data.data[].csg_name | string | 否 |  | 利润表项目名称 |
| data.data[].oc_amount | string | 否 |  | 原币金额 |
| data.data[].currency | string | 否 |  | 原币币种的代码，可到ERP的“汇率管理”菜单中查看币种名称 |
| data.data[].del_flag | number | 否 |  | 是否被删除：0表示有效数据，大于0表示已被删除 |
| data.data[].primary_key | string | 否 |  | 主键，可根据此字段来更新数据 |
| data.data[].account_code | string | 否 |  | 巨量千川账号ID/账户快手id |
| data.data[].journal_type_name | string | 否 |  | 推广账户ID/广告主账户id |
| data.data[].description | string | 否 |  | 巨量千川账号名称&推广账户名称/描述 |

### 请求示例

```json
{
  "cursor": 1,
  "start_time": "2024-05-28",
  "time_type": "modified",
  "end_time": "2024-06-28",
  "shop_ids": "10156284,10040204",
  "page_size": 10
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "cursor": 0,
    "trance_id": "",
    "data": [
      {
        "fee_name": "",
        "auto_id": 0,
        "shop_id": 0,
        "fee_time": "",
        "csg_name": "",
        "amount": 0,
        "channel": "",
        "csg_code": ""
        "primaryKey": "2011abc"
      }
    ],
    "has_next": true
  }
}
```


### 异常示例

_无_


---

## 【聚核账收费接口】分层获取出入库明细数据

`/open/webapi/pfapi/openinoutchecking/loadinoutresultdetaildataforlevel`

| 项 | 内容 |
|---|---|
| 接口名称 | 【聚核账收费接口】分层获取出入库明细数据 |
| 接口路径 | `/open/webapi/pfapi/openinoutchecking/loadinoutresultdetaildataforlevel` |
| docType / docId | 36 / 532 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=532 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfapi/openinoutchecking/loadinoutresultdetaildataforlevel` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfapi/openinoutchecking/loadinoutresultdetaildataforlevel` |


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
| page_index | integer | 否 |  | 第几页 |
| pageS_size | integer | 否 |  | 页大小 |
| time_type | integer | 是 |  | 时间类型 单据时间 0； 更新时间 1 |
| begin_date | string | 是 |  | 开始时间 |
| end_date | string | 是 |  | 结束时间 |
| shop_id | array | 否 |  | 店铺集合 |
| shop_id[] | string | 否 |  |  |
| code | string | 否 |  | 单号 |
| code_type | string | 否 |  | 单号类型 内部单号：o_id； 原始线上单号：item_so_id； 出入库单号：io_id； 出入库子单号：ioi_id； 售后单号：as_id |
| bill_detail_type | string | 否 |  | 单据类型：销售出仓；销售退货；销售退款；换货；无出入库单出库；无出入库单退货；无出入库单换货；无出入库单采入；无出入库单采退；无信息件；自动调整；手动调整；未处理冲平；未处理结转；收款；妥投；到账视为妥投 |
| bill_flag | integer | 否 |  | 单据状态 正常单据：0； 历史单据：1； 结账后变更单据：2； 无信息件：3； 仅推送：4； 异常单据：5； 全部：null |
| push_period | string | 否 |  | 会计期间 |
| is_settle | integer | 否 |  | 结账状态 未结账：0；已结账：1；结账中：2；反结账中：3；结账失败：4；反结账失败：5 |
| situation | string | 否 |  | 特殊标签 |
| outer_push_status | integer | 否 |  | 推送状态 未推送：0；已推送：2；推送失败：-1 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| page_index | number | 是 |  | 第几页 |
| page_size | number | 是 |  | 页大小 |
| data_count | number | 是 |  | 总条数 |
| page_count | number | 是 |  | 总页数 |
| has_next | boolean | 是 |  | 是否有下一页 |
| issuccess | boolean | 是 |  | 是否成功 |
| msg | null | 是 |  | 错误信息 |
| level_data | array | 是 |  | 数据集合 |
| level_data[] | object | 否 |  |  |
| level_data[].co_id | number | 是 |  | 公司编号 |
| level_data[].serial_id | string | 是 |  | 流水单号 出仓取o_id；退仓取io_id；退款取as_id；换货取as_id |
| level_data[].serial_type | number | 是 |  | -	流水类型 出仓：1；退仓：2；退款：3；换货：4 |
| level_data[].ensemble_check_status | string | 是 |  | 流水核销状态 未核销：0；部分核销：1；已核销：2 明细全部未核销，则流水核销状态未核销；明细全部已核销，则流水核销状态已核销；其他情况流水核销状态未部分核销 |
| level_data[].ensemble_outer_push_status | string | 是 |  | 流水推送状态 未推送：0；部分推送：1；已推送：2 明细全部未推送，则流水核销状态未推送；明细全部已推送，则流水核销状态已推送；其他情况流水核销状态未部分推送 |
| level_data[].ensemble_order_sign_status | string | 是 |  | 流水妥投状态 未妥投：0；部分妥投：1；已妥投：2 明细全部未妥投，则流水核销状态未妥投；明细全部已妥投，则流水核销状态已妥投；其他情况流水核销状态未部分妥投 |
| level_data[].bc_begin_date | string | 是 |  | 核销开始时间 |
| level_data[].bc_end_date | string | 是 |  | 核销结束时间 |
| level_data[].line_count | number | 是 |  | 明细行数 |
| level_data[].detail_type_data | array | 是 |  | 第二层数据集合 |
| level_data[].detail_type_data[] | object | 否 |  |  |
| level_data[].detail_type_data[].every_serial_type | number | 是 |  | 流水明细类型 出仓：[销售出仓：1；妥投：2；销售出仓调整：3；销售出仓收款：4] 退仓：[销售退仓：5] 退款：[销售退款：6；销售退款调整：7；销售退款收款：8] 换货：[换货退款：9；换货退款调整：10；换货退款收款：11] 销售出仓包含：销售出仓、无出入库单出库 销售退款包含：销售退款、无出入库单退货 换货包含：换货、无出入库单换货 |
| level_data[].detail_type_data[].inout_result_detai_data | array | 是 |  | 第三层数据集合 |
| level_data[].detail_type_data[].inout_result_detai_data[] | object | 否 |  |  |
| level_data[].detail_type_data[].inout_result_detai_data[].id | number | 是 |  | 唯一id |
| level_data[].detail_type_data[].inout_result_detai_data[].actual_id | number | 是 |  | 单据号（根据单据类型返回不同单据号） |
| level_data[].detail_type_data[].inout_result_detai_data[].actual_detail_id | number | 是 |  | 子单据号（根据单据类型返回不同单据号） |
| level_data[].detail_type_data[].inout_result_detai_data[].io_date | string | 是 |  | 出入库时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].io_type | number | 是 |  | 出入库方向 |
| level_data[].detail_type_data[].inout_result_detai_data[].red_blue_flag | number | 是 |  | 红蓝字 |
| level_data[].detail_type_data[].inout_result_detai_data[].wms_co_name | string | 是 |  | 分仓 |
| level_data[].detail_type_data[].inout_result_detai_data[].wh_name | string | 是 |  | 仓库 |
| level_data[].detail_type_data[].inout_result_detai_data[].link_io_id | integer | 是 |  | 联调拨原单 |
| level_data[].detail_type_data[].inout_result_detai_data[].bill_detail_type | string | 是 |  | 单据类型 |
| level_data[].detail_type_data[].inout_result_detai_data[].bill_flag | string | 是 |  | 单据标识 |
| level_data[].detail_type_data[].inout_result_detai_data[].inout_labels | string | 是 |  | 出入库标签 |
| level_data[].detail_type_data[].inout_result_detai_data[].inout_stock_enabled | string | 是 |  | 是否扣库存 |
| level_data[].detail_type_data[].inout_result_detai_data[].sku_id | string | 是 |  | 商品编码 |
| level_data[].detail_type_data[].inout_result_detai_data[].situation | string | 是 |  | 特殊标签 |
| level_data[].detail_type_data[].inout_result_detai_data[].is_settle | string | 是 |  | 结账状态 |
| level_data[].detail_type_data[].inout_result_detai_data[].i_id | string | 是 |  | 商品款号 |
| level_data[].detail_type_data[].inout_result_detai_data[].sku_name | string | 是 |  | 商品名称 |
| level_data[].detail_type_data[].inout_result_detai_data[].brand | string | 是 |  | 商品品牌 |
| level_data[].detail_type_data[].inout_result_detai_data[].category | string | 是 |  | 商品分类 |
| level_data[].detail_type_data[].inout_result_detai_data[].properties_value | string | 是 |  | 商品属性 |
| level_data[].detail_type_data[].inout_result_detai_data[].vc_name | string | 是 |  | 虚拟分类 |
| level_data[].detail_type_data[].inout_result_detai_data[].color | string | 是 |  | 颜色规格 |
| level_data[].detail_type_data[].inout_result_detai_data[].sent_qty | number | 是 |  | 出入库数量(实发) |
| level_data[].detail_type_data[].inout_result_detai_data[].shop_name | string | 是 |  | 店铺 |
| level_data[].detail_type_data[].inout_result_detai_data[].drp_co_id_from_name | string | 是 |  | 分销商 |
| level_data[].detail_type_data[].inout_result_detai_data[].drp_co_id_to_name | string | 是 |  | 供应商(供销商) |
| level_data[].detail_type_data[].inout_result_detai_data[].bc_amount | number | 是 |  | 实收/实退金额 |
| level_data[].detail_type_data[].inout_result_detai_data[].freight | number | 是 |  | 运费收入 |
| level_data[].detail_type_data[].inout_result_detai_data[].free_amount | number | 是 |  | 商家优惠 |
| level_data[].detail_type_data[].inout_result_detai_data[].amount | number | 是 |  | 商品金额 |
| level_data[].detail_type_data[].inout_result_detai_data[].sales_tax | number | 是 |  | 销项税 |
| level_data[].detail_type_data[].inout_result_detai_data[].isales_tax_rated | number | 是 |  | 销项税率 |
| level_data[].detail_type_data[].inout_result_detai_data[].cost_price | number | 是 |  | 成本单价 |
| level_data[].detail_type_data[].inout_result_detai_data[].cost_amount | number | 是 |  | 成本金额 |
| level_data[].detail_type_data[].inout_result_detai_data[].order_qty | number | 是 |  | 订单/售后商品数量 |
| level_data[].detail_type_data[].inout_result_detai_data[].send_date | string | 是 |  | 发货时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].aftersale_confirm_date | ['string', 'null'] | 是 |  | 售后确认时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].refund_confirm_date | string | 是 |  | 退款确认时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].order_sign_date | string | 是 |  | 签收时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].order_sign_status | string | 是 |  | 签收状态 |
| level_data[].detail_type_data[].inout_result_detai_data[].as_id | ['number', 'null'] | 是 |  | 售后单号 |
| level_data[].detail_type_data[].inout_result_detai_data[].o_id | number | 是 |  | 内部单号 |
| level_data[].detail_type_data[].inout_result_detai_data[].oi_id | integer | 是 |  | 内部子单号 |
| level_data[].detail_type_data[].inout_result_detai_data[].creator_name | string | 是 |  | 业务员 |
| level_data[].detail_type_data[].inout_result_detai_data[].order_labels | string | 是 |  | 订单标签 |
| level_data[].detail_type_data[].inout_result_detai_data[].aftersale_labels | string | 是 |  | 售后标签 |
| level_data[].detail_type_data[].inout_result_detai_data[].order_type | string | 是 |  | 订单类型 |
| level_data[].detail_type_data[].inout_result_detai_data[].aftersale_type | string | 是 |  | 售后类型 |
| level_data[].detail_type_data[].inout_result_detai_data[].aftersale_question_type | string | 是 |  | 售后问题类型 |
| level_data[].detail_type_data[].inout_result_detai_data[].push_status | string | 是 |  | 推送状态 未推送：0；已推送：2；推送失败：-1 |
| level_data[].detail_type_data[].inout_result_detai_data[].push_date | string | 是 |  | 推送时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].push_period | string | 是 |  | 会计期间 |
| level_data[].detail_type_data[].inout_result_detai_data[].oc_bc_amount | number | 是 |  | 实收/实退金额(原币) |
| level_data[].detail_type_data[].inout_result_detai_data[].oc_freight | number | 是 |  | 运费收入(原币) |
| level_data[].detail_type_data[].inout_result_detai_data[].currency | string | 是 |  | 币别(原币) |
| level_data[].detail_type_data[].inout_result_detai_data[].currency_to_rmb | number | 是 |  | 兑人民币汇率(原币) |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_goods_qty | number | 是 |  | 商品数量 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_sales_income | number | 是 |  | 销售收入 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_sales_cost | number | 是 |  | 销售成本 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_paid_amount | number | 是 |  | 应收账款 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_pay_amount | number | 是 |  | 应付账款 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_amount_loss | number | 是 |  | 资产减值损失 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_sent_goods_amount | number | 是 |  | 发出商品 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_stock_goods_amount | number | 是 |  | 库存商品 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_sent_goods_qty | number | 是 |  | 发出商品数量 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_stock_goods_qty | number | 是 |  | 库存商品数量 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_nodeal_amount | number | 是 |  | 未处理 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_bill_date | string | 是 |  | 单据时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_check_goods_qty | number | 是 |  | 核销用商品数量 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_check_stock_goods_qty | number | 是 |  | 核销用库存商品数量 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_check_paid_amount | number | 是 |  | 核销用应收账款 |
| level_data[].detail_type_data[].inout_result_detai_data[].bc_result_amount | number | 是 |  | 到账金额 |
| level_data[].detail_type_data[].inout_result_detai_data[].check_no | string | 是 |  | 核销单号 |
| level_data[].detail_type_data[].inout_result_detai_data[].bc_date | string | 是 |  | 到账时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].modified | string | 是 |  | 最后更新时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].check_status | string | 是 |  | 核销状态 |
| level_data[].detail_type_data[].inout_result_detai_data[].outer_push_status | string | 是 |  | 推送状态 |
| level_data[].detail_type_data[].inout_result_detai_data[].bill_id | integer | 是 |  | 单据编号：暂时不用 |
| level_data[].detail_type_data[].inout_result_detai_data[].bill_detail_id | integer | 是 |  | 子单据编号：暂时不用 |
| level_data[].detail_type_data[].inout_result_detai_data[].bill_type | string | 是 |  | 单据大类:实际出入库/虚拟 |
| level_data[].detail_type_data[].inout_result_detai_data[].io_id | number | 是 |  | 出入库单号 |
| level_data[].detail_type_data[].inout_result_detai_data[].ioi_id | number | 是 |  | 出入库子单号 |
| level_data[].detail_type_data[].inout_result_detai_data[].asi_id | number | 是 |  | 售后明细单号 |
| level_data[].detail_type_data[].inout_result_detai_data[].wms_co_id | integer | 是 |  | 分仓编号 |
| level_data[].detail_type_data[].inout_result_detai_data[].wh_id | integer | 是 |  | 仓库编号 |
| level_data[].detail_type_data[].inout_result_detai_data[].shop_id | number | 是 |  | 店铺编号 |
| level_data[].detail_type_data[].inout_result_detai_data[].drp_co_id_from | number | 是 |  | 分销商 |
| level_data[].detail_type_data[].inout_result_detai_data[].drp_co_id_to | number | 是 |  | 供应商(供销商) |
| level_data[].detail_type_data[].inout_result_detai_data[].order_order_date | string | 是 |  | 订单下单时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].order_pay_date | string | 是 |  | 订单支付时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].order_creator | number | 是 |  | 业务员编号 |
| level_data[].detail_type_data[].inout_result_detai_data[].inout_type_flag | number | 是 |  | 1--发货出库，2--撤销发货 |
| level_data[].detail_type_data[].inout_result_detai_data[].remark | string | 是 |  | 备注，系统自动记录 |
| level_data[].detail_type_data[].inout_result_detai_data[].source | string | 是 |  | 数据来源：inout，order，aftersale，adjustment，delivered |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_created | string | 是 |  | 入库时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].special_flag | integer | 是 |  | 特殊标记，特殊情况的标记值 |
| level_data[].detail_type_data[].inout_result_detai_data[].gid | string | 是 |  | 调整的guid |
| level_data[].detail_type_data[].inout_result_detai_data[].first_send_date | string | 是 |  | 原始线上单号首次发货时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].summary | string | 是 |  | 摘要，用户手动记录 |
| level_data[].detail_type_data[].inout_result_detai_data[].l_id | string | 是 |  | 快递单号 |
| level_data[].detail_type_data[].inout_result_detai_data[].bc_operate_date | string | 是 |  | 核销时的系统时间 |
| level_data[].detail_type_data[].inout_result_detai_data[].check_user | string | 是 |  | 操作用户（手动核销、手动调整等的操作账号） |
| level_data[].detail_type_data[].inout_result_detai_data[].check_modified | string | 是 |  | 用户操作记录的修改时间（手动核销、撤销核销、手动调整等操作） |
| level_data[].detail_type_data[].inout_result_detai_data[].check_amount_split_type | string | 是 |  | 用户选择的金额分摊方式（系统分摊：Auto手工输入：User） |
| level_data[].detail_type_data[].inout_result_detai_data[].bc_remark | string | 是 |  | 核销备注（用户输入的备注） |
| level_data[].detail_type_data[].inout_result_detai_data[].lc_id | string | 是 |  | 快递公司 |
| level_data[].detail_type_data[].inout_result_detai_data[].dw_fc_dealt_amount | number | 是 |  | 已处理，针对未处理的已处理 |
| level_data[].detail_type_data[].inout_result_detai_data[].platform_subsidy | number | 是 |  | 平台补贴到账 |
| level_data[].detail_type_data[].inout_result_detai_data[].buyer_pay_amount | number | 是 |  | 买家实付到账 |
| level_data[].detail_type_data[].inout_result_detai_data[].batch_id | string | 是 |  | 生产批次 |
| level_data[].detail_type_data[].inout_result_detai_data[].produced_date | string | 是 |  | 生产日期 |
| level_data[].detail_type_data[].inout_result_detai_data[].expiration_date | string | 是 |  | 有效日期 |
| level_data[].detail_type_data[].inout_result_detai_data[].is_gift | number | 是 |  | 赠品标识,1:赠品；0:非赠品 |

### 请求示例

```json
{
  "page_index": 1,
  "page_size": 25,
  "time_type": 0,
  "begin_date": "2023-03-01 10:20:30",
  "end_date": "2023-05-22 11:10:12",
  "shop_id": null,
  "code": null,
  "code_type": null,
  "bill_detail_type": null,
  "bill_flag": null,
  "push_period": null,
  "is_settle": null,
  "situation": null,
  "outer_push_status": null
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": {
    "msg": null,
    "issuccess": true,
    "data": null,
    "level_data": [
      {
        "ensemble_check_status": "未核销",
        "ensemble_outer_push_status": "未推送",
        "ensemble_order_sign_status": null,
        "line_count": 1,
        "serial_type": 1,
        "detail_type_data": [
          {
            "every_serial_type": 1,
            "inout_result_detai_data": [
              {
                "dw_check_stock_goods_qty": -1,
                "order_labels": "线上发货",
                "aftersale_confirm_date": null,
                "dw_fc_amount_loss": 0,
                "item_so_id": null,
                "bill_type": "虚拟",
                "sku_name": "健安喜三倍浓缩鱼油胶囊/360粒*1瓶/735337",
                "id": 2738060219,
                "brand": null,
                "aftersale_labels": null,
                "bill_id": null,
                "order_sign_date": null,
                "check_amount_split_type": null,
                "bill_detail_id": null,
                "sku_id": "80001020",
                "io_id": 5100000001,
                "shop_id": 14503760,
                "properties_value": "360粒/瓶",
                "cost_amount": 0,
                "drp_co_id_to": 0,
                "red_blue_flag": 1,
                "order_sign_status": "",
                "oc_freight": 0,
                "dw_fc_nodeal_amount": 0,
                "bc_remark": null,
                "drp_co_id_to_name": "",
                "oc_bc_amount": 0,
                "dw_check_goods_qty": 1,
                "dw_fc_sales_cost": 0,
                "freight": 0,
                "dw_fc_sent_goods_amount": 0,
                "dw_fc_paid_amount": 0,
                "dw_fc_pay_amount": 0,
                "dw_check_paid_amount": 1499,
                "so_id": null,
                "order_pay_date": "2023-05-02 00:00:13",
                "bill_detail_type": "无出入库单出库",
                "currency": null,
                "dw_fc_bill_date": "2023-05-02 00:01:05",
                "wms_co_name": null,
                "situation": "",
                "free_amount": 0,
                "cost_price": 0,
                "outer_oi_id": null,
                "dw_created": "2023-05-11 06:32:52",
                "io_date": null,
                "bc_amount": 1499,
                "outer_push_status": "未推送",
                "isales_tax_rated": 0,
                "link_io_id": null,
                "check_status": "未核销",
                "aftersale_type": null,
                "raw_so_id": null,
                "dw_fc_goods_qty": 0,
                "inout_labels": null,
                "refund_confirm_date": null,
                "i_id": "80001020",
                "dw_fc_stock_goods_amount": 0,
                "dw_fc_sales_income": 0,
                "inout_type_flag": 1,
                "drp_co_id_from": 0,
                "source": "order",
                "bc_date": null,
                "bc_operate_date": null,
                "send_date": "2023-05-02 00:01:05",
                "modified": "2023-05-17 06:52:07",
                "push_date": null,
                "order_type": "普通订单",
                "vc_name": null,
                "inout_stock_enabled": null,
                "push_status": "未推送",
                "special_flag": null,
                "actual_detail_id": 301896,
                "order_creator": 0,
                "is_settle": "未结账",
                "shop_name": "抖音大贸GNC健安喜旗舰店",
                "push_period": null,
                "ioi_id": 5100000001,
                "wms_co_id": null,
                "currency_to_rmb": 0,
                "dw_fc_stock_goods_qty": -1,
                "check_user": null,
                "dw_fc_sent_goods_qty": 1,
                "bill_flag": "正常单据",
                "order_order_date": "2023-05-02 00:00:13",
                "check_no": null,
                "gid": null,
                "lc_id": null,
                "color": null,
                "as_id": null,
                "remark": "线上发货",
                "first_send_date": "2023-05-02 00:01:05",
                "sent_qty": 1,
                "check_modified": null,
                "wh_name": null,
                "aftersale_question_type": null,
                "o_id": 301480,
                "oid_count": 0,
                "summary": null,
                "amount": 1499,
                "asi_id": null,
                "actual_id": 301480,
                "drp_co_id_from_name": "",
                "order_qty": 1,
                "dw_fc_dealt_amount": 0,
                "oi_id": 301896,
                "bc_result_amount": 0,
                "sales_tax": 0,
                "wh_id": null,
                "io_type": -1,
                "creator_name": null,
                "category": null,
                "l_id": null
              }
            ]
          }
        ],
        "serial_id": "301480",
        "co_id": 12727261,
        "bc_end_date": null,
        "bc_begin_date": null
      },
      {
        "ensemble_check_status": "未核销",
        "ensemble_outer_push_status": "未推送",
        "ensemble_order_sign_status": null,
        "line_count": 1,
        "serial_type": 1,
        "detail_type_data": [
          {
            "every_serial_type": 1,
            "inout_result_detai_data": [
              {
                "dw_check_stock_goods_qty": -1,
                "order_labels": "线上发货",
                "aftersale_confirm_date": null,
                "dw_fc_amount_loss": 0,
                "item_so_id": null,
                "bill_type": "虚拟",
                "sku_name": "健安喜辅酶Q10软胶囊200MG/60粒*1瓶/785379",
                "id": 2648661743,
                "brand": null,
                "aftersale_labels": null,
                "bill_id": null,
                "order_sign_date": null,
                "check_amount_split_type": null,
                "bill_detail_id": null,
                "sku_id": "80001024",
                "io_id": 5100000001,
                "shop_id": 14503769,
                "properties_value": "60粒/瓶",
                "cost_amount": 0,
                "drp_co_id_to": 0,
                "red_blue_flag": 1,
                "order_sign_status": "",
                "oc_freight": 0,
                "dw_fc_nodeal_amount": 0,
                "bc_remark": null,
                "drp_co_id_to_name": "",
                "oc_bc_amount": 0,
                "dw_check_goods_qty": 1,
                "dw_fc_sales_cost": 0,
                "freight": 0,
                "dw_fc_sent_goods_amount": 0,
                "dw_fc_paid_amount": 0,
                "dw_fc_pay_amount": 0,
                "dw_check_paid_amount": 225.6,
                "so_id": null,
                "order_pay_date": "2023-05-04 00:00:17",
                "bill_detail_type": "无出入库单出库",
                "currency": null,
                "dw_fc_bill_date": "2023-05-04 00:00:19",
                "wms_co_name": null,
                "situation": "",
                "free_amount": 0,
                "cost_price": 0,
                "outer_oi_id": null,
                "dw_created": "2023-05-11 21:24:51",
                "io_date": null,
                "bc_amount": 225.6,
                "outer_push_status": "未推送",
                "isales_tax_rated": 0,
                "link_io_id": null,
                "check_status": "未核销",
                "aftersale_type": null,
                "raw_so_id": null,
                "dw_fc_goods_qty": 0,
                "inout_labels": null,
                "refund_confirm_date": null,
                "i_id": "80001024",
                "dw_fc_stock_goods_amount": 0,
                "dw_fc_sales_income": 0,
                "inout_type_flag": 1,
                "drp_co_id_from": 0,
                "source": "order",
                "bc_date": null,
                "bc_operate_date": null,
                "send_date": "2023-05-04 00:00:19",
                "modified": "2023-05-13 12:07:08",
                "push_date": null,
                "order_type": "普通订单",
                "vc_name": null,
                "inout_stock_enabled": null,
                "push_status": "未推送",
                "special_flag": null,
                "actual_detail_id": 305672,
                "order_creator": 0,
                "is_settle": "未结账",
                "shop_name": "抖音跨境GNC健安喜海外旗舰店",
                "push_period": null,
                "ioi_id": 5100000001,
                "wms_co_id": null,
                "currency_to_rmb": 0,
                "dw_fc_stock_goods_qty": -1,
                "check_user": null,
                "dw_fc_sent_goods_qty": 1,
                "bill_flag": "正常单据",
                "order_order_date": "2023-05-04 00:00:17",
                "check_no": null,
                "gid": null,
                "lc_id": null,
                "color": null,
                "as_id": null,
                "remark": "线上发货",
                "first_send_date": "2023-05-04 00:00:19",
                "sent_qty": 1,
                "check_modified": null,
                "wh_name": null,
                "aftersale_question_type": null,
                "o_id": 305239,
                "oid_count": 0,
                "summary": null,
                "amount": 225.6,
                "asi_id": null,
                "actual_id": 305239,
                "drp_co_id_from_name": "",
                "order_qty": 1,
                "dw_fc_dealt_amount": 0,
                "oi_id": 305672,
                "bc_result_amount": 0,
                "sales_tax": 0,
                "wh_id": null,
                "io_type": -1,
                "creator_name": null,
                "category": null,
                "l_id": null
              }
            ]
          }
        ],
        "serial_id": "305239",
        "co_id": 12727261,
        "bc_end_date": null,
        "bc_begin_date": null
      }
    ],
    "page_index": 1,
    "has_next": true,
    "data_count": 573,
    "page_count": 23,
    "page_size": 25
  },
  "request_id": null
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

## 【聚核账收费接口】回写出入库明细推送状态

`/open/webapi/pfapi/openinoutchecking/writebackinoutresultdetailforpush`

| 项 | 内容 |
|---|---|
| 接口名称 | 【聚核账收费接口】回写出入库明细推送状态 |
| 接口路径 | `/open/webapi/pfapi/openinoutchecking/writebackinoutresultdetailforpush` |
| docType / docId | 36 / 533 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=533 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfapi/openinoutchecking/writebackinoutresultdetailforpush` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfapi/openinoutchecking/writebackinoutresultdetailforpush` |


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
| id | integer | 是 | 1 | 主键id |
| outerPushStatus | integer | 是 | 2 | 推送状态 已推送：2；推送失败：-1 |
| failReason | string | 否 |  | 失败原因 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 |  | 状态码 |
| issuccess | boolean | 否 |  | 是否成功 |
| msg | string | 否 |  | 错误信息 |

### 请求示例

```json
null
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
  "code": 120,
  "msg": "错误信息",
  "request_id": "xxxxxxxxx",
  "data": "{}/[]"
}
```


---

## 【聚核账收费接口】获取新出入库流水汇总数据

`/open/webapi/pfopen/inoutchecking/getinoutgroupdetail`

| 项 | 内容 |
|---|---|
| 接口名称 | 【聚核账收费接口】获取新出入库流水汇总数据 |
| 接口路径 | `/open/webapi/pfopen/inoutchecking/getinoutgroupdetail` |
| docType / docId | 36 / 634 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=634 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/inoutchecking/getinoutgroupdetail` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/inoutchecking/getinoutgroupdetail` |


### 接口说明

收费接口如需开通请联系销售/运营沟通
 界面菜单：出入库流水汇总--多维度汇总
 聚合字段返回为动态返回，未包含在聚合字段里边不返回该字段

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
| data_type | integer | 是 | 1 | 数据类型 出入库 1； 应收2；收款3 （说明：本接口推送数据，均为出入库流水明细数据。 推送单据为出入库时，查询时间为单据时间； 推送单据为应收时，查询时间取决于版本（出库版、妥投版应收时间为单据时间，到账版应收时间为核销时间）； 推送单据为收款单时，查询时间为到账时间） |
| begin_date | string | 是 | 2023-04-01  | 开始时间 （YYYY-MM-DD） |
| end_date | string | 是 | 2023-05-01 | 结束时间（YYYY-MM-DD）查询时结束时间会自动+1 |
| bill_detail_type | string | 否 | 销售出仓,销售退货,无信息件,无出入库单出库,无出入库单退货 | 单据类型：（可传多个，英文逗号分隔） |
| bill_flag | integer | 否 | 0 | 单据状态 正常单据：0； 历史单据：1； 结账后变更单据：2； 无信息件：3； 仅推送：4； 异常单据：5； 全部：null |
| shop_id | string | 是 |  | 店铺id |
| push_period | string | 否 |  | 会计期间 |
| is_settle | integer | 否 |  | 结账状态 未结账：0；已结账：1；结账中：2；反结账中：3；结账失败：4；反结账失败：5 |
| outer_push_status | string | 否 |  | 推送状态 未推送：0；已推送：2；推送失败：-1 |
| is_check_wash_finished | boolean | 否 | false | 是否查询洗数完成：true：是；false：否；不传默认为false。 |
| check_way | array | 否 |  | 金额核销方式，自动核销（有账单）：AutoCheck：0；手工核销（有账单）：UserCheck：1；手工调整（无账单）：UserAdjustment：2，未核销Null：3;无明细核销（有账单）：4；强制核销：5）收入调整-有货款核销：6，收入调整-无货款有应收核销：7，收入调整-无货款无明细核销：8 |
| check_way[] | number | 否 |  |  |
| date_group | integer | 否 |  | 周期：按月（YYYY-MM）聚合，时间包括请求时间，和单据时间。按日0(默认)，传编号按月1 |
| group_codes | array | 是 |  | 聚合维度编号1. 店铺（默认） 2.仓库 3.商品品牌4.商品分类5.虚拟分类6.商品款号7.分销商8.供应商9.商品编码（默认)10.币种 11.分仓 12.虚拟仓 13.达人 14.红蓝字 15.出入库方向 16.单位 17.订单类型 |
| group_codes[] | integer | 否 | 1 |  |
| current_page | number | 是 |  | 当前页码 |
| page_size | number | 是 |  | 每页行数 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 0表示正常 |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].co_id | number | 是 |  | 公司id |
| data[].shop_id | number | 否 |  | 店铺(聚合字段返参，聚合字段如果没有不返回) |
| data[].shop_name | string | 否 |  | 店铺名 |
| data[].wh_id | ['number', 'null'] | 否 |  | 仓库编号(聚合字段返参，聚合字段如果没有不返回) |
| data[].wh_name | ['string', 'null'] | 否 |  | 仓库名称（和仓库编号wh_id同时返回) |
| data[].brand | ['null', 'string'] | 否 |  | 商品品牌(聚合字段返参，聚合字段如果没有不返回) |
| data[].category | ['null', 'string'] | 否 |  | 商品分类(聚合字段返参，聚合字段如果没有不返回) |
| data[].vc_name | null | 否 |  | 虚拟分类(聚合字段返参，聚合字段如果没有不返回) |
| data[].i_id | string | 否 |  | 商品款号(聚合字段返参，聚合字段如果没有不返回) |
| data[].drp_co_id_from | number | 否 |  | 分销商编码(聚合字段返参，聚合字段如果没有不返回) |
| data[].drp_co_id_from_name | string | 否 |  | 分销商名称（和商品编码sku_id同时返回） |
| data[].drp_co_id_to | number | 否 |  | 供应商(聚合字段返参，聚合字段如果没有不返回) |
| data[].drp_co_id_to_name | string | 否 |  | 供应商 (和供销商编号drp_co_id_to同时返回) |
| data[].sku_id | string | 否 |  | 商品编码(聚合字段返参，聚合字段如果没有不返回) |
| data[].sku_name | string | 否 |  | 商品名称（和商品编码sku_id同时返回） |
| data[].currency | string | 否 |  | 币别(原币)(聚合字段返参，聚合字段如果没有不返回) |
| data[].dw_fc_bill_date | string | 是 |  | 单据时间 |
| data[].bc_date | string | 是 |  | 到账时间 |
| data[].order_qty | number | 是 |  | 订单/售后商品数量 |
| data[].bc_amount | number | 是 |  | 实收/实退金额 |
| data[].freight | number | 是 |  | 其中运费收入 |
| data[].free_amount | ['number', 'null'] | 是 |  | 商家优惠 |
| data[].amount | number | 是 |  | 商品金额 |
| data[].dw_fc_sales_income | number | 是 |  | 销售收入 |
| data[].dw_fc_sales_cost | number | 是 |  | 销售成本 |
| data[].dw_fc_paid_amount | number | 是 |  | 应收账款 |
| data[].dw_fc_pay_amount | number | 是 |  | 应付账款 |
| data[].dw_fc_amount_loss | number | 是 |  | 资产减值损失 |
| data[].dw_fc_sent_goods_amount | number | 是 |  | 发出商品 |
| data[].dw_fc_stock_goods_amount | number | 是 |  | 库存商品 |
| data[].dw_fc_sent_goods_qty | number | 是 |  | 发出商品数量 |
| data[].dw_fc_stock_goods_qty | number | 是 |  | 库存商品数量 |
| data[].dw_fc_nodeal_amount | number | 是 |  | 未处理 |
| data[].dw_check_goods_qty | number | 是 |  | 核销用商品数量 |
| data[].dw_check_stock_goods_qty | number | 是 |  | 核销用库存商品数量 |
| data[].dw_check_paid_amount | number | 是 |  | 核销用应收账款 |
| data[].bc_result_amount | number | 是 |  | 到账金额 |
| data[].platform_subsidy | ['number', 'null'] | 是 |  | 其中：平台补贴到账 |
| data[].buyer_pay_amount | ['number', 'null'] | 是 |  | 其中：买家实付到账 |
| data[].adjustment_platform_subsidy | string | 是 |  | 平台补贴调整 |
| data[].adjustment_buyer_pay_amount	 | string | 是 |  | 买家实付调整 |
| data[].page | object | 是 |  |  |
| data[].page.current_page | number | 是 |  |  |
| data[].page.page_size | number | 是 |  |  |
| data[].page.count | number | 是 |  |  |
| data[].page.index | number | 是 |  |  |
| msg | string | 否 |  | 错误提示文案 |

### 请求示例

```json
{
  "end_date": "2023-05-01 10:30:40",
  "bill_flag": 0,
  "begin_date": "2023-04-01 10:30:40",
  "is_settle": 0,
  "outer_push_status": "",
  "push_period": "",
  "group_codes": [],
  "shop_id": "",
  "date_group": 0,
  "data_type": 1,
  "bill_detail_type": "销售出仓,销售退货,无信息件,无出入库单出库,无出入库单退货",
  "is_check_wash_finished": false,
  "current_page": 0,
  "check_way": [],
  "page_size": 0
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": [
    {
      "dw_fc_stock_goods_amount": -38,
      "dw_check_stock_goods_qty": -2,
      "dw_check_goods_qty": 2,
      "dw_fc_sales_cost": 0,
      "freight": 0,
      "dw_fc_sales_income": 0,
      "dw_fc_sent_goods_amount": 38,
      "dw_fc_paid_amount": 0,
      "platform_subsidy": null,
      "dw_fc_amount_loss": 0,
      "dw_fc_pay_amount": 0,
      "dw_check_paid_amount": 0,
      "sku_name": "[体验装]柏瑞美光缎多肽光透粉底霜N10+W11",
      "currency": "RMB",
      "dw_fc_bill_date": "2023-07-29",
      "buyer_pay_amount": null,
      "wms_co_name": null,
      "free_amount": 0,
      "amount": 0,
      "bc_amount": 0,
      "co_id": 12906482,
      "sku_id": "PRF010069",
      "order_qty": 2,
      "shop_name": "PRAMY柏瑞美官方旗舰店",
      "bc_result_amount": null,
      "shop_id": 14946509,
      "wms_co_id": null,
      "bc_adjustment_amount": null,
      "dw_fc_stock_goods_qty": -2,
      "dw_fc_sent_goods_qty": 2,
      "dw_fc_nodeal_amount": 0
    },
    {
      "dw_fc_stock_goods_amount": 0,
      "dw_check_stock_goods_qty": -2,
      "dw_check_goods_qty": 2,
      "dw_fc_sales_cost": 0,
      "freight": 0,
      "dw_fc_sales_income": 0,
      "dw_fc_sent_goods_amount": 0,
      "dw_fc_paid_amount": 0,
      "platform_subsidy": 0,
      "dw_fc_amount_loss": 0,
      "dw_fc_pay_amount": 0,
      "dw_check_paid_amount": 89.9,
      "sku_name": "柏瑞美后台保湿定妆喷雾(柔焦雾面)-B3",
      "currency": "RMB",
      "dw_fc_bill_date": "2023-07-29",
      "buyer_pay_amount": 89.9,
      "wms_co_name": null,
      "free_amount": 0,
      "amount": 89.9,
      "bc_amount": 89.9,
      "co_id": 12906482,
      "sku_id": "PRF020067",
      "order_qty": 2,
      "shop_name": "PRAMY柏瑞美官方旗舰店",
      "bc_result_amount": 89.9,
      "shop_id": 14946509,
      "wms_co_id": null,
      "bc_adjustment_amount": 0,
      "dw_fc_stock_goods_qty": -2,
      "dw_fc_sent_goods_qty": 2,
      "dw_fc_nodeal_amount": 0
    },
    {
      "dw_fc_stock_goods_amount": 0,
      "dw_check_stock_goods_qty": -2,
      "dw_check_goods_qty": 2,
      "dw_fc_sales_cost": 0,
      "freight": 0,
      "dw_fc_sales_income": 0,
      "dw_fc_sent_goods_amount": 0,
      "dw_fc_paid_amount": 0,
      "platform_subsidy": null,
      "dw_fc_amount_loss": 0,
      "dw_fc_pay_amount": 0,
      "dw_check_paid_amount": 0,
      "sku_name": "柏瑞美净透卸妆水旅行装",
      "currency": "RMB",
      "dw_fc_bill_date": "2023-07-29",
      "buyer_pay_amount": null,
      "wms_co_name": null,
      "free_amount": 0,
      "amount": 0,
      "bc_amount": 0,
      "co_id": 12906482,
      "sku_id": "PRF030023",
      "order_qty": 2,
      "shop_name": "PRAMY柏瑞美官方旗舰店",
      "bc_result_amount": null,
      "shop_id": 14946509,
      "wms_co_id": null,
      "bc_adjustment_amount": null,
      "dw_fc_stock_goods_qty": -2,
      "dw_fc_sent_goods_qty": 2,
      "dw_fc_nodeal_amount": 0
    },
    {
      "dw_fc_stock_goods_amount": -38,
      "dw_check_stock_goods_qty": -2,
      "dw_check_goods_qty": 2,
      "dw_fc_sales_cost": 0,
      "freight": 0,
      "dw_fc_sales_income": 0,
      "dw_fc_sent_goods_amount": 38,
      "dw_fc_paid_amount": 0,
      "platform_subsidy": null,
      "dw_fc_amount_loss": 0,
      "dw_fc_pay_amount": 0,
      "dw_check_paid_amount": 0,
      "sku_name": "[臻品]柏瑞美柏瑞美美妆蛋(印刷版)",
      "currency": "RMB",
      "dw_fc_bill_date": "2023-07-29",
      "buyer_pay_amount": null,
      "wms_co_name": null,
      "free_amount": 0,
      "amount": 0,
      "bc_amount": 0,
      "co_id": 12906482,
      "sku_id": "PRF060130",
      "order_qty": 2,
      "shop_name": "PRAMY柏瑞美官方旗舰店",
      "bc_result_amount": null,
      "shop_id": 14946509,
      "wms_co_id": null,
      "bc_adjustment_amount": null,
      "dw_fc_stock_goods_qty": -2,
      "dw_fc_sent_goods_qty": 2,
      "dw_fc_nodeal_amount": 0
    }
  ],
  "page": {
    "pages": 1,
    "count": 4,
    "index": 0,
    "current_page": 1,
    "page_size": 300
  }
}
```


### 异常示例

_无_


---

## 【聚核账收费接口】汇总推送状态回写

`/open/webapi/pfopen/inoutchecking/pushinoutgroupdetailresult`

| 项 | 内容 |
|---|---|
| 接口名称 | 【聚核账收费接口】汇总推送状态回写 |
| 接口路径 | `/open/webapi/pfopen/inoutchecking/pushinoutgroupdetailresult` |
| docType / docId | 36 / 635 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=635 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/inoutchecking/pushinoutgroupdetailresult` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/inoutchecking/pushinoutgroupdetailresult` |


### 接口说明

收费接口如需开通请联系销售/运营沟通
 聚合字段返回为动态返回，未包含在聚合字段里边不返回该字段

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
| data_type | integer | 是 | 2 | 数据类型 出入库 1； 应收2；收款3 |
| begin_date | string | 是 | 2023-6-1 | 开始时间 （YYYY-MM-DD） |
| end_date | string | 是 | 2023-6-30 | 结束时间（YYYY-MM-DD） |
| bill_detail_type | string | 否 | 妥投,到账视为妥投,手动调整,自动调整,销售退款,换货,无出入库单退货,无出入库单换货,未处理冲平,未处理结转 | 单据类型：（可传多个，英文逗号分隔） |
| bill_flag | integer | 否 |  | 单据状态 正常单据：0； 历史单据：1； 结账后变更单据：2； 无信息件：3； 仅推送：4； 异常单据：5； 全部：null |
| shop_id | integer | 否 | 10397005 | 店铺id |
| push_period | string | 否 |  | 会计期间 |
| is_settle | integer | 否 |  | 结账状态 未结账：0；已结账：1；结账中：2；反结账中：3；结账失败：4；反结账失败：5 |
| outer_push_status | string | 是 | 2 | 推送状态 未推送：0；已推送：2；推送失败：-1 |
| fail_reason | string | 否 |  | 推送失败原因outerPushStatus=-1才写入 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | object | 否 |  | 返回页面配置 |
| data.current_page | number | 否 |  |  |
| data.page_size | number | 否 |  |  |
| data.count | number | 否 |  | 总条数 |
| data.index | number | 否 |  |  |
| code | number | 否 |  | 0表示正常 |
| msg | null | 否 |  | 错误提示文案 |

### 请求示例

```json
{
  "end_date": "2023-6-30",
  "bill_flag": 0,
  "shop_id": 10397005,
  "begin_date": "2023-6-1",
  "data_type": 2,
  "bill_detail_type": "妥投,到账视为妥投,手动调整,自动调整,销售退款,换货,无出入库单退货,无出入库单换货,未处理冲平,未处理结转",
  "is_settle": 0,
  "outer_push_status": "2",
  "push_period": "",
  "fail_reason": ""
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "count": 0,
    "index": 0,
    "current_page": 0,
    "page_size": 0
  }
}
```


### 异常示例

_无_


---

## 【胜算收费接口】获取胜算日常记账数据

`/open/webapi/pfopen/pfopenorderfee/getopenfeeflowing`

| 项 | 内容 |
|---|---|
| 接口名称 | 【胜算收费接口】获取胜算日常记账数据 |
| 接口路径 | `/open/webapi/pfopen/pfopenorderfee/getopenfeeflowing` |
| docType / docId | 36 / 970 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=970 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/pfopenorderfee/getopenfeeflowing` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/pfopenorderfee/getopenfeeflowing` |


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
| time_type | string | 是 | modified | 时间类型：modified：修改时间；fee_time：费用发生时间 |
| start_time | string | 是 | 2024-03-22 | 开始时间，闭区间 |
| end_time | string | 是 | 2024-03-30 | 结束时间，开区间 |
| cursor | number | 是 | 1 | 游标（ long类型，第一页从0开始，接口会返回是否有下一页（has_next），第二页开始传上一次返回的游标值） |
| shop_ids | string | 否 | 10156284,10040204 | 店铺id列表多个都好隔开10156284,10040204 |
| page_size | number | 否 | 10 | 页大小 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 0表示正常 |
| msg | string | 否 |  | 错误提示文案 |
| data | object | 否 |  | 胜算日常记账集合 |
| data.trance_id | string | 否 |  | 链路id |
| data.cursor | number | 否 |  | 游标 |
| data.has_next | boolean | 否 |  | 是否有下一页 |
| data.data | array | 否 |  |  |
| data.data[] | object | 否 |  |  |
| data.data[].auto_id | number | 否 |  | 记录流水号 |
| data.data[].shop_id | number | 否 |  | 店铺编码 |
| data.data[].amount | number | 否 |  | 费用金额 |
| data.data[].fee_time | string | 否 |  | 费用发生时间 |
| data.data[].status | string | 否 |  | 审核状态 |
| data.data[].is_split | number | 否 |  | 是否按日期分摊 |
| data.data[].split_begin_date | string | 否 |  | 分摊开始时间 |
| data.data[].split_end_date | string | 否 |  | 分摊结束时间 |
| data.data[].remark | string | 否 |  | 备注 |
| data.data[].account | string | 否 |  | 账户编码 |
| data.data[].account_name | string | 否 |  | 账户名称 |
| data.data[].csg_code | string | 否 |  | 利润表项目编码 |
| data.data[].csg_name | string | 否 |  | 利润表项目名称 |
| data.data[].csg_io | number | 否 |  | 利润表项目收支方向:1表示收入，其它值均表示支出 |
| data.data[].csg_id | string | 否 |  | 利润表项目Id |
| data.data[].fee_type | string | 否 |  | 1-已发生费用; 0-预估费用; |
| data.data[].oc_amount | string | 否 |  | 原币金额 |
| data.data[].currency | string | 否 |  | 原币币种的代码，可到ERP的“汇率管理”菜单中查看币种名称 |
| data.data[].del_flag | number | 否 |  | 是否被删除：0表示有效数据，大于0表示已被删除 |
| data.data[].primary_key | string | 否 |  | 主键，可根据此字段来更新数据 |

### 请求示例

```json
{
  "cursor": 1,
  "start_time": "2024-03-22",
  "time_type": "modified",
  "end_time": "2024-03-30",
  "shop_ids": "10156284,10040204",
  "page_size": 10
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "cursor": 0,
    "trance_id": "",
    "data": [
      {
        "csg_name": "",
        "amount": 0,
        "split_end_date": "",
        "is_split": 0,
        "remark": "",
        "fee_type": "",
        "auto_id": 0,
        "shop_id": 0,
        "fee_time": "",
        "account_name": "",
        "csg_id": "",
        "csg_code": "",
        "csg_io": 0,
        "split_begin_date": "",
        "account": "",
        "status": ""
        "primaryKey": "45737286"
      }
    ],
    "has_next": true
  }
}
```


### 异常示例

_无_


---

## 【胜算收费接口】获取胜算链接级推广费数据

`/open/webapi/pfopen/pfopenalifee/getopenpfpromotionshopitem`

| 项 | 内容 |
|---|---|
| 接口名称 | 【胜算收费接口】获取胜算链接级推广费数据 |
| 接口路径 | `/open/webapi/pfopen/pfopenalifee/getopenpfpromotionshopitem` |
| docType / docId | 36 / 971 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=971 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/pfopenalifee/getopenpfpromotionshopitem` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/pfopenalifee/getopenpfpromotionshopitem` |


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
| time_type | string | 是 | modified | 时间类型：modified：修改时间；fee_date：费用发生时间 |
| start_time | string | 是 | 2024/1/7 | 开始时间，闭区间 |
| end_time | string | 是 | 2024/2/7 | 结束时间，开区间 |
| cursor | number | 是 | 1 | 游标（ long类型，第一页从0开始，接口会返回是否有下一页（has_next），第二页开始传上一次返回的游标值） |
| shop_ids | string | 否 | 10156284,10040204 | 店铺id列表多个都好隔开10156284,10040204 |
| page_size | number | 否 | 10 | 页大小 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 0表示正常 |
| msg | string | 否 |  | 错误提示文案 |
| data | object | 否 |  | 胜算日常记账集合 |
| data.trance_id | string | 否 |  | 链路id |
| data.cursor | number | 否 |  | 游标 |
| data.has_next | boolean | 否 |  | 是否有下一页 |
| data.data | array | 否 |  |  |
| data.data[] | object | 否 |  |  |
| data.data[].auto_id | number | 否 |  | 记录流水号 |
| data.data[].shop_id | number | 否 |  | 店铺编码 |
| data.data[].fee_time | string | 否 |  | 费用发生时间 |
| data.data[].amount | number | 否 |  | 费用金额 |
| data.data[].shop_i_id | string | 否 |  | 链接id(可能为空，为空时表示为店铺级数据) |
| data.data[].channel | string | 否 |  | 平台类型，枚举：https://www.erp321.com/app/support/document.html#page=7491 |
| data.data[].csg_code | string | 否 |  | 利润表项目编码 |
| data.data[].csg_name | string | 否 |  | 利润表项目名称 |
| data.data[].oc_amount | string | 否 |  | 原币金额 |
| data.data[].currency | string | 否 |  | 原币币种的代码，可到ERP的“汇率管理”菜单中查看币种名称 |
| data.data[].del_flag | number | 否 |  | 是否被删除：0表示有效数据，大于0表示已被删除 |
| data.data[].primary_key | string | 否 |  | 主键，可通过此字段来更新数据 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
|  |  |  |


### 请求示例

```json
{
  "cursor": 1,
  "start_time": "2024/1/7",
  "time_type": "modified",
  "end_time": "2024/2/7",
  "shop_ids": "10156284,10040204",
  "page_size": 10
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "cursor": 0,
    "trance_id": "",
    "data": [
      {
        "auto_id": 0,
        "shop_id": 0,
        "fee_time": "",
        "csg_name": "",
        "amount": 0,
        "channel": "",
        "csg_code": "",
        "shop_i_id": ""
        "primaryKey": "2011abc"
      }
    ],
    "has_next": true
  }
}
```


### 异常示例

_无_


---

## 【胜算收费接口】获取胜算平台原始账单

`/open/webapi/pfopen/pfopenalifee/getopenalipaybillrecords`

| 项 | 内容 |
|---|---|
| 接口名称 | 【胜算收费接口】获取胜算平台原始账单 |
| 接口路径 | `/open/webapi/pfopen/pfopenalifee/getopenalipaybillrecords` |
| docType / docId | 36 / 973 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=36&docId=973 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/pfopen/pfopenalifee/getopenalipaybillrecords` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/pfopen/pfopenalifee/getopenalipaybillrecords` |


### 接口说明

当前接口的数据是从平台获取的原始账单数据，没有经过处理，就好比从支付宝后台导出的文件是一样的，所以是没有账单项目和没有线上单号的；没有特殊需求不建议对接此接口，因为各平台的账单清洗规则各不一样，如果不熟悉平台规则，就清洗不出账单项目和线上单号，获取此接口的数据也产生不了价值。

 如果要获取胜算处理后的账单数据，请对接如下接口：
 https://open.jushuitan.com/document.aspx?doc_id=2373

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
| time_type | string | 是 | modified | 时间类型： fee_time：费用发生时间；modified：更新时间 |
| start_time | string | 是 | 2023/10/24 | 开始时间，闭区间 |
| end_time | string | 是 | 2023/10/25 | 结束时间，开区间 |
| cursor | number | 是 | 1 | 游标（ long类型，第一页从0开始，接口会返回是否有下一页（has_next），第二页开始传上一次返回的游标值） |
| shop_ids | string | 否 | 10156284,10040204 | 店铺id列表多个都好隔开10156284,10040204 |
| page_size | number | 否 | 10 | 页大小 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 否 |  | code对应一种特定的错误码 |
| msg | string | 否 |  | 接口信息 |
| data | object | 否 |  | 胜算日常记账集合 |
| data.trance_id | string | 否 |  | 链路id |
| data.cursor | number | 否 |  | 游标 |
| data.has_next | boolean | 否 |  | 是否有下一页 |
| data.data | array | 否 |  |  |
| data.data[] | object | 否 |  |  |
| data.data[].shop_id | number | 否 |  | 店铺编号 |
| data.data[].platform_shop_id | string | 否 |  | 平台店铺编码 |
| data.data[].channel | string | 否 |  | 数据来源渠道，对应枚举：https://www.erp321.com/app/support/document.html#page=7274 |
| data.data[].oute_trade_detail_no | string | 否 |  | 账务流水号 |
| data.data[].pay_order_no | string | 否 |  | 业务流水号 |
| data.data[].merchant_order_no | string | 否 |  | 商户订单号 |
| data.data[].sku_name | string | 否 |  | 商品名称 |
| data.data[].fee_time | string | 否 |  | 费用发生时间 |
| data.data[].in_amount | number | 否 |  | 收入金额 |
| data.data[].out_amount | number | 否 |  | 支出金额 |
| data.data[].balance | number | 否 |  | 余额 |
| data.data[].business_type | string | 否 |  | 业务类型 |
| data.data[].memo | string | 否 |  | 备注 |
| data.data[].business_desc | string | 否 |  | 业务描述 |
| data.data[].business_from | string | 否 |  | 业务账单来源 |
| data.data[].out_trade_no | string | 否 |  | 业务基础订单号 |
| data.data[].business_order_no | string | 否 |  | 业务订单号 |
| data.data[].remark | string | 否 |  | 自定义备注 |
| data.data[].del_flag | number | 否 |  | 是否被删除：0表示有效数据，大于0表示已被删除 |
| data.data[].primary_key | string | 否 |  | 主键，可通过此字段来更新数据 |

### 请求示例

```json
{
  "cursor": 1,
  "start_time": "2023/10/24",
  "time_type": "modified",
  "end_time": "2023/10/25",
  "shop_ids": "10156284,10040204",
  "page_size": 10
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": {
    "cursor": 0,
    "trance_id": "",
    "data": [
      {
        "pay_order_no": "",
        "channel": "",
        "oute_trade_detail_no": "",
        "memo": "",
        "remark": "",
        "merchant_order_no": "",
        "business_from": "",
        "in_amount": 0,
        "shop_id": 0,
        "fee_time": "",
        "out_trade_no": "",
        "balance": 0,
        "business_desc": "",
        "business_type": "",
        "out_amount": 0,
        "sku_name": "",
        "business_order_no": ""
        "primaryKey": "2011abc"
      }
    ],
    "has_next": true
  }
}
```


### 异常示例

_无_


---
