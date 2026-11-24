# 聚水潭开放平台 · 拣货批次API（线下版）

> 抓取日期：2026-11-23  
> 分类：拣货批次API（docType=51）  
> 官方入口：https://openweb.jushuitan.com/dev-doc?docType=51&docId=730

公共调用方式：仅 POST；`Content-Type: application/x-www-form-urlencoded;charset=UTF-8`；业务 JSON 放在 `biz`；
`charset=utf-8`，`version=2`；公共字段 `app_key` / `access_token` / `timestamp` / `sign` 必填。

## 本分类接口目录

| 接口 | 路径 | docId | 官方文档 |
|---|---|---|---|
| 校验播种车的状态是否可用 | `/open/jushuitan/carryid/check` | 730 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=730) |
| 绑定播种柜号和播种车 | `/open/jushuitan/binid/carryid/bind` | 729 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=729) |
| 解绑批次拣货车/播种车 | `/open/webapi/wmsapi/wave/unbindwavecarryid` | 467 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=467) |
| 播种回传（不出库） | `/open/jushuitan/seed/return` | 456 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=456) |
| 绑定播种车 | `/open/webapi/wmsapi/wave/bindbinidcarryid` | 111 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=111) |
| 根据播种车号解绑出库单 | `/open/webapi/wmsapi/wave/unbindinoutbycarryid` | 232 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=232) |
| 播种回传（出库） | `/open/jushuitan/seed/callback` | 194 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=194) |
| 获取播种批次信息（支持新版三方仓查询） | `/open/jushuitan/wave/get` | 188 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=188) |
| 更新批次拣货状态 | `/open/jushuitan/wavestatus/upload` | 180 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=180) |
| 指定机器人批次 | `/open/jushuitan/agv/wave/assign` | 172 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=172) |
| 批次预占重算 | `/open/jushuitan/prereducewave/query` | 160 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=160) |
| 机器人获取批次 | `/open/jushuitan/pickwave/query` | 159 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=159) |
| 拣货批次管理查询 | `/open/webapi/wmsapi/wavequery/loadwavesbyfilter` | 112 | [打开](https://openweb.jushuitan.com/dev-doc?docType=51&docId=112) |

## 目录

- [校验播种车的状态是否可用](#校验播种车的状态是否可用)
- [绑定播种柜号和播种车](#绑定播种柜号和播种车)
- [解绑批次拣货车/播种车](#解绑批次拣货车播种车)
- [播种回传（不出库）](#播种回传不出库)
- [绑定播种车](#绑定播种车)
- [根据播种车号解绑出库单](#根据播种车号解绑出库单)
- [播种回传（出库）](#播种回传出库)
- [获取播种批次信息（支持新版三方仓查询）](#获取播种批次信息支持新版三方仓查询)
- [更新批次拣货状态](#更新批次拣货状态)
- [指定机器人批次](#指定机器人批次)
- [批次预占重算](#批次预占重算)
- [机器人获取批次](#机器人获取批次)
- [拣货批次管理查询](#拣货批次管理查询)

---

## 校验播种车的状态是否可用

`/open/jushuitan/carryid/check`

| 项 | 内容 |
|---|---|
| 接口名称 | 校验播种车的状态是否可用 |
| 接口路径 | `/open/jushuitan/carryid/check` |
| docType / docId | 51 / 730 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=730 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/carryid/check` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/carryid/check` |


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
| carry_ids | array | 是 |  | 播种车号 |
| carry_ids[] | string | 否 | BZQ0080 |  |
| wms_co_id | number | 否 | 11180979 | 仓库编码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | boolean | 是 |  | 是否校验成功 |
| code | string | 是 |  | 返回码 |
| issuccess | string | 是 |  | 是否执行成功 |
| msg | string | 是 |  | 执行信息 |

### 请求示例

```json
{
  "wms_co_id": 11180979,
  "carry_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": true,
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

## 绑定播种柜号和播种车

`/open/jushuitan/binid/carryid/bind`

| 项 | 内容 |
|---|---|
| 接口名称 | 绑定播种柜号和播种车 |
| 接口路径 | `/open/jushuitan/binid/carryid/bind` |
| docType / docId | 51 / 729 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=729 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/binid/carryid/bind` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/binid/carryid/bind` |


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
| wave_id | string | 是 |  | 批次号 |
| carry_id | string | 否 |  | 播种车号 |
| wms_co_id | string | 是 |  | 分仓编号 |
| bind_bin_id_carry_ids | array | 是 |  | 出库单播种柜号 |
| bind_bin_id_carry_ids[] | object | 否 |  |  |
| bind_bin_id_carry_ids[].key | object | 是 |  |  |
| bind_bin_id_carry_ids[].key.io_id | number | 是 |  | 出库单号 |
| bind_bin_id_carry_ids[].key.extend_flag | object | 否 |  |  |
| bind_bin_id_carry_ids[].key.extend_flag.lock_wh_id | number | 否 |  | 虚拟仓锁定ID |
| bind_bin_id_carry_ids[].key.extend_flag.outer_lock_whId | number | 否 |  | 外部锁定虚拟仓ID |
| bind_bin_id_carry_ids[].key.extend_flag.is_lock_success | string | 否 |  | 虚拟仓库存是否锁定标记 |
| bind_bin_id_carry_ids[].key.extend_flag.outer_sync_status | string | 否 |  | 外部同步状态 |
| bind_bin_id_carry_ids[].key.extend_flag.push_orders_status | string | 否 |  | 推送出库单状态 |
| bind_bin_id_carry_ids[].key.extend_flag.print_no | number | 否 |  | 打印序号 |
| bind_bin_id_carry_ids[].key.extend_flag.link_bu_id | string | 否 |  | BU 转让或 转入 关联信息 |
| bind_bin_id_carry_ids[].key.extend_flag.p2d_purchase_type | number | 否 |  | 快销采购类型（无 = 0,外采 = 1,单留 = 2, 单拣 = 3） |
| bind_bin_id_carry_ids[].key.extend_flag.lock_percentages | array | 否 |  | 虚拟仓百分比设置 |
| bind_bin_id_carry_ids[].key.extend_flag.lock_percentages[] | object | 否 |  |  |
| bind_bin_id_carry_ids[].key.extend_flag.lock_percentages[].l_wh_id | number | 否 |  | 虚拟仓锁定ID |
| bind_bin_id_carry_ids[].key.extend_flag.lock_percentages[].percentage | number | 否 |  | 百分比 |
| bind_bin_id_carry_ids[].value | number | 是 |  | 播种柜号（相当于bin_id） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | boolean | 是 |  | 是否绑定成功 |
| code | string | 是 |  | 错误码 |
| issuccess | string | 是 |  | 是否执行成功 |
| msg | string | 是 |  | 返回信息 |

### 请求示例

```json
{
  "wave_id": 123,
  "carry_id": "456",
  "bind_bin_id_carry_ids": [
    {
      "key": {
        "io_id": 123,
        "extend_flag": {
          "lock_wh_id": 123,
          "outer_lock_whId": 123,
          "is_lock_success": "abc",
          "outer_sync_status": "abc",
          "push_orders_status": "abc",
          "print_no": 123,
          "link_bu_id": "abc",
          "p2d_purchase_type": "1",
          "lock_percentages": [
            {
              "l_wh_id": 123,
              "percentage": 50
            }
          ]
        }
      },
      "value": 1
    }
  ]
}
```


### 响应示例

```json
{
  "msg": "",
  "code": "",
  "data": true,
  "issuccess": ""
}
```


### 异常示例

```json
{
  "data": true,
  "code": 0,
  "issuccess": true,
  "msg": "执行成功"
}
```


---

## 解绑批次拣货车/播种车

`/open/webapi/wmsapi/wave/unbindwavecarryid`

| 项 | 内容 |
|---|---|
| 接口名称 | 解绑批次拣货车/播种车 |
| 接口路径 | `/open/webapi/wmsapi/wave/unbindwavecarryid` |
| docType / docId | 51 / 467 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=467 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/wave/unbindwavecarryid` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/wave/unbindwavecarryid` |


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
| carry_ids | array | 是 |  |  |
| carry_ids[] | string | 否 | 10 |  |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  |  |
| data | object | 是 |  |  |
| data.is_success | boolean | 是 |  | 是否成功 |
| data.msg | string | 是 |  |  |
| msg | string | 是 |  |  |

### 请求示例

```json
{
  "carry_ids": []
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "data": {
    "msg": "",
    "is_success": true
  }
}
```


### 异常示例

_无_


---

## 播种回传（不出库）

`/open/jushuitan/seed/return`

| 项 | 内容 |
|---|---|
| 接口名称 | 播种回传（不出库） |
| 接口路径 | `/open/jushuitan/seed/return` |
| docType / docId | 51 / 456 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=456 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/seed/return` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/seed/return` |


### 接口说明

只做播种，不更新播种状态

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
| wave_id | number | 是 |  | 批次号 |
| wms_co_id | number | 否 |  | 分仓编码 |
| datas | array | 是 |  | 出库信息集合 |
| datas[] | object | 否 |  |  |
| datas[].io_id | number | 是 |  | 出库单号 |
| datas[].items | array | 是 |  | 商品集合 |
| datas[].items[] | object | 否 |  |  |
| datas[].items[].skuid | string | 是 |  | 商品编码 |
| datas[].items[].skusn | string | 否 |  | 商品唯一码 |
| datas[].items[].ioi_id | string | 是 |  | 出库明细号 |
| datas[].items[].qty | number | 是 |  | 本次播种数量 |
| datas[].items[].seed_qty | number | 是 |  | 累计播种数量 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 是 |  | 返回码 0 表示成功 |
| issuccess | string | 是 |  | 是否调用成功 |
| msg | string | 是 |  | 返回信息 |

### 请求示例

```json
{
  "datas": [
    {
      "items": [
        {
          "qty": "",
          "ioi_id": "",
          "skuid": "",
          "skusn": ""
        }
      ],
      "io_id": 0
    }
  ],
  "wave_id": 0
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

## 绑定播种车

`/open/webapi/wmsapi/wave/bindbinidcarryid`

| 项 | 内容 |
|---|---|
| 接口名称 | 绑定播种车 |
| 接口路径 | `/open/webapi/wmsapi/wave/bindbinidcarryid` |
| docType / docId | 51 / 111 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=111 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/wave/bindbinidcarryid` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/wave/bindbinidcarryid` |


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
| io_ids | array | 是 |  | 出库单信息 |
| io_ids[] | object | 否 |  |  |
| io_ids[].io_id | string | 是 |  | 出库明细号 |
| io_ids[].bin_id | string | 是 |  | 仓位编码 |
| wave_id | string | 是 |  | 批次编码 |
| carry_id | string | 是 |  | 车号 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | boolean | 否 |  | 是否成功 |
| code | number | 否 |  | 返回编码 |
| msg | string | 否 |  | 返回信息 |
| request_id | string | 否 |  | 请求id |

### 请求示例

```json
{
  "carry_id": "",
  "wave_id": "",
  "io_ids": [
    {
      "bin_id": "",
      "io_id": ""
    }
  ]
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

```json
{"code":0,"msg":"错误信息","request_id":"xxxxxx","data":{}/[]}
```


---

## 根据播种车号解绑出库单

`/open/webapi/wmsapi/wave/unbindinoutbycarryid`

| 项 | 内容 |
|---|---|
| 接口名称 | 根据播种车号解绑出库单 |
| 接口路径 | `/open/webapi/wmsapi/wave/unbindinoutbycarryid` |
| docType / docId | 51 / 232 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=232 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/wave/unbindinoutbycarryid` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/wave/unbindinoutbycarryid` |


### 接口说明

禅道任务： https://jst.zentaopm.com/task-view-115470.html

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
| carry_id | string | 是 | 1234 | 车号 |
| is_append_jb_cc | boolean | 是 | true | 传true |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 是 |  | 0表示正常 |
| msg | string | 是 |  | 错误提示文案 |
| data | boolean | 是 |  |  |

### 请求示例

```json
{
  "carry_id": "1234",
  "is_append_jb_cc": true
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

## 播种回传（出库）

`/open/jushuitan/seed/callback`

| 项 | 内容 |
|---|---|
| 接口名称 | 播种回传（出库） |
| 接口路径 | `/open/jushuitan/seed/callback` |
| docType / docId | 51 / 194 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=194 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/seed/callback` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/seed/callback` |


### 接口说明

更多播种API相关问题请关注常见问题文档（持续更新）： https://openweb.jushuitan.com/qaCenter?groupId=12&cataId=29&currentPage=1&pageSize=20

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
| wave_id | string | 是 |  |  |
| wms_co_id | number | 否 |  | 分仓编码 |
| datas | array | 是 |  |  |
| datas[] | object | 否 |  |  |
| datas[].io_id | integer | 是 |  |  |
| datas[]. items | array | 是 |  |  |
| datas[]. items[] | object | 否 |  |  |
| datas[]. items[].skuid | string | 是 |  | 商品编码 |
| datas[]. items[].skusn | string | 否 |  | 商品唯一码 |
| datas[]. items[].ioi_id | string | 是 |  | 出库明细号 |
| datas[]. items[].qty | string | 是 |  | 本次播种数量 |
| datas[]. items[].seed_qty | string | 是 |  | 累计播种数量 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | string | 否 |  |  |
| issuccess | boolean | 否 |  |  |
| msg | string | 否 |  |  |
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].wave_id | string | 否 |  | 批次号 |
| data[].io_id | integer | 否 |  | 出库单号 |
| data[].ioi_id | integer | 否 |  |  |
| data[].issuccess | string | 否 |  |  |
| data[].msg | string | 否 |  |  |

### 请求示例

```json
{
  "wave_id": 5105742,
  "datas": [
    {
      "io_id": 128949836,
      "items": [
        {
          "skuid": "6936586112599",
          "ioi_id": 195414605,
          "qty": 2,
          "seed_qty": 2
        },
        {
          "skuid": "6936586119109",
          "ioi_id": 195414608,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586119147",
          "ioi_id": 195414606,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128998303,
      "items": [
        {
          "skuid": "6936586119031",
          "ioi_id": 195493438,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586111493",
          "ioi_id": 195493439,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128965499,
      "items": [
        {
          "skuid": "6936586112599",
          "ioi_id": 195439771,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586119109",
          "ioi_id": 195439772,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586119024",
          "ioi_id": 195439773,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128957830,
      "items": [
        {
          "skuid": "6936586161863",
          "ioi_id": 195427387,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586112599",
          "ioi_id": 195427386,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586189102",
          "ioi_id": 195427385,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128975988,
      "items": [
        {
          "skuid": "6936586119093",
          "ioi_id": 195457725,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586112599",
          "ioi_id": 195457724,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586119024",
          "ioi_id": 195457723,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 129015474,
      "items": [
        {
          "skuid": "6974386978236",
          "ioi_id": 195518303,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "LDN181A3853",
          "ioi_id": 195518304,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128953413,
      "items": [
        {
          "skuid": "6936586112599",
          "ioi_id": 195420465,
          "qty": 2,
          "seed_qty": 2
        },
        {
          "skuid": "6936586119116",
          "ioi_id": 195420467,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586119093",
          "ioi_id": 195420466,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 129008326,
      "items": [
        {
          "skuid": "6936586192751",
          "ioi_id": 195508298,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6974386971657",
          "ioi_id": 195508297,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586181489",
          "ioi_id": 195508299,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128999413,
      "items": [
        {
          "skuid": "6936586176423",
          "ioi_id": 195495044,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 129019548,
      "items": [
        {
          "skuid": "LDN20724A4812",
          "ioi_id": 195524736,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6941814400706",
          "ioi_id": 195524735,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "LDN20724A5010",
          "ioi_id": 195524737,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128986227,
      "items": [
        {
          "skuid": "6974387000660",
          "ioi_id": 195475175,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586181601",
          "ioi_id": 195475174,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128971373,
      "items": [
        {
          "skuid": "6974387008413",
          "ioi_id": 195449922,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586181465",
          "ioi_id": 195449923,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586188129",
          "ioi_id": 195449920,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586181496",
          "ioi_id": 195449921,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 129019624,
      "items": [
        {
          "skuid": "6941814407347",
          "ioi_id": 195524847,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6941814407514",
          "ioi_id": 195524848,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "LDN6023A3225",
          "ioi_id": 195524849,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6941814407460",
          "ioi_id": 195524850,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128964385,
      "items": [
        {
          "skuid": "6936586118676",
          "ioi_id": 195437772,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586119109",
          "ioi_id": 195437773,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128965194,
      "items": [
        {
          "skuid": "6936586119109",
          "ioi_id": 195439205,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586189102",
          "ioi_id": 195439204,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "LDN181A3657",
          "ioi_id": 195439206,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "LDN181A4464",
          "ioi_id": 195439207,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128983546,
      "items": [
        {
          "skuid": "6936586104761",
          "ioi_id": 195470596,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586119109",
          "ioi_id": 195470597,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 129019196,
      "items": [
        {
          "skuid": "6936586194045",
          "ioi_id": 195524193,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586193994",
          "ioi_id": 195524192,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "LDN0958A4010",
          "ioi_id": 195524191,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 129019676,
      "items": [
        {
          "skuid": "LDN102A4067",
          "ioi_id": 195524930,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "LDN102A4027",
          "ioi_id": 195524929,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "6936586181359",
          "ioi_id": 195524928,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 129016905,
      "items": [
        {
          "skuid": "LDN202710A4211",
          "ioi_id": 195520498,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    },
    {
      "io_id": 128986109,
      "items": [
        {
          "skuid": "LDN1521A2905",
          "ioi_id": 195474975,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "LDN20724A4410",
          "ioi_id": 195474977,
          "qty": 1,
          "seed_qty": 1
        },
        {
          "skuid": "LDN1521A2815",
          "ioi_id": 195474976,
          "qty": 1,
          "seed_qty": 1
        }
      ]
    }
  ]
}
```


### 响应示例

```json
{
  "code": 0,
  "issuccess": true,
  "msg": "执行成功",
  "data": [
    {
      "wave_id": 5105742,
      "io_id": 128949836,
      "ioi_id": 195414605,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128949836,
      "ioi_id": 195414608,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128949836,
      "ioi_id": 195414606,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128998303,
      "ioi_id": 195493438,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128998303,
      "ioi_id": 195493439,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128965499,
      "ioi_id": 195439771,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128965499,
      "ioi_id": 195439772,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128965499,
      "ioi_id": 195439773,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128957830,
      "ioi_id": 195427387,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128957830,
      "ioi_id": 195427386,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128957830,
      "ioi_id": 195427385,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128975988,
      "ioi_id": 195457725,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128975988,
      "ioi_id": 195457724,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128975988,
      "ioi_id": 195457723,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129015474,
      "ioi_id": 195518303,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129015474,
      "ioi_id": 195518304,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128953413,
      "ioi_id": 195420465,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128953413,
      "ioi_id": 195420467,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128953413,
      "ioi_id": 195420466,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129008326,
      "ioi_id": 195508298,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129008326,
      "ioi_id": 195508297,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129008326,
      "ioi_id": 195508299,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128999413,
      "ioi_id": 195495044,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019548,
      "ioi_id": 195524736,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019548,
      "ioi_id": 195524735,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019548,
      "ioi_id": 195524737,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128986227,
      "ioi_id": 195475175,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128986227,
      "ioi_id": 195475174,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128971373,
      "ioi_id": 195449922,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128971373,
      "ioi_id": 195449923,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128971373,
      "ioi_id": 195449920,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128971373,
      "ioi_id": 195449921,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019624,
      "ioi_id": 195524847,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019624,
      "ioi_id": 195524848,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019624,
      "ioi_id": 195524849,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019624,
      "ioi_id": 195524850,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128964385,
      "ioi_id": 195437772,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128964385,
      "ioi_id": 195437773,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128965194,
      "ioi_id": 195439205,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128965194,
      "ioi_id": 195439204,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128965194,
      "ioi_id": 195439206,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128965194,
      "ioi_id": 195439207,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128983546,
      "ioi_id": 195470596,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128983546,
      "ioi_id": 195470597,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019196,
      "ioi_id": 195524193,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019196,
      "ioi_id": 195524192,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019196,
      "ioi_id": 195524191,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019676,
      "ioi_id": 195524930,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019676,
      "ioi_id": 195524929,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129019676,
      "ioi_id": 195524928,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 129016905,
      "ioi_id": 195520498,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128986109,
      "ioi_id": 195474975,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128986109,
      "ioi_id": 195474977,
      "issuccess": true,
      "msg": "执行成功"
    },
    {
      "wave_id": 5105742,
      "io_id": 128986109,
      "ioi_id": 195474976,
      "issuccess": true,
      "msg": "执行成功"
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

## 获取播种批次信息（支持新版三方仓查询）

`/open/jushuitan/wave/get`

| 项 | 内容 |
|---|---|
| 接口名称 | 获取播种批次信息（支持新版三方仓查询） |
| 接口路径 | `/open/jushuitan/wave/get` |
| docType / docId | 51 / 188 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=188 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/wave/get` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/wave/get` |


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
| wave_id | integer | 是 |  | 批次号 |
| wms_co_id | number | 否 |  | 分仓编码（如果是分仓的拣货批次需要传对应的分仓编码） |
| is_force_seeder | boolean | 否 |  | 是否强制绑定播种人（忽略批次已有播种人，仅等待播种状态生效） |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | boolean | 否 |  | 0代表成功 |
| msg | string | 否 |  | 执行描述 |
| data | object | 否 |  |  |
| data.wave_id | integer | 否 |  | 批次号 |
| data.order_count | integer | 否 |  | 订单数量 |
| data.sku_count | integer | 否 |  | 商品种类数量 |
| data.sku_qty | integer | 否 |  | 商品数量 |
| data.status | string | 否 |  | 批次状态 |
| data.created | string | 否 |  | 批次状态 |
| data.remark | string | 否 |  | 备注 |
| data.Inouts | array | 否 |  | 出库单集合 |
| data.Inouts[] | object | 否 |  |  |
| data.Inouts[].io_id | integer | 否 |  | 出库单号 |
| data.Inouts[].o_id | integer | 否 |  | 内部订单号 |
| data.Inouts[].idx | integer | 否 |  | 播种柜号 |
| data.Inouts[].l_international_id  | string | 否 |  | 国际物流单号 |
| data.Inouts[].l_id | string | 否 |  | 快递单号 |
| data.Inouts[].lc_id | string | 否 |  | 快递编码 |
| data.Inouts[].logistics_company | string | 否 |  | 物流公司名称 |
| data.Inouts[].status | string | 否 |  | 出库单状态 |
| data.Inouts[].items | array | 否 |  | 播种商品集合 |
| data.Inouts[].items[] | object | 否 |  |  |
| data.Inouts[].items[].sku_id | string | 否 |  | 商品编码 |
| data.Inouts[].items[].sku_code | string | 否 |  | 国标码 |
| data.Inouts[].items[]._sku_codes | array | 否 |  | 辅助码（改版三方仓不支持，最多透出10个） |
| data.Inouts[].items[]._sku_codes[] | string | 否 |  |  |
| data.Inouts[].items[].i_id | string | 否 |  | 款式编码 |
| data.Inouts[].items[].name | string | 否 |  | 商品名称 |
| data.Inouts[].items[].qty | integer | 否 |  | 商品数量 |
| data.Inouts[].items[].seed_qty | integer | 否 |  | 已播数数量 |
| data.Inouts[].items[].properties_value | string | 否 |  | 样式 |
| data.Inouts[].items[].ioi_id | integer | 否 |  | 商品自增键 |

### 请求示例

```json
{
  "wave_id": 115
}
```


### 响应示例

```json
{
  "code": null,
  "msg": "",
  "data": {
    "data": {
      "wave_id": 115,
      "status": "Picking",
      "order_count": 56,
      "sku_count": 101,
      "sku_qty": 112,
      "created": "2021-09-12 15:15:17",
      "remark": null,
      "Inouts": [
        {
          "io_id": 56,
          "idx": 0,
          "l_id": "1111111111166",
          "lc_id": "STO",
          "logistics_company": "申通E物流",
          "status": "WaitConfirm",
          "o_id": "1",
          "items": [
            {
              "sku_id": "LDN000A0001",
              "name": "【000杂款清仓】",
              "qty": 1,
              "seed_qty": 0,
              "properties_value": "凉拖正品;",
              "ioi_id": 111
            },
            {
              "sku_id": "LDN0205A4419",
              "name": "【0205流氓兔洞洞鞋】",
              "qty": 1,
              "seed_qty": 0,
              "properties_value": "黑色;44",
              "ioi_id": 112
            }
          ]
        },
        {
          "io_id": 55,
          "idx": 1,
          "l_id": "1111111111165",
          "lc_id": "STO",
          "logistics_company": "申通E物流",
          "status": "WaitConfirm",
          "o_id": "2",
          "items": [
            {
              "sku_id": "LDN000A0002",
              "name": "【000杂款清仓】",
              "qty": 1,
              "seed_qty": 0,
              "properties_value": "凉拖残次;",
              "ioi_id": 109
            },
            {
              "sku_id": "LDN0205A4467",
              "name": "【0205流氓兔洞洞鞋】",
              "qty": 1,
              "seed_qty": 0,
              "properties_value": "深蓝;44",
              "ioi_id": 110
            }
          ]
        }
      ]
    }
  }
}
```


### 异常示例

```json
{
  "msg": "参数无法转换，请检查. Error parsing NaN value. Path 'wave_id', line 1, position 11.",
  "code": 130,
  "requestId": "2760825f17273151789827767ede8d"
}
```


---

## 更新批次拣货状态

`/open/jushuitan/wavestatus/upload`

| 项 | 内容 |
|---|---|
| 接口名称 | 更新批次拣货状态 |
| 接口路径 | `/open/jushuitan/wavestatus/upload` |
| docType / docId | 51 / 180 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=180 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/wavestatus/upload` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/wavestatus/upload` |


### 接口说明

更改批次状态，由正常拣货更改为等待出库验货（单件），等待播种（多件）

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
| wave_id | number | 是 |  | 拣货批次号 |
| wave_status | string | 否 |  | 批次状态（等待播种；等待验货出库） |
| wms_co_id | number | 否 |  | 分仓编码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 状态码 0表示成功 |
| issuccess | boolean | 否 |  | 执行结果 |
| msg | string | 否 |  | 提示信息 |

### 请求示例

```json
{
  "wave_id": 0
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

## 指定机器人批次

`/open/jushuitan/agv/wave/assign`

| 项 | 内容 |
|---|---|
| 接口名称 | 指定机器人批次 |
| 接口路径 | `/open/jushuitan/agv/wave/assign` |
| docType / docId | 51 / 172 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=172 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/agv/wave/assign` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/agv/wave/assign` |


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
| wave_id | number | 是 |  | 批次Id |
| robot_name | string | 是 |  | 机器人名称（用户及权限的用户名） |
| bin | string | 否 |  | 仓位 |
| wms_co_id | number | 否 |  | 分仓编码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| code | number | 否 |  | 状态码 |
| issuccess | boolean | 否 |  | 是否成功 |
| msg | string | 否 |  | 描述信息 |
| data | object | 否 |  | 数据集合 |
| data.wave_id | number | 否 |  | 批次号 |
| data.status | string | 否 |  | 状态 |
| data.type | string | 否 |  | 类型 |
| data.bin | string | 否 |  | 仓位 |
| data.pick_finish | boolean | 否 |  | 是否拣货完成 |
| data.is_agv_pick | boolean | 否 |  | 是否AGV拣货 |
| data.remark | string | 否 |  | 备注 |
| data.filter | string | 否 |  | 过滤 |
| data.user_id | number | 否 |  | 用户id |

### 请求示例

```json
{
  "bin": "",
  "robot_name": "",
  "wave_id": 0
}
```


### 响应示例

```json
{
  "msg": "",
  "code": 0,
  "issuccess": true,
  "data": {
    "filter": "",
    "user_id": 0,
    "bin": "",
    "wave_id": 0,
    "pick_finish": true,
    "is_agv_pick": true,
    "remark": "",
    "type": "",
    "status": ""
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

## 批次预占重算

`/open/jushuitan/prereducewave/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 批次预占重算 |
| 接口路径 | `/open/jushuitan/prereducewave/query` |
| docType / docId | 51 / 160 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=160 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/prereducewave/query` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/prereducewave/query` |


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
| wave_ids | array | 是 |  | 批次号列表，最多50个 |
| wave_ids[] | number | 否 |  |  |
| wms_co_id | number | 否 |  | 分仓编码 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].wave_id | number | 否 |  | 批次号 |
| data[].bin | string | 否 |  | 仓位 |
| data[].status | string | 否 |  | 状态 |
| code | string | 否 |  | 0代码成功 |
| issuccess | string | 否 |  | 是否成功描述 |
| msg | string | 否 |  | 执行结果描述 |

### 请求示例

```json
{
  "wave_ids": [
    6849,
    565745
  ]
}
```


### 响应示例

```json
{
  "code": 0,
  "issuccess": true,
  "msg": "执行成功",
  "data": [
    {
      "wave_id": 6849,
      "bin": "A-1-3-4",
      "status": "Confirmed"
    },
    {
      "wave_id": 565745,
      "bin": "A-1-4-4",
      "status": "Delete"
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

## 机器人获取批次

`/open/jushuitan/pickwave/query`

| 项 | 内容 |
|---|---|
| 接口名称 | 机器人获取批次 |
| 接口路径 | `/open/jushuitan/pickwave/query` |
| docType / docId | 51 / 159 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=159 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/jushuitan/pickwave/query` |
| 正式环境 | `https://openapi.jushuitan.com/open/jushuitan/pickwave/query` |


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
| robot_id | string | 是 |  | 机器人编号 |
| wms_co_id | number | 否 |  | 分仓编号，0 代表主仓本仓 |
| bin | string | 否 |  | 仓位 |
| wave_id | number | 否 |  | 批次号 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | object | 否 |  |  |
| data.wave_id | number | 否 |  | 批次号 |
| data.status | string | 否 |  | 当前批次状态 |
| data.type | string | 否 |  | 类型 |
| data.bin | string | 否 |  | 拣货的第一个仓位 |
| data.pick_finish | boolean | 否 |  | 是否已拣完货 |
| data.remark | string | 否 |  | 标志(备注) |
| data.is_agv_pick | boolean | 否 |  |  |
| data.filter | string | 否 |  |  |
| code | string | 否 |  | 错误码，0代表成功 |
| issuccess | string | 否 |  | true代表成功 |
| msg | string | 否 |  | 描述 |

### 请求示例

```json
{
  "robot_id": "A00439",
  "wave_id": 1648327
}
```


### 响应示例

```json
{
  "data": {
    "wave_id": 1648327,
    "status": "Seeding",
    "type": "Multiple",
    "bin": null,
    "pick_finish": true,
    "is_agv_pick": true,
    "remark": "【AGV拣货】全店铺全二楼全区多件-6",
    "filter": "全店铺全二楼全区多件-6"
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

## 拣货批次管理查询

`/open/webapi/wmsapi/wavequery/loadwavesbyfilter`

| 项 | 内容 |
|---|---|
| 接口名称 | 拣货批次管理查询 |
| 接口路径 | `/open/webapi/wmsapi/wavequery/loadwavesbyfilter` |
| docType / docId | 51 / 112 |
| 官方文档 | https://openweb.jushuitan.com/dev-doc?docType=51&docId=112 |
| 请求方法 | POST，`Content-Type: application/x-www-form-urlencoded;charset=UTF-8` |
| 业务参数 | 表单字段 `biz`（JSON 字符串） |

### 请求地址

| 环境 | HTTPS 地址 |
|---|---|
| 测试环境 | `https://dev-api.jushuitan.com/open/webapi/wmsapi/wavequery/loadwavesbyfilter` |
| 正式环境 | `https://openapi.jushuitan.com/open/webapi/wmsapi/wavequery/loadwavesbyfilter` |


### 接口说明

1 不加创建时间的查询默认只筛选近三天的数据，查询超过三天的数据需要传入创建时间字段参与查询。
 2 反参中type对应的枚举值如下：
 [Description("选择商品")]
 None = 0,
 [Description("一单一件")]
 Single = 1,
 [Description("一单多件")]
 Multiple = 2,
 [Description("采购退货")]
 PurchaseReturn = 5,
 [Description("现场|大单")]
 Door = 6,
 [Description("调拨单")]
 Allocate = 61,
 [Description("其它出库")]
 OtherOut = 62,
 [Description("整箱")]
 Pack = 7,
 [Description("补货")]
 Add = 8,
 [Description("组团")]
 Group = 9,
 [Description("二次分拣")]
 PickPick = 10,
 [Description("订单拣货")]
 OrderPick = 101,
 [Description("组装")]
 CombinePick = 11,
 [Description("下架任务")]
 UnShelvesPick = 12,
 [Description("快销配货批次")]
 P2DPick = 13,
 [Description("A+N拣货")]
 ANPick = 15,
 [Description("移货拣货")]
 MovePick = 16,
 [Description("散货上架")]
 ScatteredToBin = 88,
 [Description("进仓上架")]
 InToBin = 89,
 [Description("补货上架")]
 AddToBin = 90,
 [Description("AGV")]
 AGV = 201,
 [Description("单SKU拣货")]
 SingleSku = 17,
 [Description("单SPU拣货")]
 SingleSpu = 18

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
| wave_ids | array | 否 |  | 批次列表 |
| wave_ids[] | number | 否 |  |  |
| create_time_begin | string | 否 |  | 创建开始时间（时间请求跨度在三天以内） |
| create_time_end | string | 否 |  | 创建结束时间（时间请求跨度在三天以内） |
| modified_begin | string | 否 |  | 修改开始时间（时间请求跨度在三天以内） |
| modified_end | string | 否 |  | 修改结束时间（时间请求跨度在三天以内） |
| wave_status | array | 否 |  | None = 0, WaitPurchase = 6, WaitPick = 1, Picking = 11, WaitSeed = 2, Seeding = 22, WaitCheck = 3, Checking = 33, WaitFinish = 4, Finished = 44, Break = 5, WaitToBin = 55。只传批次状态（wave_status ）或者批次类型（wave_types ）查询默认添加最近3天以内时间限制 |
| wave_status[] | string | 否 |  |  |
| wave_types | array | 否 |  | 1：单件批次 2：多件 6：大单 7：整箱 8：补货 9：组团 10：二次分拣 15：A+N批次。只传批次状态（wave_status ）或者批次类型（wave_types ）查询默认添加最近3天以内时间限制） |
| wave_types[] | number | 否 |  |  |
| wave_carry_ids | array | 否 |  | 批次绑定的播种车号（批次号最大查询数量控制在1000） |
| wave_carry_ids[] | string | 否 | 0493 |  |
| check_wms_coid | boolean | 否 |  | 默认是true只能查主仓，传false可以查分仓的批次 |

### 返回参数

| 参数 | 类型 | 必填 | 示例 | 说明 |
|---|---|---|---|---|
| data | array | 否 |  |  |
| data[] | object | 否 |  |  |
| data[].wave_id | number | 否 |  | 批次号 |
| data[].carry_ids | array | 否 |  | 播种车号 |
| data[].carry_ids[] | string | 否 |  |  |
| data[].type | string | 否 |  | 类型 |
| data[].co_id | number | 否 |  | 公司编码 |
| data[].picker | string | 否 |  | 拣货员编码 |
| data[].picked_qty | number | 否 |  | 已拣数 |
| data[].qty | number | 否 |  | 商品总数 |
| data[].picker_name | string | 否 |  | 拣货员名称 |
| data[].order_count | number | 否 |  | 订单数 |
| data[].sku_count | number | 否 |  | 单品种类数 |
| data[].sku_qty | number | 否 |  | 商品总量 |
| data[].status | string | 否 |  | 批次状态（WaitPick 等待拣货 Break 终止拣货 Finished 已完成 WaitToBin 等待上架 WaitSeed 等待播种 WaitCheck 等待出库验货 WaitFinish 等待完成 Picking 正在拣货 WaitPurchase 等待采购 Seeding 正在播种 Checking 正在出库验货） |
| data[].created | string | 否 |  | 创建时间 |
| data[].creator | string | 否 |  | 创建人 |
| data[].modified | string | 否 |  | 修改时间 |
| data[].seed_begin | string | 否 |  | 播种开始时间 |
| data[].seeder_id | string | 否 |  | 播种员编号 |
| data[].seeder_name | string | 否 |  | 播种员名称 |
| data[].remark | string | 否 |  | 标志 |
| data[].hybrid_pick | string | 否 |  | 混合捡 |
| data[].wms_co_id | number | 否 |  | 分仓编码 |
| data[].filter | string | 否 |  | 策略 |
| data[].is_print | boolean | 否 |  | 是否打印 |
| data[].wave_bin | string | 否 |  | 批次箱号 |
| data[].po_id | number | 否 |  | 采购单号 |
| data[].split_pick | string | 否 |  | 分段捡 |
| data[].is_print_express | boolean | 否 |  | 是否打印面单 |
| data[].paper_pick | string | 否 |  | 纸质批次 |
| data[].pick_seed | string | 否 |  |  |
| data[].is_print_order | boolean | 否 |  | 是否打印订单 |
| data[].wh_id | number | 否 |  | 仓位号 主仓=1、销退仓=2、进货仓=3、次品仓=4 |
| data[].priorty | number | 否 |  | 优先级 |
| data[].pick_invert | boolean | 否 |  | 倒序拣货 |
| data[].is_print_ordertags | boolean | 否 |  | 是否打印订单标签 |
| data[].wave_flag | object | 否 |  |  |
| data[].wave_extend_type | string | 否 |  | 批次子类型 |
| data[].items | array | 否 |  | 商品明细 |
| data[].items[] | object | 否 |  |  |
| data[].items[].wave_item_id | number | 否 |  | 批次明细编号 |
| data[].items[].wave_id | number | 否 |  | 批次编号 |
| data[].items[].bin | string | 否 |  | 仓位 |
| data[].items[].sku_id | string | 否 |  | 商品编号 |
| data[].items[].name | string | 否 |  | 商品名称 |
| data[].items[].properties_value | string | 否 |  | 商品属性 |
| data[].items[].picked_qty | number | 否 |  | 已拣数量 |
| data[].items[].qty | number | 否 |  | 数量 |
| data[].items[].bin_id | number | 否 |  | 播种柜号 |
| data[].items[].skip | boolean | 否 |  | 是否跳过 |
| data[].items[].checked_qty | number | 否 |  | 纸质批次拣货指引已拣数量 |
| data[].items[].disabled | boolean | 否 |  | 是否有效 |
| data[].items[].other_bin | string | 否 |  | 其它仓位 |
| data[].items[].i_id | string | 否 |  | 款号 |
| data[].items[].sub_pack_qty | number | 否 |  | 小包装数量 |
| data[].items[].skip_pick_pack | boolean | 否 |  | 跳过拣货区 |
| data[].items[].skip_pick_bin | boolean | 否 |  | 跳过存货区 |
| data[].items[].combine_sku_id | string | 否 |  | 组合装编号 |
| data[].items[].batch_id | string | 否 |  | 批次号 |
| data[].items[].produced_date | string | 否 |  | 生产日期 |
| data[].items[].supplier_id | number | 否 |  | 供应商编号 |
| data[].items[].wave_item_type | string | 否 |  | 移货类型(MoveOut:移出,MoveIn:移入) |
| data[].items[].relate_id | number | 否 |  | 移货批次关联Id |
| data[].items[].expiration_date | string | 否 |  | 失效日期 |
| data[].items[].wave_co_id | number | 否 |  | 商家编号 |
| code | number | 否 |  | 返回码 |
| msg | string | 否 |  | 提示信息 |
| request_id | string | 否 |  | 请求唯一码 |

### 请求示例

```json
{
  "wave_ids": [
    25182
  ],
  "wave_status": [
    "1"
  ],
  "wave_types": [
    1,
    2,
    6,
    7,
    8,
    9,
    10,
    15
  ],
  "create_time_begin": "2023-03-27 15:35:04",
  "modified_begin": null,
  "modified_end": null,
  "create_time_end": "2023-04-03 15:35:04"
}
```


### 响应示例

```json
{
  "msg": null,
  "code": 0,
  "data": [
    {
      "is_print_express": null,
      "wave_bin": null,
      "po_id": null,
      "remark": "顺丰",
      "type": 2,
      "seeder_id": null,
      "pick_invert": false,
      "picker_name": null,
      "paper_pick": null,
      "pick_seed": null,
      "wave_id": 25182,
      "modified": "2023-04-03 15:50:49",
      "split_pick": null,
      "picker": null,
      "is_print": null,
      "hybrid_pick": null,
      "creator": 15752113,
      "order_count": 3,
      "created": "2023-04-03 15:34:47",
      "co_id": 12281572,
      "seed_begin": null,
      "filter": "邮政",
      "is_print_order": true,
      "priorty": 1000,
      "wms_co_id": 12281572,
      "sku_qty": 10,
      "wh_id": 1,
      "is_print_ordertags": null,
      "sku_count": 1,
      "wave_flag": "{\"IsStockout\":false,\"OrderPool\":0,\"UrgencyCount\":0,\"TimeOrderCount\":0,\"AislesCount\":0,\"IsSAdd\":false,\"PickBySku\":false}",
      "wave_extend_type": null,
      "seeder_name": null,
      "status": "Finished",
      "ts": "AAAAABAI9Zs="
    }
  ],
  "request_id": null
}
```


### 异常示例

```json
{"code":0,"msg":"错误信息","request_id":"xxxxxx","data":{}/[]}
```


---
