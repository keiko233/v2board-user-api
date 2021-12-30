## 1.订单列表

> `GET` /user/order/fetch

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": [
    {
      "invite_user_id": null,
      "plan_id": 1,
      "coupon_id": null,
      "payment_id": 10,
      "type": 1,
      "cycle": "month_price",
      "trade_no": "xxx",
      "callback_no": null,
      "total_amount": 10,
      "discount_amount": null,
      "surplus_amount": null,
      "refund_amount": null,
      "balance_amount": null,
      "surplus_order_ids": null,
      "status": 2,
      "commission_status": 0,
      "commission_balance": 0,
      "paid_at": null,
      "created_at": 1234567890,
      "updated_at": 1234567890,
      "plan": {
        "表关联"
      }
    }
  ]
}
```

| 参数名                | 类型                       | 描述                        |
|--------------------|--------------------------|---------------------------|
| invite_user_id     | number                   | 邀请人id                     |
| plan_id            | number                   | 订阅id                      |
| coupon_id          | number                   | 优惠券id                     |
| payment_id         | number                   | 支付方式id                    |
| type               | number                   | 订单类型 1新购2续费3升级            |
| cycle              | string                   | 订阅周期                      |
| trade_no           | string                   | 订单号                       |
| callback_no        | string                   | 退款单号                      |
| total_amount       | number                   | 总金额                       |
| discount_amount    | number                   | 折扣金额                      |
| surplus_amount     | number                   | 剩余价值                      |
| refund_amount      | number                   | 退款金额                      |
| balance_amount     | number                   | 使用余额                      |
| surplus_order_ids  | number                   | 折抵订单                      |
| status             | number                   | 订单状态 0待支付1开通中2已取消3已完成4已折抵 |
| commission_status  | number                   | 佣金状态 0待确认1发放中2有效3无效       |
| commission_balance | number                   | 佣金余额                      |
| paid_at            | timestamp                | 支付时间                      |
| created_at         | timestamp                | 创建时间                      |
| updated_at         | timestamp                | 更新时间                      |
| plan               | [关联表](/plan.md/#1订阅商店列表) | 订阅详情                      |

## 2.支付方式

> `GET` /user/order/getPaymentMethod

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": [
    {
      "id": 10,
      "name": "pay",
      "payment": "XXXPay"
    }
  ]
}
```

| 参数名     | 类型     | 描述   |
|---------|--------|------|
| id      | number | 支付id |
| name    | string | 支付名称 |
| payment | string | 支付模块 |

## 3.订单详情

> `GET` /user/order/details?trade_no={trade_no}

- 请求参数 `query`

| 参数名      | 类型     | 描述  |
|----------|--------|-----|
| trade_no | string | 订单号 |

- 成功返回示例 `json`

```json
{
  "data": {
    "id": 1275,
    "invite_user_id": null,
    "user_id": 2057,
    "plan_id": 1,
    "coupon_id": null,
    "payment_id": null,
    "type": 1,
    "cycle": "month_price",
    "trade_no": "xxx",
    "callback_no": null,
    "total_amount": 10,
    "discount_amount": null,
    "surplus_amount": null,
    "refund_amount": null,
    "balance_amount": null,
    "surplus_order_ids": null,
    "status": 0,
    "commission_status": 0,
    "commission_balance": 0,
    "paid_at": null,
    "created_at": 1234567890,
    "updated_at": 1234567890,
    "plan": {
      "表关联"
    },
    "try_out_plan_id": 0
  }
}
```

| 参数名                | 类型                       | 描述                        |
|--------------------|--------------------------|---------------------------|
| id                 | number                   | 订单id                      |
| invite_user_id     | number                   | 邀请人id                     |
| user_id            | number                   | 用户id                      |
| user_id            | number                   | 用户自增id                    |
| plan_id            | number                   | 订阅id                      |
| coupon_id          | number                   | 优惠券id                     |
| payment_id         | number                   | 支付方式id                    |
| type               | number                   | 订单类型 1新购2续费3升级            |
| cycle              | string                   | 订阅周期                      |
| trade_no           | string                   | 订单号                       |
| callback_no        | string                   | 退款单号                      |
| total_amount       | number                   | 总金额                       |
| discount_amount    | number                   | 折扣金额                      |
| surplus_amount     | number                   | 剩余价值                      |
| refund_amount      | number                   | 退款金额                      |
| balance_amount     | number                   | 使用余额                      |
| surplus_order_ids  | number                   | 折抵订单                      |
| status             | number                   | 订单状态 0待支付1开通中2已取消3已完成4已折抵 |
| commission_status  | number                   | 佣金状态 0待确认1发放中2有效3无效       |
| commission_balance | number                   | 佣金余额                      |
| paid_at            | timestamp                | 支付时间                      |
| created_at         | timestamp                | 创建时间                      |
| updated_at         | timestamp                | 更新时间                      |
| plan               | [关联表](/plan.md/#1订阅商店列表) | 订阅详情                      |
| try_out_plan_id    | number                   | 试用计划 ID                   |

## 4.订单状态

> `GET` /user/order/check?trade_no={trade_no}

- 请求参数 `query`

| 参数名      | 类型     | 描述  |
|----------|--------|-----|
| trade_no | string | 订单号 |

- 成功返回示例 `json`

```json
{
  "data": 0
}
```

| 参数名  | 类型     | 描述                   |
|------|--------|----------------------|
| data | number | 0待支付1开通中2已取消3已完成4已折抵 |

## 5.创建订单

> `POST` /user/order/save

- 请求参数 `json`

```json
{
  "cycle": "month_price",
  "plan_id": 1
}
```

| 参数名     | 类型     | 描述   |
|---------|--------|------|
| cycle   | string | 订阅周期 |
| plan_id | number | 订阅id |

- 成功返回示例 `json`

```json
{
  "data": "xxx"
}
```

| 参数名  | 类型     | 描述  |
|------|--------|-----|
| data | string | 订单号 |

## 6.结算订单

> `POST` /user/order/checkout

- 请求参数 `json`

```json
{
  "trade_no": "xxx",
  "method": 1
}
```

| 参数名      | 类型     | 描述   |
|----------|--------|------|
| trade_no | string | 订单号  |
| method   | number | 支付id |

- 成功返回示例 `json`

```json
{
  "type": 0,
  "data": "xxx"
}
```

| 参数名  | 类型     | 描述             |
|------|--------|----------------|
| type | number | 0:qrcode 1:url |
| data | string | 付款地址           |

## 7.关闭订单

> `POST` /user/order/cancel

- 请求参数 `json`

```json
{
  "trade_no": "xxx"
}
```

| 参数名      | 类型     | 描述   |
|----------|--------|------|
| trade_no | string | 订单号  |

- 成功返回示例 `json`

```json
{
  "data": true
}
```

| 参数名  | 类型      | 描述     |
|------|---------|--------|
| data | boolean | 是否关闭成功 |


