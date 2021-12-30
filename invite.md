## 1.邀请码管理

> `GET` /user/invite/fetch

- 请求参数 `null`

- 成功返回示例 `json`

```json
{
  "data": {
    "codes": [
      {
        "id": 1,
        "user_id": 1,
        "code": "xxx",
        "status": 0,
        "pv": 0,
        "created_at": 1234567890,
        "updated_at": 1234567890
      }
    ],
    "stat": [
      0,
      0,
      0,
      15,
      0
    ]
  }
}
```

| 参数名              | 类型        | 描述     |
|------------------|-----------|--------|
| codes.id         | number    | 邀请码id  |
| codes.user_id    | number    | 用户id   |
| codes.code       | array     | 邀请码    |
| codes.status     | number    | 邀请码状态  |
| codes.pv         | number    | 访问量    |
| codes.created_at | timestamp | 创建时间   |
| codes.updated_at | timestamp | 更新时间   |
| stat[0]          | number    | 已注册用户数 |
| stat[1]          | number    | 有效的佣金  |
| stat[2]          | number    | 确认中的佣金 |
| stat[3]          | number    | 佣金比例   |
| stat[4]          | number    | 可用佣金   |

## 2.生成邀请码

> `GET` /user/invite/save

- 请求参数 `null`

- 成功返回示例 `json`

```json
{
  "data": true
}
```

| 参数名  | 类型      | 描述   |
|------|---------|------|
| data | boolean | 生成成功 |

## 3.邀请明细

> `GET` /user/invite/details

- 请求参数 `null`

- 成功返回示例 `json`

```json
{
  "id": 1,
  "commission_status": 1,
  "commission_balance": 10,
  "created_at": 1234567890,
  "updated_at": 1234567890
}
```

| 参数名                | 类型        | 描述                  |
|--------------------|-----------|---------------------|
| id                 | number    | 邀请id                |
| commission_status  | number    | 佣金状态 0待确认1发放中2有效3无效 |
| commission_balance | number    | 佣金                  |
| created_at         | timestamp | 创建时间                |
| updated_at         | timestamp | 更新时间                |