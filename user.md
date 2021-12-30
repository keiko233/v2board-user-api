## 1.登出

> `GET` /user/logout

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": true
}
```

| 参数名  | 类型      | 描述     |
|------|---------|--------|
| data | boolean | 是否登出成功 |

## 2.账号信息

> `GET` /user/info

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": {
    "email": "xxxx@xx.com",
    "transfer_enable": 0,
    "last_login_at": null,
    "created_at": 1234567890,
    "banned": 0,
    "remind_expire": 0,
    "remind_traffic": 0,
    "expired_at": 0,
    "balance": 0,
    "commission_balance": 0,
    "plan_id": null,
    "discount": null,
    "commission_rate": null,
    "telegram_id": null,
    "uuid": "xxxxxx-xxxx-xxxx-xxxx-xxxxxx",
    "avatar_url": "https://xxxx.com/xxx.xxx"
  }
}
```

| 参数名                | 类型                     | 描述      |
|--------------------|------------------------|---------|
| email              | string                 | 邮箱地址    |
| transfer_enable    | number                 | 总可用流量   |
| last_login_at      | timestamp              | 最后登入时间  |
| created_at         | timestamp              | 创建时间    |
| banned             | number                 | 是否封禁使用  |
| remind_expire      | number                 | 到期邮件提醒  |
| remind_traffic     | number                 | 流量邮件提醒  |
| expired_at         | timestamp              | 过期时间    |
| balance            | number                 | 用户余额    |
| commission_balance | number                 | 佣金余额    |
| plan_id            | number - object(&plan) | 当前订阅id  |
| discount           | number                 | 消费折扣    |
| commission_rate    | number                 | 佣金率     |
| telegram_id        | number                 | 绑定TG id |
| uuid               | string                 | 唯一UUID  |
| avatar_url         | string                 | 头像地址    |

## 3.订阅信息

> `GET` /user/getSubscribe

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": {
    "plan_id": null,
    "token": "xxx",
    "expired_at": 0,
    "u": 0,
    "d": 0,
    "transfer_enable": 0,
    "email": "xxx@xxx.com",
    "subscribe_url": "https://xxx.com/api/v1/client/subscribe?token=xxx",
    "reset_day": null
  }
}
```

| 参数名             | 类型                     | 描述       |
|-----------------|------------------------|----------|
| plan_id         | number - object(&plan) | 订阅id     |
| token           | string                 | 用户 token |
| expired_at      | timestamp              | 过期时间     |
| u               | number                 | 已用上行流量   |
| d               | number                 | 已用下行流量   |
| transfer_enable | number                 | 总可用流量    |
| email           | string                 | 邮箱地址     |
| subscribe_url   | string                 | 订阅链接     |
| reset_day       | number                 | 重置日      |

## 4.重置订阅链接

> `GET` /user/resetSecurity

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": "https://xxx.com/api/v1/client/subscribe?token=xxx"
}
```

| 参数名  | 类型     | 描述   |
|------|--------|------|
| data | string | 订阅链接 |

## 5.代办事项

> `GET` /user/getStat

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": [
    0,
    0,
    0
  ]
}
```

| 参数名     | 类型     | 描述    |
|---------|--------|-------|
| data[0] | number | 待付订单  |
| data[1] | number | 代办工单  |
| data[2] | number | 待确认邀请 |

## 6.修改密码

> `POST` /user/changePassword

- 请求参数 `json`

```json
{
  "old_password": "123456789",
  "new_password": "1234567890"
}
```

| 参数名          | 类型     | 必填  | 描述  |
|--------------|--------|-----|-----|
| old_password | string | ✔︎  | 旧密码 |
| new_password | string | ✔︎  | 新密码 |

- 成功返回示例 `json`

```json
{
  "data": true
}
```

| 参数名  | 类型      | 描述     |
|------|---------|--------|
| data | boolean | 是否修改成功 |

## 7.通知状态

> `POST` /user/update

- 请求参数 `json`

```json
{
  "remind_expire": 0
}
```

| 参数名            | 类型     | 必填  | 描述     |
|----------------|--------|-----|--------|
| remind_expire  | number | ✖︎︎ | 到期邮件提醒 |
| remind_traffic | number | ✖︎  | 流量邮件提醒 |

- 成功返回示例 `json`

```json
{
  "data": true
}
```

| 参数名  | 类型      | 描述     |
|------|---------|--------|
| data | boolean | 是否修改成功 |

## 8.佣金划转

> `POST` /user/transfer

- 请求参数 `json`

```json
{
  "transfer_amount": 1000
}
```

| 参数名             | 类型     | 必填  | 描述   |
|-----------------|--------|-----|------|
| transfer_amount | number | ✔︎  | 划转金额 |

- 成功返回示例 `json`

```json
{
  "data": true
}
```

| 参数名  | 类型      | 描述     |
|------|---------|--------|
| data | boolean | 是否划转成功 |
