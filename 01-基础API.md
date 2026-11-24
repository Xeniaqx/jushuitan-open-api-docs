# 聚水潭开放平台 · 基础API（线下版）

> 抓取日期：2026-11-23  
> 分类：基础API（docType=1）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=1&docId=1

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 店铺查询 | `/open/shops/query` | 1 | [打开](https://openweb.jushuitan.com/dev-doc?docType=1&docId=1) |
| 物流公司查询 | `/open/logisticscompany/query` | 2 | [打开](https://openweb.jushuitan.com/dev-doc?docType=1&docId=2) |
| 仓库查询 | `/open/wms/partner/query` | 3 | [打开](https://openweb.jushuitan.com/dev-doc?docType=1&docId=3) |
| 商家用户信息 | `/open/webapi/userapi/company/getcompanyusers` | 611 | [打开](https://openweb.jushuitan.com/dev-doc?docType=1&docId=611) |
| 查询我的供应商列表（新） | `/open/api/drp/inneropen/partner/channel/querymysupplier` | 862 | [打开](https://openweb.jushuitan.com/dev-doc?docType=1&docId=862) |
| 分销商查询 | `/open/api/drp/inneropen/partner/supplier/querymychannel` | 955 | [打开](https://openweb.jushuitan.com/dev-doc?docType=1&docId=955) |

## 目录

- [店铺查询](#店铺查询)
- [物流公司查询](#物流公司查询)
- [仓库查询](#仓库查询)
- [商家用户信息](#商家用户信息)
- [查询我的供应商列表（新）](#查询我的供应商列表新)
- [分销商查询](#分销商查询)

---

## 店铺查询

`/open/shops/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 店铺查询 |
| 接口路径 | `/open/shops/query` |
| docType / docId | 1 / 1 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=1&docId=1 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/shops/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/shops/query` |


### 接口说明

系统相关界面：【设置】----业务设置----【店铺设置】

 Q：为什么接口返回的条数和ERP界面中的数据量不一样
 A：接口仅返回ERP中已启用的店铺，未启用的不返回

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
| page_index | integer | 否 | 1 | 第几页，默认第一页 |
| page_size | integer | 否 | 10 | 每页多少条；默认100条，最大100条 |
| shop_ids | array | 否 |  | 店铺编码 |
| shop_ids[] | integer | 否 | 12343451,17138865 | 店铺编号 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 是 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  |  |
| data.page_index | integer | 是 | 1 | 第几页 |
| data.page_size | integer | 是 | 100 | 每页多少条 |
| data.has_next | boolean | 否 | true | 是否有下一页 |
| data.datas | array | 否 |  | 店铺列表 |
| data.datas[] | object | 否 |  |  |
| data.datas[].shop_id | integer | 否 | 10178845 | 店铺编号 |
| data.datas[].shop_name | string | 否 | HIDZMY | 店铺名称 |
| data.datas[].co_id | integer | 否 | 12252 | 公司编号 |
| data.datas[].shop_site | string | 否 | 商家自有商城 | 店铺站点（https://openweb.jushuitan.com/doc?docId=338） |
| data.datas[].shop_url | string | 否 |  | 店铺网址 |
| data.datas[].created | string | 否 |  | 创建时间 |
| data.datas[].nick | string | 否 | 5084 | 授权账号 |
| data.datas[].session_expired | string | 否 |  | 授权过期时间 |
| data.datas[].session_uid | string | 否 |  | 会话用户编号 |
| data.datas[].short_name | string | 否 |  | 店铺简称 |
| data.datas[].group_id | number | 否 |  | 分组id |
| data.datas[].group_name | string | 否 |  | 分组名称 |
| data.datas[].session_status | number | 否 |  | 授权状态（0未授权 1已过期 2已授权 3无需授权） |
| data.datas[].platform_shop_name | string | 否 |  | 平台店铺名称 |

### 错误码

| 错误码 | 错误信息 | 排查方法 |
|---|---|---|
| 140 | 验证失败！如果biz参数值存在中文需要采用UTF-8进行URL编码 |  |


### 请求示例

```json
{
  "page_index": 1,
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
        "nick": "5084",
        "shop_id": 10178845,
        "session_expired": "",
        "shop_url": "",
        "created": "",
        "co_id": 12252,
        "session_uid": "",
        "short_name": "",
        "shop_site": "商家自有商城",
        "shop_name": "HIDZMY"
      }
    ],
    "page_index": 1,
    "has_next": true,
    "page_size": 100
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

## 物流公司查询

`/open/logisticscompany/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 物流公司查询 |
| 接口路径 | `/open/logisticscompany/query` |
| docType / docId | 1 / 2 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=1&docId=2 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/logisticscompany/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/logisticscompany/query` |


### 接口说明

系统相关界面：【设置】------【物流(快递)公司及打印模板】

 Q：接口中返回的数据与ERP界面中维护的数据不一致
 A：接口默认返回ERP已对接的全部快递公司，当入参中传入正确的wms_co_id时，接口会返回对应查询商家已经接入且已生效的快递公司

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
| page_index | integer | 否 | 1 | 第几页，默认第一页开始 |
| page_size | integer | 否 | 10 | 每页多少条，默认30条，最大50条 |
| modified_begin | string | 否 | 2021-1-18 00:00:00 | 修改起始时间 |
| modified_end | string | 否 | 2021-1-21 00:00:00 | 修改结束时间 |
| wms_co_id | integer | 否 | 12252 | 公司编号，该值存在时查询对应公司或分仓下的启用的物流公司信息，否则查询系统内所有的物流公司信息 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 是 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  |  |
| data.page_index | integer | 是 | 1 | 第几页 |
| data.page_size | integer | 是 | 2 | 每页多少条 |
| data.has_next | boolean | 否 | false | 是否有下一页 |
| data.data_count | integer | 否 | 2 | 总条数 |
| data.page_count | integer | 否 | 1 | 总页数 |
| data.datas | array | 否 |  | 店铺列表 |
| data.datas[] | object | 否 |  |  |
| data.datas[].lc_id | string | 否 | KDKY | 快递公司编码 ERP唯一 |
| data.datas[].lc_name | string | 否 | 百世快递 | 快递公司 |
| data.datas[].modified | string | 否 | 2021-01-2016:56:19 | 修改时间 |

### 请求示例

```json
{
  "wms_co_id": 12252,
  "page_index": 1,
  "modified_begin": "2021-1-1800:00:00",
  "modified_end": "2021-1-2100:00:00",
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
        "lc_id": "KDKY",
        "modified": "2021-01-2016:56:19",
        "lc_name": "百世快递"
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

## 仓库查询

`/open/wms/partner/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 仓库查询 |
| 接口路径 | `/open/wms/partner/query` |
| docType / docId | 1 / 3 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=1&docId=3 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 正式环境 | `https://openapi.jushuitan.com/open/wms/partner/query` |
| 测试环境 | `https://dev-api.jushuitan.com/open/wms/partner/query` |


### 接口说明

系统相关界面：【库存】------【我的分仓（第三方物流）】------分仓+三方仓类别

 Q：为什么接口返回的条数和ERP界面中的数据量不一样
 A：接口仅返回ERP中已生效的仓库，作废的不返回

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
| page_index | integer | 否 |  | 第几页，默认第一页开始 |
| page_size | integer | 否 |  | 每页多少条，非必填项，默认30条 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | integer | 否 | 0 | 错误码 |
| msg | string | 否 | 执行成功 | 错误描述 |
| data | object | 否 |  |  |
| data.data_count | integer | 否 | 2 | 总条数 |
| data.page_count | integer | 否 | 1 | 总页数 |
| data.has_next | boolean | 否 | false | 是否有下一页 |
| data.page_index | integer | 否 | 1 | 第几页 |
| data.page_size | integer | 否 | 2 | 每页多少条 |
| data.datas | array | 否 |  | 店铺列表 |
| data.datas[] | object | 否 |  |  |
| data.datas[].name | string | 否 | 测试公司 | 分仓名称 |
| data.datas[].co_id | integer | 否 | 12252 | 主仓公司编号 |
| data.datas[].wms_co_id | integer | 否 | 1 | 分仓编号 |
| data.datas[].is_main | boolean | 否 | false | 是否为主仓，true=主仓 |
| data.datas[].status | string | 否 |  | 状态 |
| data.datas[].remark1 | string | 否 |  | 对方备注 |
| data.datas[].remark2 | string | 否 |  | 我方备注 |

### 请求示例

```json
{
  "page_index": 0,
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
        "wms_co_id": 1,
        "is_main": false,
        "name": "测试公司",
        "co_id": 12252
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

## 商家用户信息

`/open/webapi/userapi/company/getcompanyusers`

| 项 | 内容 |
|---|---|
| 接口名称 | 商家用户信息 |
| 接口路径 | `/open/webapi/userapi/company/getcompanyusers` |
| docType / docId | 1 / 611 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=1&docId=611 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/userapi/company/getcompanyusers` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/userapi/company/getcompanyusers` |


### 接口说明

对应erp菜单“用户及权限”数据

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
| current_page | number | 是 | 1 | 当前页 |
| page_size | number | 是 | 50 | 每页数 |
| page_action | number | 否 | 0 | 查询类型，0:查询分页列表和总数量,1:只查询分页列表,2:只查询总数量 |
| enabled | boolean | 否 |  | 用户状态 |
| version | number | 否 |  | 版本号(默认只返回u_id，name，enabled，created，modified；如需返回分组等信息这个值需要传2) |
| loginId | string | 否 |  | 查询的登录账号 |
| creatd_begin | string | 否 |  | 创建开始时间 |
| creatd_end | string | 否 |  | 创建结束时间 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  |  |
| data | object | 否 |  |  |
| data.current_page | string | 否 |  | 当前页 |
| data.page_size | string | 否 |  | 每页数 |
| data.count | string | 否 |  | 总条数 |
| data.pages | string | 否 |  | 总页数 |
| data.datas | array | 否 |  | 用户数据 |
| data.datas[] | object | 否 |  |  |
| data.datas[].u_id | number | 否 |  | 用户编码 |
| data.datas[].name | string | 否 |  | 用户名称 |
| data.datas[].enabled | string | 否 |  | 状态 |
| data.datas[].created | string | 否 |  | 创建时间 |
| data.datas[].modified | string | 否 |  | 修改时间 |
| data.datas[].last_login_time | string | 否 |  | 最后登录时间 |
| data.datas[].ug_names | array | 否 |  | 所属分组名称 |
| data.datas[].ug_names[] | string | 否 |  |  |
| data.datas[].ug_ids | string | 否 |  | 所属分组id |
| data.datas[].roles | string | 否 |  | 角色名称列表 |
| data.datas[].roleIds | string | 否 |  | 角色id列表 |
| data.datas[].pwd_modified | string | 否 |  | 密码修改时间 |
| data.datas[].remark | string | 否 |  | 备注 |
| data.datas[].empId | string | 否 |  | 工号 |
| data.datas[].creator | string | 否 |  | 创建人 |
| data.datas[].modifier | string | 否 |  | 修改人 |
| msg | string | 否 |  |  |
| requestId | string | 否 |  |  |

### 请求示例

```json
{
  "page_action": 0,
  "current_page": 1,
  "enabled": true,
  "page_size": 50
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "pages": "",
    "datas": [
      {
        "u_id": 0,
        "created": "",
        "name": "",
        "modified": "",
        "enabled": ""
      }
    ],
    "count": "",
    "current_page": "",
    "page_size": ""
  },
  "request_id": ""
}
```


### 异常示例

_无_


---

## 查询我的供应商列表（新）

`/open/api/drp/inneropen/partner/channel/querymysupplier`

| 项 | 内容 |
|---|---|
| 接口名称 | 查询我的供应商列表（新） |
| 接口路径 | `/open/api/drp/inneropen/partner/channel/querymysupplier` |
| docType / docId | 1 / 862 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=1&docId=862 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/drp/inneropen/partner/channel/querymysupplier` |
| 正式环境 | `https://openapi.jushuitan.com/open/api/drp/inneropen/partner/channel/querymysupplier` |


### 接口说明

对应旧接口/open/api/company/inneropen/partner/channel/querymysupplier

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
| status | number | 否 |  | 合作状态-0:待授权；1:待审核；2:合作中;3:已拒绝；4:已终止 |
| co_name | string | 否 |  | 供应商名称 |
| supplier_co_id | string | 否 |  | 供应商编号 |
| page_num | number | 是 | 1 | 页数 |
| page_size | number | 是 | 2 | 每页数量，最大100 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  |  |
| msg | string | 是 |  |  |
| data | object | 是 |  |  |
| data.total | number | 是 |  | 总数 |
| data.supplier_vos | array | 是 |  |  |
| data.supplier_vos[] | object | 否 |  |  |
| data.supplier_vos[].status | number | 是 |  | 合作状态-0:待授权；1:待审核；2:合作中;3:已拒绝；4:已终止 |
| data.supplier_vos[].co_name | string | 是 |  | 供应商公司名 |
| data.supplier_vos[].supplier_co_id | string | 是 |  | 供应商编号 |

### 请求示例

```json
{
  "page_num": 1,
  "supplier_co_id": "",
  "status": 0,
  "co_name": "",
  "page_size": 2
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "total": 0,
    "supplier_vos": [
      {
        "supplier_co_id": "",
        "status": 0,
        "co_name": ""
      }
    ]
  }
}
```


### 异常示例

_无_


---

## 分销商查询

`/open/api/drp/inneropen/partner/supplier/querymychannel`

| 项 | 内容 |
|---|---|
| 接口名称 | 分销商查询 |
| 接口路径 | `/open/api/drp/inneropen/partner/supplier/querymychannel` |
| docType / docId | 1 / 955 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=1&docId=955 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/api/drp/inneropen/partner/supplier/querymychannel` |
| 正式环境 | `https://openapi-hz.jushuitan.com/open/api/drp/inneropen/partner/supplier/querymychannel` |


### 接口说明

系统相关界面：【分销】 ----- 【我的分销商】

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
| status | number | 否 |  | 合作状态-0:待授权；1:待审核；2:合作中;3:已拒绝；4:已终止 |
| page_num | number | 是 | 1 | 页数 |
| page_size | number | 是 | 2 | 每页数量，最大100 |
| updated_start | string | 否 |  | yyyy-MM-dd HH:mm:ss修改时间开始区间开区间,不包含当前值 |
| updated_end | string | 否 |  | yyyy-MM-dd HH:mm:ss修改时间结束时间开区间,不包含当前值 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  |  |
| msg | string | 是 |  |  |
| data | object | 是 |  |  |
| data.total | number | 是 |  | 总数 |
| data.channel_vos | array | 是 |  |  |
| data.channel_vos[] | object | 否 |  |  |
| data.channel_vos[].status | number | 是 |  | 合作状态-0:待授权；1:待审核；2:合作中;3:已拒绝；4:已终止 |
| data.channel_vos[].co_name | string | 是 |  | 分销商商公司名 |
| data.channel_vos[].channel_co_id | string | 是 |  | 分销商编号 |
| data.channel_vos[].apply_time | string | 是 |  | 申请时间 |
| data.channel_vos[].confirm_time | string | 是 |  | 合作时间 |
| data.channel_vos[].bill_name | string | 是 |  | 开单名称 |
| data.channel_vos[].contact_name | string | 是 |  | 联系人名称 |
| data.channel_vos[].contact_phone | string | 是 |  | 联系人手机号 |
| data.channel_vos[].supplier_remark | string | 是 |  | 供应商备注 |
| data.channel_vos[].supplier_salesman_name | string | 是 |  | 供应商业务员名称 |
| data.channel_vos[].dis_level | number | 是 |  | 分销商等级 |
| data.channel_vos[].updated | string | 是 |  | 修改时间 |

### 请求示例

```json
{
  "page_num": 1,
  "status": 0,
  "page_size": 2
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "total": 0,
    "channel_vos": [
      {
        "supplier_salesman_name": "",
        "contact_name": "",
        "contact_phone": "",
        "supplier_remark": "",
        "apply_time": "",
        "bill_name": "",
        "channel_co_id": "",
        "confirm_time": "",
        "status": 0,
        "co_name": ""
      }
    ]
  }
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
