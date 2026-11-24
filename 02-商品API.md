# 聚水潭开放平台 · 商品API（线下版）

> 抓取日期：2026-11-23  
> 分类：商品API（docType=2）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=2&docId=486

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 商品类目上传/更新 | `/open/webapi/itemapi/category/addorupdate` | 486 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=486) |
| 商品历史成本价分页查询 | `/open/webapi/itemapi/skuhisvalues/getpagelist` | 1609 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=1609) |
| 绑定/解绑商品对应关系 | `/open/webapi/itemapi/skulink/bindskulinks` | 1117 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=1117) |
| 批量上传/更新普通商品资料（新版） | `/open/webapi/itemapi/itemsku/itemskubatchupload` | 1074 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=1074) |
| 商品款式更新 | `/open/webapi/itemapi/itemskuim/itemupload` | 1032 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=1032) |
| 商品恢复数据查询 | `/open/webapi/itemapi/itemsku/queryitemskuopshistory` | 836 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=836) |
| 更新商品库容信息 | `/open/webapi/itemapi/itemsku/setskubins` | 683 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=683) |
| 商品历史成本价上传 | `/open/jushuitan/itemsku/costprice/upload` | 600 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=600) |
| BOM信息上传 | `/open/webapi/itemapi/bom/save` | 495 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=495) |
| 普通商品资料上传/更新（旧版） | `/open/jushuitan/itemsku/upload` | 4 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=4) |
| 新增/修改商品多供应商 | `/open/webapi/itemapi/suppliersku/save` | 483 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=483) |
| 商品多供应商查询 | `/open/webapi/itemapi/suppliersku/getsupplierskulist` | 449 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=449) |
| 商品BOM信息查询 | `/open/webapi/itemapi/bom/getskubompagelist` | 358 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=358) |
| 组合装商品上传（批量上传） | `/open/item/combinesku/upload` | 65 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=65) |
| 普通商品资料查询（按sku查询） | `/open/sku/query` | 14 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=14) |
| 普通商品查询（按款查询） | `/open/mall/item/query` | 13 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=13) |
| 商品类目查询 | `/open/category/query` | 12 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=12) |
| 组合装商品查询 | `/open/combine/sku/query` | 11 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=11) |
| 店铺商品资料查询 | `/open/skumap/query` | 10 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=10) |
| 店铺商品资料上传 | `/open/jushuitan/skumap/upload` | 5 | [打开](https://openweb.jushuitan.com/dev-doc?docType=2&docId=5) |

## 目录

- [商品类目上传/更新](#商品类目上传更新)
- [商品历史成本价分页查询](#商品历史成本价分页查询)
- [绑定/解绑商品对应关系](#绑定解绑商品对应关系)
- [批量上传/更新普通商品资料（新版）](#批量上传更新普通商品资料新版)
- [商品款式更新](#商品款式更新)
- [商品恢复数据查询](#商品恢复数据查询)
- [更新商品库容信息](#更新商品库容信息)
- [商品历史成本价上传](#商品历史成本价上传)
- [BOM信息上传](#bom信息上传)
- [普通商品资料上传/更新（旧版）](#普通商品资料上传更新旧版)
- [新增/修改商品多供应商](#新增修改商品多供应商)
- [商品多供应商查询](#商品多供应商查询)
- [商品BOM信息查询](#商品bom信息查询)
- [组合装商品上传（批量上传）](#组合装商品上传批量上传)
- [普通商品资料查询（按sku查询）](#普通商品资料查询按sku查询)
- [普通商品查询（按款查询）](#普通商品查询按款查询)
- [商品类目查询](#商品类目查询)
- [组合装商品查询](#组合装商品查询)
- [店铺商品资料查询](#店铺商品资料查询)
- [店铺商品资料上传](#店铺商品资料上传)

---

## 商品类目上传/更新

`/open/webapi/itemapi/category/addorupdate`

| 项 | 内容 |
|---|---|
| 接口名称 | 商品类目上传/更新 |
| 接口路径 | `/open/webapi/itemapi/category/addorupdate` |
| docType / docId | 2 / 486 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=486 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/category/addorupdate` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/category/addorupdate` |


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
| c_name | string | 是 | @string | 分类名 |
| parent_c_id | number | 否 | 0 | 父级分类id |
| c_id | number | 否 | 1441261765 | 分类Id(创建时系统自动生成的值，修改时需要传) |
| sort | number | 否 | 1 | 排序 |
| is_pv | boolean | 否 | false | 是否添加PV |
| pv_names | array | 否 |  | 商品类目（只能新增颜色尺码类的属性，不支持自定义属性新增，属性不支持更新） |
| pv_names[] | string | 否 |  |  |
| enable | boolean | 否 |  | 是否启用；默认null 不修改 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 |  |  |
| msg | string | 否 |  |  |
| data | object | 否 |  |  |
| data.c_id | number | 否 |  | 类目id |
| data.parent_c_id | number | 是 |  | 父级类目id |
| request_id | string | 否 |  |  |

### 请求示例

```json
{
  "pv_names": [],
  "parent_c_id": 0,
  "is_pv": false,
  "c_id": 1441261765,
  "c_name": "@string",
  "sort": 1
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": {
    "parent_c_id": 0,
    "c_id": 0
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 商品历史成本价分页查询

`/open/webapi/itemapi/skuhisvalues/getpagelist`

| 项 | 内容 |
|---|---|
| 接口名称 | 商品历史成本价分页查询 |
| 接口路径 | `/open/webapi/itemapi/skuhisvalues/getpagelist` |
| docType / docId | 2 / 1609 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=1609 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/skuhisvalues/getpagelist` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/skuhisvalues/getpagelist` |


### 接口说明

修改时间或者商品编码必填一项 修改起始结束时间必须同时存在 修改开始时间必须小于结束时间 最大查询范围7天

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
| sku_ids | array | 是 |  | 商品编码(修改时间商品编码必填一项) |
| sku_ids[] | string | 否 | #001xxx1 |  |
| wms_co_ids | array | 否 |  | 仓储方集合 |
| wms_co_ids[] | number | 否 |  |  |
| modified_start | string | 是 | 2026-08-01 | 修改时间开始(修改时间商品编码必填一项) |
| modified_end | string | 是 | 2026-08-07 | 修改时间截至 |
| page | object | 是 |  | 分页对象 |
| page.current_page | number | 是 | 1 | 当前页(默认50，最大100条) |
| page.page_size | number | 是 | 50 | 页码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.list | array | 否 |  |  |
| data.list[] | object | 否 |  |  |
| data.list[].sku_id | string | 否 |  | 商品编码 |
| data.list[].cost_price | number | 否 |  | 成本价 |
| data.list[].end_date | string | 否 |  | 截止日期 |
| data.list[].wms_co_id | number | 否 |  | 分仓公司编号，未开启分仓历史成本价的商家，0或当前公司 co_id：公司级。开了这个业务，wmsCoId不为0的表示分仓商家 |
| data.list[].modified | string | 否 |  | 修改时间 |
| data.list[].created | string | 否 |  | 创建时间 |
| data.page | object | 否 |  |  |
| data.page.current_page | number | 否 |  |  |
| data.page.page_size | number | 否 |  |  |
| data.page.count | number | 否 |  |  |
| data.page.pages | number | 否 |  |  |
| data.page.index | number | 否 |  |  |
| msg | null | 否 |  |  |
| request_id | string | 否 |  |  |

### 请求示例

```json
{
  "wms_co_ids": [],
  "sku_ids": [],
  "modified_end": "2026-08-07",
  "page": {
    "current_page": 1,
    "page_size": 50
  },
  "modified_start": "2026-08-01"
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": {
    "page": {
      "pages": 1,
      "count": 2,
      "index": 0,
      "current_page": 1,
      "page_size": 50
    },
    "list": [
      {
        "end_date": "2022-11-10",
        "wms_co_id": 11053062,
        "created": "2022-12-06 11:18:50",
        "modified": "2026-08-05 18:05:47",
        "sku_id": "001C0812",
        "cost_price": 3
      },
      {
        "end_date": "2022-11-10",
        "wms_co_id": 11053062,
        "created": "2023-01-03 14:05:24",
        "modified": "2026-08-05 18:05:43",
        "sku_id": "1234567",
        "cost_price": 3
      }
    ]
  },
  "msg_type": "string",
  "request_id": "3ccdc14417859799431081343ebe54"
}
```


### 异常示例

_无_


---

## 绑定/解绑商品对应关系

`/open/webapi/itemapi/skulink/bindskulinks`

| 项 | 内容 |
|---|---|
| 接口名称 | 绑定/解绑商品对应关系 |
| 接口路径 | `/open/webapi/itemapi/skulink/bindskulinks` |
| docType / docId | 2 / 1117 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=1117 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/skulink/bindskulinks` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/skulink/bindskulinks` |


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
| bind | boolean | 是 | true | 绑定/解绑 |
| output_links | boolean | 是 | true | 返回成功结果集 |
| links | array | 是 |  | 商品数据集合 |
| links[] | object | 否 |  | 商品对应关系 |
| links[].shop_id | integer | 是 | 4 | 店铺id |
| links[].shop_i_id | string | 是 | 20220815001 | 平台店铺款式id |
| links[].shop_sku_id | string | 是 | 202208150012 | 平台店铺商品编码 |
| links[].link_sku_id | string | 是 | hg012-6 | 对应商品编码（解绑时可空） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 |  | 错误码，0=成功 |
| data | array | 否 |  | 返回数据 |
| data[] | object | 否 |  |  |
| data[].shop_id | number | 否 |  | 店铺id |
| data[].shop_i_id | string | 否 |  | 平台店铺款式id |
| data[].shop_sku_id | string | 否 |  | 平台店铺商品编码 |
| data[].link_sku_id | string | 否 |  | 对应商品编码（解绑时可空） |
| msg | null | 否 |  | 错误信息 |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "bind": true,
  "links": [
    {
      "shop_id": 4,
      "link_sku_id": "hg012-6",
      "shop_i_id": "20220815001",
      "shop_sku_id": "202208150012"
    }
  ],
  "output_links": true
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": [
    {
      "shop_id": 0,
      "link_sku_id": "",
      "shop_i_id": "",
      "shop_sku_id": ""
    }
  ],
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

## 批量上传/更新普通商品资料（新版）

`/open/webapi/itemapi/itemsku/itemskubatchupload`

| 项 | 内容 |
|---|---|
| 接口名称 | 批量上传/更新普通商品资料（新版） |
| 接口路径 | `/open/webapi/itemapi/itemsku/itemskubatchupload` |
| docType / docId | 2 / 1074 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=1074 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/itemsku/itemskubatchupload` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/itemsku/itemskubatchupload` |


### 接口说明

系统相关界面：【商品】------【普通商品资料】
 数据流向：外部系统->聚水潭ERP

 根据商品编码sku_id更新数据

Q：接口一次最大可以上传多少个商品
 A：接口每次请求最大500

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
| is_update | boolean | 否 |  | 是否允许更新，默认true，false将跳过当前行 |
| is_add_labels | boolean | 否 |  | 是否追加商品标签，默认true，false全量覆盖 |
| is_add_other_code | boolean | 否 |  | 是否追加辅助码，默认true，false全量覆盖 |
| is_cover_item | boolean | 否 |  | 是否覆盖款，默认true：款下有多个商品，取第一个商品维护内容覆盖到款，false：不覆盖款有值的字段 |
| items | array | 是 |  | 商品数据列表（一次最大上传500条） |
| items[] | object | 否 |  |  |
| items[].i_id | string | 是 |  | 款式编码 |
| items[].sku_id | string | 是 | 766102360018017083 | 商品编码 |
| items[].batch_enabled | boolean | 否 |  | 是否开启批次生产批次 |
| items[].is_series_number | boolean | 否 |  | 是否开启序列号 |
| items[].shelf_life | number | 否 |  | 保质期(天) |
| items[].hand_day | number | 否 |  | 临期天数 |
| items[].reject_lifecycle | number | 否 |  | 保质期禁收天数 |
| items[].lockup_lifecycle | number | 否 |  | 保质期禁售天数 |
| items[].advent_lifecycle | number | 否 |  | 保质期临期预警天数 |
| items[].production_licence | string | 否 |  | 生产许可证 |
| items[].labels | array | 否 |  | 标签 |
| items[].labels[] | string | 否 |  |  |
| items[].remove_labels | array | 否 |  | 删除标签 |
| items[].remove_labels[] | string | 否 |  |  |
| items[].category_propertys | object | 否 |  | 按款显示时商品列表里的属性 传值时商品分类需存在；字段名称及字段值都可自定义，可更新 |
| items[].category_propertys.111 | string | 否 |  | 自定义属性 |
| items[].category_propertys.222 | string | 否 |  |  |
| items[].remark | string | 否 |  | 备注 |
| items[].supplier_i_id | string | 否 |  | 供应商款式编码 |
| items[].sku_code | string | 否 |  | 国标码 |
| items[].name | string | 否 |  | 名称 |
| items[].other1 | string | 否 |  | 其它属性1 |
| items[].other2 | string | 否 |  | 其它属性2 |
| items[].other3 | string | 否 |  | 其它属性3 |
| items[].other4 | string | 否 |  | 其它属性4 |
| items[].other5 | string | 否 |  | 其它属性5 |
| items[].other6 | string | 否 |  | 其它属性6 |
| items[].other7 | string | 否 |  | 其它属性7 |
| items[].other8 | string | 否 |  | 其它属性8 |
| items[].other9 | string | 否 |  | 其它属性9 |
| items[].other10 | string | 否 |  | 其它属性10 |
| items[].unit | string | 否 |  | 单位 |
| items[].supplier_sku_id | string | 否 |  | 供应商商品编码 |
| items[].market_price | string | 否 |  | 市场\|吊牌价 |
| items[].weight | string | 否 |  | 重量 |
| items[].l | number | 否 |  | 长 |
| items[].w | number | 否 |  | 宽 |
| items[].h | number | 否 |  | 高 |
| items[].brand | string | 否 |  | 品牌 |
| items[].sale_price | string | 否 |  | 基本售价 |
| items[].cost_price | string | 否 |  | 成本价 |
| items[].fj_price_rate | number | 否 |  | 成本价比率 |
| items[].short_name | string | 否 |  | 商品简称 |
| items[].properties_value | string | 否 |  | 颜色规格 |
| items[].supplier_name | string | 否 |  | 供应商名称 |
| items[].purchase_price | number | 否 |  | 采购成本价 |
| items[].vc_name | string | 否 |  | 虚拟分类 |
| items[].other_code | string | 否 |  | 辅助码 |
| items[].category | string | 否 | 衣服 - 上衣 - 连衣裙 | 分类名称（根目录空格-空格子目录） |
| items[].item_type | string | 否 |  | 商品属性 |
| items[].enabled | number | 否 |  | 商品状态：1启用/-1禁用/0备用,默认启用 |
| items[].other_price1 | number | 否 |  | 其它价格1 |
| items[].other_price2 | number | 否 |  | 其它价格2 |
| items[].other_price3 | number | 否 |  | 其它价格3 |
| items[].other_price4 | number | 否 |  | 其它价格4 |
| items[].other_price5 | number | 否 |  | 其它价格5 |
| items[].stock_disabled | boolean | 否 |  | 禁止同步，true=禁止，false=允许 |
| items[].pic | string | 否 |  | 商品图片 |
| items[].pic_big | string | 否 |  | 商品大图 |
| items[].item_pic | string | 否 |  | 款图片 |
| items[].pics | array | 否 |  | 多图，最大支持10张， pics 有值时，忽略pic、pic_big字段 |
| items[].pics[] | string | 否 |  |  |
| items[].manufacturing_enterprise | string | 否 |  | 生产企业 |
| items[].registration_certificate_no | string | 否 |  | 注册证 |
| items[].batch_format | string | 否 | 年月日 | 生产日期格 |
| items[].expiration_date | string | 否 | 2026-10-13 | 许可证到期 |
| items[].batch_end_format | string | 否 | 年月日 | 有效期格式 |
| items[].storeage | string | 否 | 储运方式3 | 储运方式 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | array | 否 |  | 为空则全部成功 |
| data[] | object | 否 |  |  |
| data[].sku_id | string | 是 |  | 商品编码 |
| data[].message | string | 是 |  | 错误描述 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "is_cover_item": true,
  "is_update": true,
  "is_add_other_code": true,
  "is_add_labels": true,
  "items": [
    {
      "i_id": "",
      "other10": "",
      "supplier_i_id": "",
      "item_type": "",
      "pic": "",
      "expiration_date": "2026-10-13",
      "fj_price_rate": 0,
      "brand": "",
      "pics": [],
      "vc_name": "",
      "other_code": "",
      "storeage": "储运方式3",
      "weight": "",
      "sku_id": "766102360018017083",
      "batch_format": "年月日",
      "labels": [],
      "unit": "",
      "properties_value": "",
      "stock_disabled": true,
      "is_series_number": true,
      "registration_certificate_no": "",
      "name": "",
      "purchase_price": 0,
      "market_price": "",
      "short_name": "",
      "sku_code": "",
      "lockup_lifecycle": 0,
      "production_licence": "",
      "remark": "",
      "pic_big": "",
      "enabled": 0,
      "shelf_life": 0,
      "batch_enabled": true,
      "other_price3": 0,
      "other_price2": 0,
      "other_price5": 0,
      "remove_labels": [],
      "other_price4": 0,
      "other9": "",
      "hand_day": 0,
      "other8": "",
      "batch_end_format": "年月日",
      "reject_lifecycle": 0,
      "other5": "",
      "other4": "",
      "advent_lifecycle": 0,
      "other7": "",
      "other6": "",
      "other1": "",
      "supplier_name": "",
      "other3": "",
      "other_price1": 0,
      "other2": "",
      "cost_price": "",
      "category_propertys": {
        "111": "",
        "222": ""
      },
      "manufacturing_enterprise": "",
      "h": 0,
      "item_pic": "",
      "l": 0,
      "sale_price": "",
      "supplier_sku_id": "",
      "w": 0,
      "category": "衣服 - 上衣 - 连衣裙"
    }
  ]
}
```


### 响应示例

```json
{
  "code": 0,
  "act": 0,
  "data": [
    {
      "sku_id": "766102360018017083",
      "message": "上传失败，失败原因：商品已存在且不允许更新"
    },
    {
      "sku_id": "766102360018017081",
      "message": "上传失败，失败原因：商品已存在且不允许更新"
    }
  ],
  "msg": null,
  "request_id": null
}
```


### 异常示例

_无_


---

## 商品款式更新

`/open/webapi/itemapi/itemskuim/itemupload`

| 项 | 内容 |
|---|---|
| 接口名称 | 商品款式更新 |
| 接口路径 | `/open/webapi/itemapi/itemskuim/itemupload` |
| docType / docId | 2 / 1032 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=1032 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/itemskuim/itemupload` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/itemskuim/itemupload` |


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
| items | array | 是 |  | 最大500条 |
| items[] | object | 否 |  |  |
| items[].i_id | string | 是 | test111 | 款式编码 |
| items[].name | string | 否 |  | 名称 |
| items[].brand | string | 否 |  | 品牌 |
| items[].category | string | 否 |  | 分类 |
| items[].vc_name | string | 否 |  | 虚拟分类 |
| items[].supplier_name | string | 否 |  | 供应商名称 |
| items[].supplier_i_id | string | 否 |  | 供应商款式编码 |
| items[].sale_price | number | 否 |  | 基本售价 |
| items[].market_price | number | 否 |  | 市场\|吊牌价 |
| items[].cost_price | number | 否 |  | 成本价 |
| items[].weight | number | 否 |  | 重量 |
| items[].unit | string | 否 |  | 单位 |
| items[].item_type | string | 否 |  | 商品属性 |
| items[].l | number | 否 |  | 长 |
| items[].w | number | 否 |  | 宽 |
| items[].h | number | 否 |  | 高 |
| items[].remark | string | 否 |  | 备注 |
| items[].pic | string | 否 |  | 主图 |
| items[].pic2 | string | 否 |  | 辅图 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].i_id | string | 否 |  | 款式编码（只返回失败的） |
| data[].message | string | 否 |  | 错误描述 |
| msg | string | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "items": [
    {
      "i_id": "test111",
      "vc_name": "",
      "supplier_i_id": "",
      "item_type": "",
      "h": 0,
      "weight": 0,
      "remark": "",
      "pic": "",
      "l": 0,
      "sale_price": 0,
      "unit": "",
      "w": 0,
      "name": "",
      "market_price": 0,
      "category": "",
      "supplier_name": "",
      "pic2": "",
      "brand": "",
      "cost_price": 0
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": [
    {
      "i_id": "",
      "message": ""
    }
  ],
  "request_id": ""
}
```


### 异常示例

_无_


---

## 商品恢复数据查询

`/open/webapi/itemapi/itemsku/queryitemskuopshistory`

| 项 | 内容 |
|---|---|
| 接口名称 | 商品恢复数据查询 |
| 接口路径 | `/open/webapi/itemapi/itemsku/queryitemskuopshistory` |
| docType / docId | 2 / 836 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=836 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/itemsku/queryitemskuopshistory` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/itemsku/queryitemskuopshistory` |


### 接口说明

对应ERP菜单-【普通商品资料】-【商品资料恢复】功能

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
| current_page | number | 是 |  | 页码 |
| page_size | number | 是 |  | 每页条数(一页最大2000条) |
| start_time | string | 是 |  | 开始时间 |
| end_time | string | 是 |  | 结束时间 |
| creatorname | string | 否 |  | 创建人名称 |
| skuid | string | 否 |  | 商品编码 |
| iid | string | 否 |  | 款式编码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.page | object | 否 |  |  |
| data.page.current_page | number | 否 |  |  |
| data.page.page_size | number | 否 |  |  |
| data.page.count | number | 否 |  |  |
| data.page.pages | number | 否 |  |  |
| data.page.index | number | 否 |  |  |
| data.list | array | 否 |  |  |
| data.list[] | object | 否 |  |  |
| data.list[].autoid | number | 否 |  | 自增编号 |
| data.list[].operation_type | string | 否 |  | 操作类型 |
| data.list[].operation_description | string | 否 |  | 操作描述 |
| data.list[].created | string | 否 |  | 创建时间 |
| data.list[].creator_name | string | 否 |  | 创建人名称 |
| data.list[].sku_id | string | 否 |  | 商品编码 |
| data.list[].i_id | string | 否 |  | 款式编码 |
| data.list[].name | string | 否 |  | 商品名称 |
| data.list[].properties_value | string | 否 |  | 颜色及规格 |
| data.list[].sku_type | string | 否 |  | 商品类型 |
| data.list[].recovery_count | null | 否 |  | 恢复次数 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "start_time": "",
  "iid": "",
  "end_time": "",
  "creatorname": "",
  "current_page": 0,
  "skuid": "",
  "page_size": 0
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "page": {
      "pages": 0,
      "count": 0,
      "index": 0,
      "current_page": 0,
      "page_size": 0
    },
    "list": [
      {
        "i_id": "",
        "recovery_count": "",
        "properties_value": "",
        "operation_type": "",
        "created": "",
        "sku_type": "",
        "autoid": 0,
        "operation_description": "",
        "name": "",
        "creator_name": "",
        "sku_id": ""
      }
    ]
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 更新商品库容信息

`/open/webapi/itemapi/itemsku/setskubins`

| 项 | 内容 |
|---|---|
| 接口名称 | 更新商品库容信息 |
| 接口路径 | `/open/webapi/itemapi/itemsku/setskubins` |
| docType / docId | 2 / 683 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=683 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/itemsku/setskubins` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/itemsku/setskubins` |


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
| data | array | 否 |  | 返回结果 |
| data[] | object | 否 |  |  |
| data[].sku_id | string | 否 |  | 商品编码 |
| data[].issuccess | boolean | 否 |  | 是否成功 |
| data[].msg | string | 否 |  | 提示信息 |
| msg | string | 否 |  |  |
| requestId | null | 否 |  |  |

### 请求示例

```json
[
  {
    "pack_qty": 0,
    "other_bin": [],
    "pack_volume": 0,
    "bin": "",
    "min_qty": 0,
    "overflow_qty": 0,
    "sku_id": "#000000002comine",
    "max_qty": 0
  }
]
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

## 商品历史成本价上传

`/open/jushuitan/itemsku/costprice/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 商品历史成本价上传 |
| 接口路径 | `/open/jushuitan/itemsku/costprice/upload` |
| docType / docId | 2 / 600 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=600 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/itemsku/costprice/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/itemsku/costprice/upload` |


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
| datas | array | 是 |  |  |
| datas[] | object | 否 |  |  |
| datas[].sku_id | string | 是 |  | 商品编码 |
| datas[].end_date | string | 是 |  | 截止时间 |
| datas[].cost_price | string | 是 |  | 历史成本价 |
| is_clear_old | boolean | 否 |  | 是否清除原历史成本价后导入 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 状态码 |
| issuccess | boolean | 是 |  | 是否成功 |
| msg | string | 是 |  | 描述信息 |

### 请求示例

```json
{
  "datas": [
    {
      "end_date": "",
      "sku_id": "",
      "cost_price": ""
    }
  ]
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
  "code": 120,
  "msg": "错误信息",
  "request_id": "xxxxxxxxx",
  "data": "{}/[]"
}
```


---

## BOM信息上传

`/open/webapi/itemapi/bom/save`

| 项 | 内容 |
|---|---|
| 接口名称 | BOM信息上传 |
| 接口路径 | `/open/webapi/itemapi/bom/save` |
| docType / docId | 2 / 495 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=495 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/bom/save` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/bom/save` |


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
| bom_list | array | 否 |  | 商品主料集合 |
| bom_list[] | object | 否 |  |  |
| bom_list[].rm_qty | number | 否 | 2.5 | 主料数量，不填，默认1 |
| bom_list[].outer_sku_id | string | 是 | ####0711新品_1 | 成品商品编码 |
| bom_list[].map_outer_sku_id | string | 是 | ####0711新品_2aa444 | 主料商品编码 |
| bom_list[].i_id | string | 是 | ####0711新品_1 | 款式编码 |
| bom_list[].is_delete | boolean | 否 |  | 是否删除主料，默认false |
| minor_list | array | 否 |  | 商品辅料集合 |
| minor_list[] | object | 否 |  |  |
| minor_list[].outer_sku_id | string | 是 | ####0711新品_1312312aa2 | 辅料商品编码 |
| minor_list[].i_id | string | 是 | ####0711新品_1 | 款式编码 |
| minor_list[].is_delete | boolean | 否 |  | 是否删除辅料，默认false |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | boolean | 否 |  |  |
| msg | string | 否 |  |  |

### 请求示例

```json
{
  "bom_list": [
    {
      "outer_sku_id": "####0711新品_1",
      "i_id": "####0711新品_1",
      "map_outer_sku_id": "####0711新品_2aa444",
      "rm_qty": 2.5,
      "is_delete": true
    },
    {
      "outer_sku_id": "####0711新品_2",
      "i_id": "####0711新品_2",
      "map_outer_sku_id": "####0711新品_222",
      "rm_qty": 2.5,
      "is_delete": true
    }
  ],
  "minor_list": [
    {
      "outer_sku_id": "####0711新品_1312312aa2",
      "i_id": "####0711新品_1",
      "is_delete": true
    }
  ]
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

## 普通商品资料上传/更新（旧版）

`/open/jushuitan/itemsku/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 普通商品资料上传/更新（旧版） |
| 接口路径 | `/open/jushuitan/itemsku/upload` |
| docType / docId | 2 / 4 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=4 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/itemsku/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/itemsku/upload` |


### 接口说明

系统相关界面：【商品】------【普通商品资料】

 数据流向：外部系统->聚水潭ERP

 Q：接口一次最大可以上传多少个商品
 A：接口每次请求最大200

 Q：为什么测试环境中的账号页面中有按款显示，正式环境中没有
 A：是否开启按款显示开关位置：【基础设置（推荐）】-->【是否开通按款显示】-->【是否开通按款显示】（开启此开关时请联系您的公司的操作ERP的负责人确认需要开通后在开通）

 Q：接口中的字段不能满足需求，我们系统中部分字段接口中也没有
 A：接口中 其他价格1-5，其他属性1-5 可作为备用字段，字段名称在ERP中可自定义修改，如需修改请联系您的ERP实施工程师或ERP首页在线客服修改

 Q:为什么可更新字段，传值数据有些更新了，有些没有更新？
 A:若字段传值空值，原有数据会被清空，不传该字段就不会被清空；方案：字段有更新 传那个字段，不更新的字段不用传
 更多普通商品api相关问题参见常见问题文档 ： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=15&currentPage=1&pageSize=20

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
| items | array | 是 |  | 商品列表 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | 001C0812 | 商品编码 |
| items[].i_id | string | 是 | 001C0812 | 款式编码 可更新 |
| items[].brand | string | 否 | NIKE12 | 品牌 可更新 |
| items[].vc_name | string | 否 | 虚拟分类12 | 虚拟分类 可更新 |
| items[].c_name | string | 否 |  | 商品分类 必须是[商品类目管理]中的叶子节点，可更新 |
| items[].s_price | number | 否 |  | 基本售价 可更新 |
| items[].item_type | string | 否 | 成品 | 商品属性，可选值["成品","半成品","原材料","包材"]，可更新 |
| items[].l | number | 否 | 1 | 长 可更新 |
| items[].w | number | 否 | 3 | 宽 可更新 |
| items[].h | number | 否 | 1 | 高 可更新 |
| items[].pic | string | 否 | 1231 | 图片地址（款图片） 可更新，varchar(300) |
| items[].pic_big | string | 否 | Pic_big1 | 大图地址 可更新，varchar(300) |
| items[].sku_pic | string | 否 | Sku_pic11 | 商品图片（sku图片） 可更新，varchar(300) |
| items[].name | string | 是 | 短袖112 | 名称 可更新 |
| items[].remark | string | 否 | 123 | 备注，可更新 |
| items[].properties_value | string | 否 | 蓝色;XXL | 颜色及规格 可更新（最多100个字符，1个汉字等于1个字符） |
| items[].short_name | string | 否 | 短袖12 | 简称 可更新 |
| items[].weight | number | 否 | 1.52 | 重量 可更新 |
| items[].enabled | integer | 否 | -1 | 是否启用，默认值1,可选值:-1=禁用,0=备用,1=启用，可更新 |
| items[].supplier_name | string | 否 | 供应商1 | 供应商名称 可更新 |
| items[].sku_code | string | 否 | 648125644612 | 国标码 可更新 |
| items[].supplier_sku_id | string | 否 | sup_sku_id12 | 供应商商品编码 可更新 |
| items[].supplier_i_id | string | 否 | sup_i_id12 | 供应商款式编码 可更新 |
| items[].other_price_1 | number | 否 |  | 其它价格1 可更新 |
| items[].other_price_2 | number | 否 |  | 其它价格2，可更新 |
| items[].other_price_3 | number | 否 |  | 其它价格3，可更新 |
| items[].other_price_4 | number | 否 |  | 其它价格4，可更新 |
| items[].other_price_5 | number | 否 |  | 其它价格5，可更新 |
| items[].other_1 | string | 否 | 2.11 | 其它属性1，可更新 |
| items[].other_2 | string | 否 | 2.21 | 其它属性2，可更新 |
| items[].other_3 | string | 否 | 2.31 | 其它属性3，可更新 |
| items[].other_4 | string | 否 | 2.41 | 其它属性4，可更新 |
| items[].other_5 | string | 否 | 2.51 | 其它属性5，可更新 |
| items[].other_6 | string | 否 |  | 其它属性6，可更新 |
| items[].other_7 | string | 否 |  | 其它属性7，可更新 |
| items[].other_8 | string | 否 |  | 其它属性8，可更新 |
| items[].other_9 | string | 否 |  | 其它属性9，可更新 |
| items[].other_10 | string | 否 |  | 其它属性10，可更新 |
| items[].stock_disabled | boolean | 否 | true | 禁止同步，true=禁止，false=允许，可更新 |
| items[].c_price | number | 否 |  | 成本价 可更新 |
| items[].market_price | number | 否 | 300 | 市场\|吊牌价 可更新 |
| items[].unit | string | 否 |  | 单位 |
| items[].labels | array | 否 |  | 增加标签 |
| items[].labels[] | string | 否 |  |  |
| items[].batch_enabled | boolean | 否 |  | 是否启用生产批次 可更新 |
| items[].is_series_number | boolean | 否 |  | 是否启用序列号 可更新 |
| items[].other_code | string | 否 |  | 辅助码；长度不超过500，系统中相关业务项需配置 |
| items[].shelf_life | integer | 否 |  | 保质期天数；必须大于0 |
| items[].hand_day | integer | 否 |  | 临期天数 |
| items[].rejectLifecycle | integer | 否 |  | 保质期禁收天数 |
| items[].lockupLifecycle | integer | 否 |  | 保质期禁售天数 |
| items[].adventLifecycle | integer | 否 |  | 保质期临期预警天数 |
| items[].CategoryPropertys | object | 否 |  | 按款显示时商品列表里的属性 传值时商品类目需存在；字段名称及字段值都可自定义，可更新 |
| items[].CategoryPropertys.年份 | string | 否 |  | 自定义属性名称和值 |
| items[].deletedlabels | array | 否 |  | 移除标签 |
| items[].deletedlabels[] | string | 否 |  |  |
| items[].production_licence | string | 否 |  | 生产许可证 |
| items[].purchase_price | number | 否 |  | 采购价 |
| is_normal | boolean | 否 |  | 校验是否已经有了组合装商品编码，默认为false,入参为 true 则校验修改的sku 类型不得为组合装，否则跳过不处理并输出错误信息 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  |  |
| data.datas | array | 是 |  |  |
| data.datas[] | object | 否 |  |  |
| data.datas[].is_success | string | 是 |  | 是否上传成功 |
| data.datas[].sku_id | string | 是 |  | 商品编码 |
| data.datas[].msg | string | 是 |  | 执行信息 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 130 | 分类【xxxxx】不存在，请修改分类或者重新维护【商品类目管理】 |  |
| 130 | 处理款(xxxxx)时发生错误:Arithmetic overflow error converting numeric to data type numeric |  |
| 130 | sku_id 必填且非空 |  |


### 请求示例

```json
{
  "items": [
    {
      "i_id": "001C0812",
      "supplier_i_id": "sup_i_id12",
      "item_type": "成品",
      "sku_pic": "Sku_pic11",
      "remark": "123",
      "pic": "1231",
      "pic_big": "Pic_big1",
      "enabled": -1,
      "shelf_life": 10,
      "batch_enabled": true,
      "s_price": 100,
      "supplier_name": "供应商1",
      "brand": "NIKE12",
      "vc_name": "虚拟分类12",
      "other_price_5": 1.52,
      "other_code": "",
      "h": 1,
      "weight": 1.52,
      "other_5": "2.51",
      "c_price": 0,
      "sku_id": "001C0812",
      "other_4": "2.41",
      "other_3": "2.31",
      "l": 1,
      "other_2": "2.21",
      "other_1": "2.11",
      "labels": [],
      "supplier_sku_id": "sup_sku_id12",
      "unit": "",
      "properties_value": "蓝色;XXL",
      "stock_disabled": true,
      "w": 3,
      "is_series_number": true,
      "name": "短袖112",
      "market_price": 300,
      "c_name": "",
      "short_name": "短袖12",
      "other_price_3": 1.32,
      "sku_code": "648125644612",
      "other_price_4": 1.42,
      "other_price_1": 1.12,
      "other_price_2": 1.22,
      "hand_day": 180,
      "rejectLifecycle": 10,
      "lockupLifecycle": 20,
      "adventLifecycle": 30,
      "production_licence": "SC001",
      "CategoryPropertys": {
        "年份": "2021",
        "季节": "春",
        "波段": "春一波",
        "面料成分": "面料",
        "面料类别": "针织类",
        "执行标准": "2019",
        "安全技术类别": " B类",
        "计划上市日期": "2020-12-24"
      }
    }
  ]
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
        "msg": "上传/更新成功",
        "sku id": "WL0400043",
        "is_success": true
      }
    ]
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

## 新增/修改商品多供应商

`/open/webapi/itemapi/suppliersku/save`

| 项 | 内容 |
|---|---|
| 接口名称 | 新增/修改商品多供应商 |
| 接口路径 | `/open/webapi/itemapi/suppliersku/save` |
| docType / docId | 2 / 483 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=483 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/suppliersku/save` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/suppliersku/save` |


### 接口说明

如果同一sku需要新增多供应商的情况下，需要多次调用接口传不同的供应商信息

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
| supplier_id | number | 是 | 235438 | 供应商Id |
| i_id | string | 是 | #001 | 款式编码 |
| sku_id | string | 是 | #001 | 商品编码 |
| supplier_sku_id | string | 否 | 测试供应商商品编码1 | 供应商商品编码 |
| supplier_i_id | string | 否 | 测试供应商商款式编码2 | 供应商商品款号 |
| cost_price | number | 否 | null | 采购成本价 |
| purchase_url | string | 否 |  | 采购链接 |
| delivery_day | number | 否 | null | 交货天数 |
| pack_qty | number | 否 | null | 装箱数 |
| remark | string | 否 |  | 备注 |
| is_default | boolean | 否 | null | 是否默认(true false null )true为设置默认 false 为移除 null 为不操作 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 |  |  |
| msg | string | 是 |  |  |
| request_id | string | 是 |  |  |

### 请求示例

```json
{
  "i_id": "#001",
  "pack_qty": "null",
  "supplier_sku_id": "测试供应商商品编码1",
  "supplier_i_id": "测试供应商商款式编码2",
  "purchase_url": "",
  "sku_id": "#001",
  "remark": "",
  "delivery_day": "null",
  "is_default": false,
  "supplier_id": 235438,
  "cost_price": "null"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "request_id": ""
}
```


### 异常示例

_无_


---

## 商品多供应商查询

`/open/webapi/itemapi/suppliersku/getsupplierskulist`

| 项 | 内容 |
|---|---|
| 接口名称 | 商品多供应商查询 |
| 接口路径 | `/open/webapi/itemapi/suppliersku/getsupplierskulist` |
| docType / docId | 2 / 449 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=449 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/suppliersku/getsupplierskulist` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/suppliersku/getsupplierskulist` |


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
| skuid | string | 否 |  | 商品编码 |
| iid | string | 否 |  | 款式编码 |
| supplier_id | number | 否 |  | 供应商id |
| begin | string | 否 | 2023-01-31 16:40 | 最早创建时间 |
| end | string | 否 | 2023-03-17 17:44:43 | 最晚创建时间 |
| current_page | number | 是 |  | 当前分页 |
| page_size | number | 是 |  | 分页数 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 |  |  |
| msg | string | 是 |  |  |
| data | object | 是 |  |  |
| data.page | object | 是 |  |  |
| data.page.pages | number | 是 |  | 第几页 |
| data.page.count | number | 是 |  | 总条数 |
| data.list | array | 是 |  |  |
| data.list[] | object | 否 |  |  |
| data.list[].i_id | string | 是 |  | 商品款式编码 |
| data.list[].supplier_i_id | string | 是 |  | 供应商品款式编码 |
| data.list[].created | string | 是 |  | 创建时间 |
| data.list[].purchase_url | string | 是 |  | 采购链接 |
| data.list[].sku_id | string | 是 |  | 商品编码 |
| data.list[].remark | string | 是 |  | 备注 |
| data.list[].pack_qty | string | 是 |  | 装箱数 |
| data.list[].supplier_sku_id | string | 是 |  | 供应商商品编码 |
| data.list[].delivery_day | string | 是 |  | 交货天数（天） |
| data.list[].supplier_name | string | 是 |  | 供应商名称 |
| data.list[].supplier_code | string | 是 |  | 供应商编码 |
| data.list[].supplier_id | string | 是 |  | 内部供应商编码 |
| data.list[].cost_price | number | 是 |  | 成本价 |

### 请求示例

```json
{
  "iid": "",
  "end": "2023-03-17 17:44:43",
  "supplier_id": 0,
  "begin": "2023-01-31 16:40",
  "skuid": "",
  "current_page": 0,
  "page_size": 0
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": {
    "page": {
      "pages": 1,
      "count": 1
    },
    "list": [
      {
        "i_id": "4564486454",
        "supplier_i_id": "4565464",
        "created": "2022-10-21 14:45:09",
        "purchase_url": null,
        "rn__": 1,
        "sku_id": "54668454242",
        "remark": null,
        "pack_qty": null,
        "supplier_sku_id": "5645645",
        "delivery_day": null,
        "supplier_name": "柚凡",
        "supplier_code": null,
        "supplier_id": 36565,
        "cost_price": 0.1
      }
    ]
  },
  "request_id": null
}
```


### 异常示例

_无_


---

## 商品BOM信息查询

`/open/webapi/itemapi/bom/getskubompagelist`

| 项 | 内容 |
|---|---|
| 接口名称 | 商品BOM信息查询 |
| 接口路径 | `/open/webapi/itemapi/bom/getskubompagelist` |
| docType / docId | 2 / 358 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=358 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/itemapi/bom/getskubompagelist` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/itemapi/bom/getskubompagelist` |


### 接口说明

bom维护界面中的信息维护了商品主料，才会查到数据

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
| modified_start | string | 否 | 2023-01-29 | 修改开始时间，时间间隔不能超过30天 |
| modified_end | string | 否 | 2023-02-28 | 修改结束时间，时间间隔不能超过30天 |
| sku_ids | array | 否 |  | 商品编码；与修改时间不能同时为空，最大50 |
| sku_ids[] | string | 否 | S01 |  |
| page | object | 是 |  |  |
| page.current_page | number | 是 | 1 | 当前页 |
| page.page_size | number | 是 | 20 | 页大小，最大2000 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.list | object | 是 |  |  |
| data.list.sku_id | string | 是 |  | 商品编码 |
| data.list.i_id | string | 是 |  | 款式编码 |
| data.list.boms | array | 是 |  | 主料BOM信息 |
| data.list.boms[] | object | 否 |  |  |
| data.list.boms[].sku_id | number | 是 |  | 主料商品编码 |
| data.list.boms[].outer_sku_id | string | 是 |  | 关联ERP内部主料商品编码 |
| data.list.boms[].name | string | 是 |  | 商品名称 |
| data.list.boms[].map_sku_id | number | 是 |  | 主料关联编码的autoid |
| data.list.boms[].map_outer_sku_id | string | 是 |  | 主料关联编码 |
| data.list.boms[].map_name | string | 是 |  | 主料名称 |
| data.list.boms[].properties_value | ['null', 'string'] | 是 |  | 规格属性 |
| data.list.boms[].map_properties_value | ['null', 'string'] | 是 |  | 关联规格属性 |
| data.list.boms[].pic | null | 是 |  | 图片地址 |
| data.list.boms[].rm_qty | number | 是 |  | 主料数量 |
| data.list.modifier_name | string | 是 |  | 主料修改人 |
| data.list.modified | string | 是 |  | 主料修改时间 |
| data.list.bom_minors | array | 是 |  | 辅料BOM信息 |
| data.list.bom_minors[] | object | 否 |  |  |
| data.list.bom_minors[].sku_id | number | 是 |  | 辅料商品编码 |
| data.list.bom_minors[].outer_sku_id | string | 是 |  | 关联ERP内部辅料商品编码 |
| data.list.bom_minors[].name | string | 是 |  | 商品名称 |
| data.list.bom_minors[].properties_value | ['string', 'null'] | 是 |  | 规格属性 |
| data.list.bom_minors[].qty | number | 是 |  | 数量 |
| data.page | object | 是 |  | 分页信息 |
| data.page.current_page | integer | 是 |  | 当前页 |
| data.page.page_size | integer | 是 |  | 页大小 |
| msg | null | 否 |  |  |
| request_id | null | 否 |  |  |

### 请求示例

```json
{
  "sku_ids": [],
  "modified_end": "2023-02-28",
  "page": {
    "current_page": 1,
    "page_size": 20
  },
  "modified_start": "2023-01-29"
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "page": {
      "current_page": 0,
      "page_size": 0
    },
    "list": {
      "i_id": "",
      "bom_minors": [
        {
          "outer_sku_id": "",
          "properties_value": "",
          "qty": 0,
          "name": "",
          "sku_id": 0
        }
      ],
      "sku_id": "",
      "boms": [
        {
          "outer_sku_id": "",
          "map_properties_value": "",
          "map_outer_sku_id": "",
          "properties_value": "",
          "map_name": "",
          "rm_qty": 0,
          "name": "",
          "sku_id": 0,
          "pic": "",
          "map_sku_id": 0
        }
      ]
    }
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 组合装商品上传（批量上传）

`/open/item/combinesku/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 组合装商品上传（批量上传） |
| 接口路径 | `/open/item/combinesku/upload` |
| docType / docId | 2 / 65 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=65 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/item/combinesku/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/item/combinesku/upload` |


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
| is_cover | boolean | 否 |  | 存在是否覆盖，默认值true，true:是,false:否 |
| is_null_cover | boolean | 否 |  | 空值是否覆盖，默认值false，true:是,false:否 |
| items | array | 是 |  | 一次最多上传50个 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | 20220527 | 商品编码 |
| items[].i_id | string | 否 | 20220527 | 商品款号 可更新 |
| items[].enty_sku_id | string | 否 |  | 实体编码 只能传普通商品资料已有的编码并且只能用于一个组合装商品中 |
| items[].name | string | 否 | XY999组合款1 | 商品名称 可更新 |
| items[].properties_value | string | 否 | 130 | 组合颜色及规格；可更新 |
| items[].brand | string | 否 |  | 品牌；可更新 |
| items[].cost_price | integer | 否 |  | 成本价；可更新 |
| items[].other_1 | string | 否 |  | 其它属性1；可更新 |
| items[].other_2 | string | 否 |  | 其它属性2；可更新 |
| items[].other_3 | string | 否 |  | 其它属性3；可更新 |
| items[].other_4 | string | 否 |  | 其它属性4；可更新 |
| items[].other_5 | string | 否 |  | 其它属性5；可更新 |
| items[].other_6 | string | 否 |  | 其它属性6；可更新 |
| items[].other_7 | string | 否 |  | 其它属性7；可更新 |
| items[].other_8 | string | 否 |  | 其它属性8；可更新 |
| items[].other_9 | string | 否 |  | 其它属性9；可更新 |
| items[].other_10 | string | 否 |  | 其它属性10；可更新 |
| items[].other_price_1 | number | 否 |  | 其它价格1；可更新 |
| items[].other_price_2 | number | 否 |  | 其它价格2；可更新 |
| items[].other_price_3 | number | 否 |  | 其它价格3；可更新 |
| items[].other_price_4 | number | 否 |  | 其它价格4；可更新 |
| items[].other_price_5 | number | 否 |  | 其它价格5；可更新 |
| items[].market_price | integer | 否 |  | 市场\|吊牌价；可更新 |
| items[].purchase_price | integer | 否 |  | 采购价；可更新 |
| items[].pic | string | 否 |  | 图片 可更新 |
| items[].short_name | string | 否 |  | 简称；可更新 |
| items[].remark | string | 否 |  | 备注；可更新 |
| items[].compose_sale_price | integer | 否 |  | 组合基本售价：可更新 |
| items[].enabled | string | 否 | 启用 | 是否启用，支持传“启用”，“备用”，“禁用”，不传该字段默认启用；可更新 |
| items[]. childList | array | 是 |  |  |
| items[]. childList[] | object | 否 |  |  |
| items[]. childList[].src_sku_id | string | 是 | 123 | 商品编码 可更新 |
| items[]. childList[].qty | integer | 是 |  | 数量；可更新 |
| items[]. childList[].sale_price | number | 是 |  | 应占售价；可更新 |
| items[].deleteLabels | string | 否 |  | 移除标签；多个标签逗号间隔 |
| items[].labels | string | 否 |  | 多标签，逗号分隔，最长200字符，仅可追加系统维护的标签，部分特定标签如奇门WMS,每日加权等标签不可追加 |
| is_add_labels | string | 否 |  | 是否追加标签；true追加，false全覆盖 |
| is_update_enty_sku_from_combine_sku | boolean | 否 |  | 按组合装信息更新实体编码信息，默认false,更新基本售价、成本价、体积、重量、其它价格1-5 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 | 0 | 错误码，0代表成功 |
| data | object | 是 |  |  |
| msg | string | 是 | "执行成功" | 执行描述 |

### 请求示例

```json
{
  "is_null_cover": true,
  "is_cover": true,
  "items": [
    {
      "i_id": "20220527",
      "sku_id": "20220527",
      "remark": "",
      "childList": [
        {
          "qty": 0,
          "src_sku_id": "123",
          "sale_price": 0
        }
      ],
      "pic": "",
      "enabled": "启用",
      "labels": "",
      "properties_value": "130",
      "name": "XY999组合款1",
      "short_name": "",
      "is_add_labels": true,
      "brand": "",
      "cost_price": 0
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {}
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

## 普通商品资料查询（按sku查询）

`/open/sku/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 普通商品资料查询（按sku查询） |
| 接口路径 | `/open/sku/query` |
| docType / docId | 2 / 14 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=14 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/sku/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/sku/query` |


### 接口说明

系统相关界面：【商品】------【普通商品资料】
根据时间升序输出

 Q:如何获取 全量的 商品资料?
 A:入参提示的时间间隔不能超过七天指的是 一次请求最大时间范围7天，不是只能查最近7天的数据，需要获取全部数据循环多次获取，尽量缩小时间查询范围为一小时，时间范围越小性能越高
 更多普通商品api相关问题参见常见问题文档： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=15&currentPage=1&pageSize=20

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
| page_size | integer | 否 | 10 | 每页多少条，默认30，最大100 |
| modified_begin | string | 否 | 2021-12-01 18:34:13 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与商品编码不能同时为空；一次请求最大时间范围7天（需要获取全部数据循环多次获取，尽量缩小时间查询范围为一小时，时间范围越小性能越高） |
| modified_end | string | 否 | 2021-12-08 18:34:13 | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与商品编码不能同时为空 |
| sku_ids | string | 否 | D0005J15101,D0005J20101 | 商品编码 与修改时间不能同时为空，最多20 |
| exactly_name | string | 否 |  A01 | 商品名称 与修改时间不能同时为空，仅支持传一个名称（精确搜索） |
| name | string | 否 |  | 商品名称 与修改时间不能同时为空，仅支持传一个名称（模糊查询） |
| brand | array | 否 |  | 品牌（name，modified_begin，modified_end，sku_ids，i_ids，vc_name，category，brand，sku_codes 效验查询条件以上不能同时为空） |
| brand[] | string | 否 |  |  |
| i_ids | array | 否 |  | 款式编码 |
| i_ids[] | string | 否 |  |  |
| date_field | string | 否 |  | 可传created,modified。默认按照modified查询 |
| flds | string | 否 |  | 可传：purchase_price 采购价，pics 多图，多个字段用逗号分开（自定义查询字段,如果指定了字段只返回指定的字段，默认的字段不返回。如果需要默认字段也需要指定传入对应的字段查询） |
| sku_codes | string | 否 |  | 辅助码，与修改时间不能同时为空 |
| labels | array | 否 |  | 包含标签 |
| labels[] | string | 否 |  |  |
| not_labels | array | 否 |  | 排除标签 |
| not_labels[] | string | 否 |  |  |
| loadSkuBin | boolean | 否 |  | 是否查询库容信息 |

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
| data.datas[].sku_id | string | 否 | CU-6 | 商品编码 |
| data.datas[].i_id | string | 否 | CU-6 | 款式编码 |
| data.datas[].name | string | 否 | 安德玛男鞋 | 商品名称 |
| data.datas[].short_name | string | 否 | 1 | 商品简称 |
| data.datas[].sale_price | number | 否 | 259 | 销售价 |
| data.datas[].cost_price | number | 否 | 101 | 成本价 |
| data.datas[].properties_value | string | 否 | 26 | 颜色规格 |
| data.datas[].color | string | 否 |  | 颜色 |
| data.datas[].c_id | integer | 否 | 868247446 | 类目id |
| data.datas[].category | string | 否 | 金属类 | 分类 |
| data.datas[].pic_big | string | 否 |  | 大图地址 |
| data.datas[].pic | string | 否 |  | 图片地址 |
| data.datas[].enabled | integer | 否 | 1 | 是否启用，0：备用，1：启用，-1：禁用 |
| data.datas[].weight | number | 否 | 1.003 | 重量 |
| data.datas[].market_price | number | 否 | 0 | 市场价 |
| data.datas[].brand | string | 否 | GUGGI | 品牌 |
| data.datas[].supplier_id | number | 否 |  | 供应商编号；对应页面：供应商信息-供应商内部编码；接口：供应商查询https://openweb.jushuitan.com/dev-doc?docType=6&docId=29 |
| data.datas[].supplier_name | string | 否 |  | 供应商名称 |
| data.datas[].modified | string | 否 | 2021-06-0916:28:12 | 修改时间 |
| data.datas[].sku_code | string | 否 | 1 | 国标码 |
| data.datas[].supplier_sku_id | string | 否 | CU-6 | 供应商商品编码 |
| data.datas[].supplier_i_id | string | 否 | CU-6 | 供应商商品款号 |
| data.datas[].vc_name | string | 否 | 分类3 | 虚拟分类 |
| data.datas[].sku_type | string | 否 | normal | 商品类型 |
| data.datas[].creator | integer | 否 |  | 创建者 |
| data.datas[].created | string | 否 | 2019-12-0211:25:29 | 创建时间 |
| data.datas[].remark | string | 否 |  | 备注 |
| data.datas[].item_type | string | 否 | 成品 | 商品属性，成品，半成品，原材料，包材 |
| data.datas[].stock_disabled | integer | 否 | 0 | 是否禁止同步，0=启用同步，1=禁用同步，2=部分禁用 |
| data.datas[].unit | string | 否 | 一个 | 单位 |
| data.datas[].shelf_life | integer | 否 | 76949 | 保质期 |
| data.datas[].labels | string | 否 | 紫色标,红色标,绿色标,黄色标 | 商品标签，多个标签时以逗号分隔 |
| data.datas[].production_licence | string | 否 |  | 生产许可证 |
| data.datas[].l | number | 否 | 1 | 长 |
| data.datas[].w | number | 否 | 4 | 宽 |
| data.datas[].h | number | 否 | 6 | 高 |
| data.datas[].is_series_number | boolean | 否 |  | 是否开启序列号 |
| data.datas[].other_price_1 | number | 否 | 1.1 | 其他价格1 |
| data.datas[].other_price_2 | number | 否 | 1.2 | 其他价格2 |
| data.datas[].other_price_3 | number | 否 | 1.3 | 其他价格3 |
| data.datas[].other_price_4 | number | 否 | 1.4 | 其他价格4 |
| data.datas[].other_price_5 | number | 否 | 1.5 | 其他价格5 |
| data.datas[].other_1 | string | 否 | 0506-DWT短外套 | 其他属性1 |
| data.datas[].other_2 | string | 否 | 2.2 | 其他属性2 |
| data.datas[].other_3 | string | 否 | 2.3 | 其他属性3 |
| data.datas[].other_4 | string | 否 | 2.4 | 其他属性4 |
| data.datas[].other_5 | string | 否 | 2.5 | 其他属性5 |
| data.datas[].other_6 | string | 否 |  | 其他属性6 |
| data.datas[].other_7 | string | 否 |  | 其他属性7 |
| data.datas[].other_8 | string | 否 |  | 其他属性8 |
| data.datas[].other_9 | string | 否 |  | 其他属性9 |
| data.datas[].other_10 | string | 否 |  | 其他属性10 |
| data.datas[].stock_type | string | 否 |  | 链接同步状态 |
| data.datas[].sku_codes | string | 否 |  | 辅助码 |
| data.datas[].autoid | integer | 否 |  | 唯一id，系统自增id（若商品编码有被修改可以用此字段判断唯一） |
| data.datas[].batch_enabled | boolean | 否 |  | 是否开启生产批次开关 |
| data.datas[].bin | string | 否 |  | 主仓位，以下字段loadSkuBin传true返回 |
| data.datas[].other_bin | string | 否 |  | 补充仓位 |
| data.datas[].min_qty | number | 否 |  | 库容下限 |
| data.datas[].max_qty | number | 否 |  | 库容上限 |
| data.datas[].overflow_qty | number | 否 |  | 溢出数量 |
| data.datas[].pack_qty | number | 否 |  | 标准装箱数量(loadSkuBin=true返回) |
| data.datas[].pack_volume | number | 否 |  | 标准装箱体积(loadSkuBin=true返回) |

### 请求示例

```json
{
  "sku_ids": "D0005J15101,D0005J20101",
  "page_index": 1,
  "modified_begin": "2021-12-01 18:34:13",
  "modified_end": "2021-12-08 18:34:13",
  "page_size": 10
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
        "i_id": "CU-6",
        "supplier_i_id": "CU-6",
        "item_type": "成品",
        "pic": "",
        "modified": "2021-06-0916:28:12",
        "brand": "GUGGI",
        "vc_name": "分类3",
        "productionbatch_format": "",
        "created": "2019-12-0211:25:29",
        "weight": 1.003,
        "sku_id": "CU-6",
        "labels": "紫色标,红色标,绿色标,黄色标",
        "unit": "一个",
        "properties_value": "26",
        "stock_disabled": 0,
        "name": "安德玛男鞋",
        "market_price": 0,
        "short_name": "1",
        "supplier_id": "0",
        "sku_code": "1",
        "remark": "",
        "production_licence": "",
        "pic_big": "",
        "enabled": 1,
        "shelf_life": 76949,
        "c_id": 868247446,
        "supplier_name": "",
        "sku_codes": "",
        "cost_price": 101,
        "creator": 16600575,
        "other_price_5": 1.5,
        "sku_type": "normal",
        "h": 6,
        "other_5": "2.5",
        "other_4": "2.4",
        "other_3": "2.3",
        "l": 1,
        "other_2": "2.2",
        "sale_price": 259,
        "other_1": "0506-DWT短外套",
        "stock_type": "",
        "supplier_sku_id": "CU-6",
        "w": 4,
        "category": "金属类",
        "other_price_3": 1.3,
        "other_price_4": 1.4,
        "other_price_1": 1.1,
        "other_price_2": 1.2
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

## 普通商品查询（按款查询）

`/open/mall/item/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 普通商品查询（按款查询） |
| 接口路径 | `/open/mall/item/query` |
| docType / docId | 2 / 13 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=13 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/mall/item/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/mall/item/query` |


### 接口说明

系统相关界面：【商品】------【普通商品资料】------【按款显示】

 新版商品是否开启按款显示开关位置：【基础设置（推荐）】-->【是否开通按款显示】-->【是否开通按款显示】

 商品单款下总量超过1000个商品编码的不适用，需要切换到普通商品查询（按sku查询）的接口

 Q:如何获取 全量的 商品资料?
 A:入参提示的时间间隔不能超过七天指的是 一次请求最大时间范围7天，不是只能查最近7天的数据，需要获取全部数据循环多次获取，尽量缩小时间查询范围为一小时，时间范围越小性能越高
 更多普通商品api相关问题参见常见问题文档： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=15&currentPage=1&pageSize=20

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
| modified_begin | string | 否 | 2021-12-01 18:34:13 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与款式编码不能同时为空 |
| modified_end | string | 否 | 2021-12-07 18:34:13 | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与款式编码不能同时为空 |
| only_item | boolean | 否 |  | 是否只查询款式信息不返回商品明细 |
| i_ids | array | 否 |  | 款式编码 与修改时间不能同时为空，最多20 |
| i_ids[] | string | 否 |  |  |
| page_index | integer | 否 | 1 | 第几页，从第一页开始，默认1 |
| page_size | integer | 否 | 10 | 每页多少条，默认30，最大50 |
| item_flds | array | 否 |  | 查询款字段，用于查询指定需要的字段,传f_json可查询款式的多图 |
| item_flds[] | string | 否 | onsale,supplier_i_id | 款的商品状态是否启用(-1=禁用,0=备用,1=启用)，供应商款号 |
| itemsku_flds | array | 否 |  | 查询商品字段，用于查询指定需要的字段 |
| itemsku_flds[] | string | 否 |  |  |
| date_field | string | 否 |  | 可传created,modified。默认按照modified查询 |

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
| data.datas[].i_id | string | 否 | 001 | 款式编码 |
| data.datas[].co_id | integer | 否 | 11053062 | 公司编号 |
| data.datas[].name | string | 否 | 短袖 | 商品名称 |
| data.datas[].c_id | integer | 否 |  | 商品分类编号 |
| data.datas[].c_name | string | 否 |  | 商品分类名称 |
| data.datas[].s_price | number | 否 | 100.0 | 基本售价（款式） |
| data.datas[].c_price | number | 否 | 100.0 | 成本价(采购价) |
| data.datas[].remark | string | 否 |  | 商品备注 |
| data.datas[].pic | string | 否 |  | 图片地址 |
| data.datas[].created | string | 否 |  | 创建时间 |
| data.datas[].modified | string | 否 | 2021-08-10 19:58:18 | 修改时间 |
| data.datas[].brand | string | 否 | 鬼冢虎 | 品牌 |
| data.datas[].weight | number | 否 |  | 重量 |
| data.datas[].market_price | string | 否 |  | 市场\|吊牌价 |
| data.datas[].vc_name | string | 否 |  | 虚拟分类 |
| data.datas[].item_type | string | 否 | 成品 | 商品属性：成品/半成品/原材料 |
| data.datas[].l | number | 否 |  | 长 |
| data.datas[].w | number | 否 |  | 宽 |
| data.datas[].h | number | 否 |  | 高 |
| data.datas[].shelf_life | integer | 否 |  | 保质期(天） |
| data.datas[].skus | array | 否 |  | sku列表 |
| data.datas[].skus[] | object | 否 |  |  |
| data.datas[].skus[].co_id | integer | 否 | 11053062 | 公司编号 |
| data.datas[].skus[].sku_id | string | 否 | A001 | 商品编码 |
| data.datas[].skus[].i_id | string | 否 | 001 | 款式编码 |
| data.datas[].skus[].name | string | 否 | 短袖 | 商品名称 |
| data.datas[].skus[].c_id | integer | 否 |  | 商品分类编号 |
| data.datas[].skus[].brand | string | 否 | 鬼冢虎 | 品牌 |
| data.datas[].skus[].market_price | number | 否 |  | 市场\|吊牌价 |
| data.datas[].skus[].sale_price | number | 否 | 100.0 | 基本售价 |
| data.datas[].skus[].cost_price | number | 否 | 100.0 | 成本价 |
| data.datas[].skus[].enabled | integer | 否 | 1 | 是否启用，默认值1,可选值:-1=禁用,0=备用,1=启用 |
| data.datas[].skus[].category | string | 否 |  | 分类 |
| data.datas[].skus[].creator | string | 否 | 0 | 创建人编号 |
| data.datas[].skus[].modifier | string | 否 | 12854967 | 修改人编号 |
| data.datas[].skus[].creator_name | string | 否 | @open-236 | 创建人名称 |
| data.datas[].skus[].modifier_name | string | 否 | 川梣 | 修改人名称 |
| data.datas[].skus[].properties_value | string | 否 |  | 颜色及规格 |
| data.datas[].skus[].sku_code | string | 否 |  | 国际码 |
| data.datas[].skus[].purchase_price | integer | 否 |  | 采购价 |
| data.datas[].skus[].pic | string | 否 |  | 图片地址 |
| data.datas[].skus[].pic_big | string | 否 |  | 大图地址 |
| data.datas[].skus[].weight | number | 否 |  | 重量 |
| data.datas[].skus[].short_name | string | 否 |  | 简称 |
| data.datas[].skus[].item_type | string | 否 | 成品 | 商品属性，可选值["成品","半成品","原材料","包材"] |
| data.datas[].skus[].supplier_id | integer | 否 |  | 供应商编码 |
| data.datas[].skus[].supplier_name | string | 否 |  | 供应商名称 |
| data.datas[].skus[].supplier_sku_id | string | 否 |  | 供应商商品编码 |
| data.datas[].skus[].supplier_i_id | string | 否 |  | 供应商款式编码 |
| data.datas[].skus[].remark | string | 否 |  | 商品备注 |
| data.datas[].skus[].vc_name | string | 否 |  | 虚拟分类 |
| data.datas[].skus[].l | number | 否 |  | 长 |
| data.datas[].skus[].w | number | 否 |  | 宽 |
| data.datas[].skus[].h | number | 否 |  | 高 |
| data.datas[].skus[].other_price_1 | number | 否 |  | 其它价格1 |
| data.datas[].skus[].other_price_2 | number | 否 |  | 其它价格2 |
| data.datas[].skus[].other_price_3 | number | 否 |  | 其它价格3 |
| data.datas[].skus[].other_price_4 | number | 否 |  | 其它价格4 |
| data.datas[].skus[].other_price_5 | number | 否 |  | 其它价格5 |
| data.datas[].skus[].labels | string | 否 |  | 商品标签 |
| data.datas[].skus[].other_1 | string | 否 |  | 其它属性1 |
| data.datas[].skus[].other_2 | string | 否 |  | 其它属性2 |
| data.datas[].skus[].other_3 | string | 否 |  | 其它属性3 |
| data.datas[].skus[].other_4 | string | 否 |  | 其它属性4 |
| data.datas[].skus[].other_5 | string | 否 |  | 其它属性5 |
| data.datas[].skus[].unit | string | 否 |  | 单位 |
| data.datas[].skus[].shelf_life | string | 否 |  | 保质期 |
| data.datas[].skus[].productionbatch_format | string | 否 |  | 生产批次信息 |
| data.datas[].skus[].production_licence | string | 否 |  | 生产许可证 |
| data.datas[].skus[].drp_co_id_to | integer | 否 |  | 供销商编号 |
| data.datas[].ups | array | 否 |  | 商品属性集合，对应款式明细里面的类目属性 |
| data.datas[].ups[] | object | 否 |  |  |
| data.datas[].ups[].p_id | integer | 否 |  | 属性编号 |
| data.datas[].ups[].p_name | string | 否 | 年份、安全等级等自定义属性名 | 属性列名 |
| data.datas[].ups[].pv_id | integer | 否 |  | 属性值编号 |
| data.datas[].ups[].pv_value | string | 否 |  | 属性值名称 |
| data.datas[].productionbatch_format | string | 否 |  | 生产批次信息 |
| data.datas[].production_licence | string | 否 |  | 生产许可证 |
| data.datas[].unit | string | 否 |  | 单位 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
|  | ups节点接口查询和页面显示的  少数据 |  |


### 请求示例

```json
{
  "only_item": true,
  "itemsku_flds": [],
  "i_ids": [],
  "page_index": 1,
  "modified_begin": "2021-12-01 18:34:13",
  "modified_end": "2021-12-07 18:34:13",
  "item_flds": [],
  "page_size": 10,
  "date_field": ""
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
        "i_id": "001",
        "vc_name": "",
        "unit": "盒",
        "skus": [
          {
            "i_id": "001",
            "modifier_name": "川梣",
            "supplier_i_id": "",
            "item_type": "成品",
            "modifier": "12854967",
            "remark": "",
            "production_licence": "",
            "pic": "",
            "pic_big": "",
            "enabled": 1,
            "shelf_life": "",
            "c_id": 0,
            "supplier_name": "",
            "brand": "鬼冢虎",
            "cost_price": 100.0,
            "vc_name": "",
            "creator": "0",
            "other_price_5": 0,
            "productionbatch_format": "",
            "co_id": 11053062,
            "h": 0,
            "weight": 0,
            "other_5": "",
            "sku_id": "A001",
            "other_4": "",
            "other_3": "",
            "l": 0,
            "other_2": "",
            "sale_price": 100.0,
            "other_1": "",
            "labels": "",
            "supplier_sku_id": "",
            "properties_value": "",
            "w": 0,
            "name": "短袖",
            "market_price": 0,
            "creator_name": "@open-236",
            "short_name": "",
            "category": "",
            "other_price_3": 0,
            "sku_code": "",
            "supplier_id": 0,
            "other_price_4": 0,
            "other_price_1": 0,
            "other_price_2": 0
          }
        ],
        "productionbatch_format": "",
        "item_type": "成品",
        "co_id": 11053062,
        "h": 0,
        "c_price": 100.0,
        "weight": 0,
        "remark": "",
        "production_licence": "",
        "pic": "",
        "l": 0,
        "shelf_life": 0,
        "s_price": 100.0,
        "w": 0,
        "name": "短袖",
        "c_id": 0,
        "created": "2021-08-10 15:51:49.917",
        "modified": "2021-08-10 19:58:18",
        "market_price": "",
        "ups": [
          {
            "pv_value": "",
            "pv_id": 0,
            "p_name": "",
            "p_id": 0
          }
        ],
        "c_name": "",
        "brand": "鬼冢虎"
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

## 商品类目查询

`/open/category/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 商品类目查询 |
| 接口路径 | `/open/category/query` |
| docType / docId | 2 / 12 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=12 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/category/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/category/query` |


### 接口说明

系统相关界面：【商品】----商品操作----【商品类目管理】

 自2020年1月开始，开放平台接口将逐步调整为只接收HTTPS请求

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
| modified_begin | string | 否 | 2020-01-1218:34:13 | 修改开始时间 |
| modified_end | string | 否 | 2020-01-1418:34:13 | 修改结束时间 |
| page_index | integer | 否 | 1 | 第几页 |
| page_size | integer | 否 | 10 | 每页记录数 |
| c_ids | array | 否 |  | 类目id集合 |
| c_ids[] | string | 否 |  |  |
| parent_c_ids | array | 否 |  | 父级类目id集合 |
| parent_c_ids[] | string | 否 |  |  |

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
| data.datas[].c_id | integer | 否 | 1461557367 | 类目id |
| data.datas[].parent_c_id | integer | 否 | 50384002 | 父级类目id |
| data.datas[].modified | string | 否 | 2018-08-0214:19:08 | 修改时间 |
| data.datas[].name | string | 否 | 111 | 类目名称 |

### 请求示例

```json
{
  "c_ids": [],
  "parent_c_ids": [],
  "page_index": 1,
  "modified_begin": "2020-01-1218:34:13",
  "modified_end": "2020-01-1418:34:13",
  "page_size": 10
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
        "parent_c_id": 50384002,
        "name": "111",
        "c_id": 1461557367,
        "modified": "2018-08-0214:19:08"
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

## 组合装商品查询

`/open/combine/sku/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 组合装商品查询 |
| 接口路径 | `/open/combine/sku/query` |
| docType / docId | 2 / 11 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=11 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/combine/sku/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/combine/sku/query` |


### 接口说明

系统相关界面：【商品】------【组合装商品及库存】 组合装没有实际库存，库存是通过子商品库存计算得到的最多可组装数
 此接口不返回禁用和备用的组合装商品

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
| modified_begin | string | 否 | 2021-12-01 13:58:41 | 修改起始时间,起始时间和结束时间必须同时存在，时间间隔不能超过七天 |
| modified_end | string | 否 | 2021-12-08 13:58:41 | 修改结束时间,起始时间和结束时间必须同时存在，时间间隔不能超过七天 |
| sku_ids | string | 否 | 557,4587553344807 | 组合装商品编码 与修改时间不能同时为空，最多20 |
| i_ids | array | 否 |  | 组合装款式编码 |
| i_ids[] | string | 否 |  |  |
| combine_itemsku_flds | array | 否 |  | 自定义返回参数数组（自定义查询字段,如果指定了字段只返回指定的字段，默认的字段不返回。如果需要默认字段也需要指定传入对应的字段查询） |
| combine_itemsku_flds[] | string | 否 | enty_sku_id,category | 实体编码,商品分类 |

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
| data.datas[].i_id | string | 否 | m04 | 组合装款式编码 |
| data.datas[].name | string | 否 | 短袖 | 组合装商品名称 |
| data.datas[].short_name | string | 否 |  | 组合装简称 |
| data.datas[].vc_name | string | 否 |  | 虚拟分类 |
| data.datas[].pic | string | 否 | https://img.dianjia.io/vpc/10010/576102910618767361/JE3003DSM_33.jpg | 图片地址 |
| data.datas[].properties_value | string | 否 | 紫色;XXL | 组合装颜色及规格 |
| data.datas[].sale_price | number | 否 | 15.0 | 组合装售价 |
| data.datas[].weight | number | 否 | 1.52 | 组合装重量 |
| data.datas[].sku_id | string | 否 | 0016 | 组合装商品编码 |
| data.datas[].modified | string | 否 | 2021-11-0816:05:05 | 修改时间 |
| data.datas[].created | string | 否 | 2021-10-2115:27:52 | 创建时间 |
| data.datas[].enty_sku_id | string | 否 |  | 组合商品实体编码 |
| data.datas[].labels | string | 否 |  | 标签 |
| data.datas[].brand | string | 否 |  | 品牌 |
| data.datas[].cost_price | number | 否 | 100.0 | 组合装商品成本价 |
| data.datas[].enabled | number | 否 |  | 是否启用 1表示启用；0表示备用；-1表示禁用 |
| data.datas[].sku_code | string | 否 |  | 国标码 |
| data.datas[].other_price_1 | number | 否 |  | 其它价格1 |
| data.datas[].other_price_2 | number | 否 |  | 其它价格2 |
| data.datas[].other_price_3 | number | 否 |  | 其它价格3 |
| data.datas[].other_price_4 | number | 否 |  | 其它价格4 |
| data.datas[].other_price_5 | number | 否 |  | 其它价格5 |
| data.datas[].other_1 | string | 否 |  | 其它属性1 |
| data.datas[].other_2 | string | 否 |  | 其它属性2 |
| data.datas[].other_3 | string | 否 |  | 其它属性3 |
| data.datas[].other_4 | string | 否 |  | 其它属性4 |
| data.datas[].other_5 | string | 否 |  | 其它属性5 |
| data.datas[].l | number | 否 |  | 长 |
| data.datas[].w | number | 否 |  | 宽 |
| data.datas[].h | number | 否 |  | 高 |
| data.datas[].volume | number | 否 |  | 体积 |
| data.datas[].item_type | string | 否 |  | 商品属性 |
| data.datas[].remark | string | 否 |  | 备注 |
| data.datas[].sku_qty | integer | 否 |  | 子商品数量 |
| data.datas[].items | array | 否 |  | 商品列表 |
| data.datas[].items[] | object | 否 |  |  |
| data.datas[].items[].src_sku_id | string | 否 | 00moli001403L | 子商品编码 |
| data.datas[].items[].qty | integer | 否 | 1 | 子商品数量 |
| data.datas[].items[].sale_price | number | 否 | 5.0 | 应占售价 |
| data.datas[].items[].modified | string | 否 | 2021-11-0816:04:48 | 修改时间 |
| data.datas[].items[].combine_sku_id | string | 否 | 0016 | 组合装商品编码 |

### 请求示例

```json
{
  "page_index": 1,
  "page_size": 30,
  "sku_ids": "1122",
  "combine_itemsku_flds": [
    "sku_code",
    "other_price_1",
    "other_price_2",
    "other_price_3",
    "other_price_4",
    "other_price_5",
    "other_1",
    "other_2",
    "other_3",
    "other_4",
    "other_5",
    "l",
    "w",
    "h",
    "volume",
    "item_type",
    "remark",
    "name",
    "short_name",
    "vc_name",
    "pic",
    "properties_value",
    "sale_price",
    "weight",
    "modified",
    "created",
    "enty_sku_id",
    "labels",
    "brand",
    "cost_price",
    "enabled"
  ]
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
        "i_id": "TZ-2-QZ-2599",
        "vc_name": null,
        "created": "2022-12-29 16:45:32",
        "weight": 1.52,
        "sku_id": "1122",
        "pic": "",
        "sale_price": "",
        "enabled": 1,
        "enty_sku_id": null,
        "labels": "指定组合装成本价",
        "properties_value": "浅蓝色;2XL,深蓝色;2XL",
        "sku_qty": 2,
        "name": "QZ-两件-休闲裤-1XT-3352-浅蓝色-1XT-3352-深蓝色-2XL",
        "modified": "2026-08-11 18:04:55",
        "short_name": null,
        "brand": null,
        "items": [
          {
            "qty": 1,
            "combine_sku_id": "1122",
            "modified": "2026-08-11 18:04:55",
            "src_sku_id": "123456",
            "sale_price": 0
          },
          {
            "qty": 1,
            "combine_sku_id": "1122",
            "modified": "2026-08-11 18:04:55",
            "src_sku_id": "1234567",
            "sale_price": 0
          }
        ],
        "cost_price": ""
      }
    ],
    "requestId": null,
    "page_index": 1,
    "has_next": false,
    "data_count": 1,
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

## 店铺商品资料查询

`/open/skumap/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 店铺商品资料查询 |
| 接口路径 | `/open/skumap/query` |
| docType / docId | 2 / 10 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=10 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/skumap/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/skumap/query` |


### 接口说明

系统相关界面：【商品】------【店铺商品资料】
 此接口查询不到淘系和拼多多店铺商品信息
 淘系通过奇门获取 https://open.jushuitan.com/document.aspx?doc_id=2365 ，拼多多自行对接平台获取
 淘系平台包含： 淘宝天猫，天猫供销，考拉pop，考拉供应商直发，阿里巴巴，淘工厂，天猫超市，天猫国际直营，阿里健康直营，淘宝定制，淘宝采购，淘宝买菜，银泰喵街

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
| modified_begin | string | 否 | 2021-12-01 13:58:41 | 修改起始时间，和结束时间必须同时存在，时间间隔不能超过七天，与商品编码不能同时为空 |
| modified_end | string | 否 | 2021-12-08 13:58:41 | 修改结束时间，和起始时间必须同时存在，时间间隔不能超过七天，与商品编码不能同时为空 |
| link_modified_begin  | string | 否 | 2021-12-01 13:58:41 | 商品对应关系修改起始时间 |
| link_modified_end | string | 否 | 2021-12-01 13:58:41 | 商品对应关系修改结束时间 |
| sku_ids | string | 否 | lyyi001,lyyi002 | 商品编码 （线上商品编码），与修改时间不能同时为空，最多20 |
| shop_id | integer | 否 | 10208692 | 店铺编号 |
| created_begin | string | 否 |  | 创建开始时间，与结束时间不能同时为空 |
| created_end | string | 否 |  | 创建结束时间，和开始时间不能同时为空 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  | 联合主键：shop_id, shop_i_id, shop_sku_id |
| data.page_size | integer | 否 | 2 | 每页多少条 |
| data.page_index | integer | 否 | 1 | 第几页 |
| data.data_count | integer | 否 | 2 | 总条数 |
| data.page_count | integer | 否 | 1 | 总页数 |
| data.has_next | boolean | 否 | false | 是否有下一页 |
| data.datas | array | 否 |  | 数据集合 |
| data.datas[] | object | 否 |  |  |
| data.datas[].co_id | integer | 否 | 10373050 | 公司编号 |
| data.datas[].shop_id | integer | 否 | 11888088 | 店铺编号 |
| data.datas[].channel | string | 否 | Self | 来源平台：https://jushuitan.yuque.com/docs/share/d34de6aa-9613-4bc3-8a6e-12b20523925f?# 《channel 来源平台 枚举值》密码：tyuy |
| data.datas[].i_id | string | 否 |  | 款式编码（线上款式编码） |
| data.datas[].sku_id | string | 否 |  | 商品编码（线上商品编码） |
| data.datas[].shop_i_id | string | 否 |  | 店铺款式编码（平台店铺款式编码/商品ID） |
| data.datas[].shop_sku_id | string | 否 |  | 店铺商品编码（平台店铺商品编码） |
| data.datas[].modified | string | 否 | 2021-11-0802:03:34 | 修改时间 |
| data.datas[].link_modified | string | 否 | 2021-11-0802:03:34 | 商品对应关系修改时间 |
| data.datas[].enabled | boolean | 否 | true | 是否上架 |
| data.datas[].c_id | integer | 否 | 10001683 | 类目编码（类目ID） |
| data.datas[].raw_sku_id | string | 否 |  | 原始商品编码（未经系统处理的线上商品编码原值） |
| data.datas[].shop_price | string | 否 |  | 平台价格（店铺售价）,系统中需开启相关配置 |
| data.datas[].name | string | 否 |  | 平台商品名称（线上商品名称） |
| data.datas[].properties_value | string | 否 |  | 线上颜色规格 |
| data.datas[].pic | string | 否 |  | 款式图片 |
| data.datas[].created | string | 否 |  | 创建时间 |
| data.datas[].shop_created | string | 否 |  | 平台创建时间 |
| data.datas[].pull_off_time | string | 否 |  | 下架时间 |
| data.datas[].outer_sku_code | string | 否 |  | 线上国标码 |
| data.datas[].type | integer | 否 |  | 链接同步设置，0:开启同步,2:禁止同步,3:商品对应关系禁止同步,254:锁定后禁止,255:锁定后禁止 |
| data.datas[].shop_qty | number | 否 |  | 店铺库存 |
| data.datas[].link_sku_id | string | 否 |  | 对应商品编码（商品对应关系页面） |
| data.datas[].sale_price_min | integer | 否 |  | 售价下限 |
| data.datas[].sale_price_max | integer | 否 |  | 售价上限 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 170 | "msg":"公司绑定验证失败6!" |  |


### 请求示例

```json
{
  "shop_id": 10208692,
  "sku_ids": "lyyi001,lyyi002",
  "page_index": 1,
  "modified_begin": "2021-12-01 13:58:41",
  "modified_end": "2021-12-08 13:58:41",
  "page_size": 30
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
        "i_id": "",
        "raw_sku_id": "",
        "outer_sku_code": "",
        "shop_price": "",
        "created": "",
        "co_id": 10373050,
        "channel": "Self",
        "sku_id": "",
        "pull_off_time": "",
        "link_sku_id": "",
        "pic": "",
        "shop_i_id": "",
        "type": 0,
        "enabled": true,
        "shop_sku_id": "",
        "shop_id": 11888088,
        "properties_value": "",
        "name": "",
        "modified": "2021-11-0802:03:34",
        "c_id": 10001683,
        "shop_qty": 0
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

## 店铺商品资料上传

`/open/jushuitan/skumap/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 店铺商品资料上传 |
| 接口路径 | `/open/jushuitan/skumap/upload` |
| docType / docId | 2 / 5 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=2&docId=5 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/skumap/upload` |
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/skumap/upload` |


### 接口说明

系统相关界面：【商品】------【店铺商品资料】

 数据流向：外部系统->聚水潭ERP

 Q：接口一次最大可以上传多少个商品
 A：接口每次请求最大50

 Q: 错误返回“店铺编号[xxx]的站点类型不是自有商城，无法上传”
 A:  在【店铺设置】里新增店铺，站点选择“商家自有商城”，关于【商家自有商城】的店铺如何创建，可查看操作： http://www.erp321.com/app/support/document.html#page=1865

 Q：为什么需要对接这个接口，有什么用处
 A：该接口主要用途为创建【店铺商品资料】信息，可以理解为商品链接，主要功能用于商品库存推送，即该接口实现的业务： https://open.jushuitan.com/document/1017.html

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
| items | array | 否 |  | 商品列表 |
| items[] | object | 否 |  |  |
| items[].sku_id | string | 是 | S01 | 商品编码 可更新（线上商品编码） |
| items[].i_id | string | 否 | I01 | 款式编码 可更新（线上款式编码） |
| items[].sku_code | string | 否 | 135489 | 国标码 可更新 |
| items[].shop_i_id | string | 是 | I01 | 店铺商品款式 （平台店铺款式编码） |
| items[].shop_sku_id | string | 是 | S01 | 店铺商品编码 （平台店铺商品编码）nvarchar(200) |
| items[].original_sku_id | string | 否 | O01 | 原始商品编码 可更新 |
| items[].shop_sku_pic | string | 否 |  | 店铺商品图片（不超过 300 字节）,可更新 |
| items[].name | string | 否 | 耳机 | 商品名称，可更新 |
| items[].shop_properties_value | string | 否 | 蓝色;XL | 店铺颜色规格，可更新（线上颜色规格） |
| items[].sku_sign | string | 否 | "" | 商品标识(线上商品的特殊属性，比如零售，阶梯)，可更新，可为空字符串 |
| items[].shop_id | integer | 是 | 10192724 | 店铺编号 |
| items[].shop_sku_url | string | 否 |  | 线上链接 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| data | object | 否 |  |  |
| msg | string | 否 | 执行成功 | 错误描述 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 170 | 店铺编号[123] 不是公司[456]的店铺 |  |


### 请求示例

```json
{
  "items": [
    {
      "i_id": "I01",
      "shop_id": 10192724,
      "original_sku_id": "O01",
      "shop_properties_value": "蓝色;XL",
      "sku_sign": "",
      "name": "耳机",
      "sku_id": "S01",
      "shop_i_id": "I01",
      "sku_code": "135489",
      "shop_sku_id": "S01"
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "执行成功",
  "code": 0,
  "data": {}
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
