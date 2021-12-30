## 1.订阅商店列表

> `GET` /user/plan/fetch

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": [
    {
      "id": 1,
      "group_id": 1,
      "transfer_enable": 100,
      "name": "Plan name",
      "show": 1,
      "sort": null,
      "renew": 1,
      "content": "xxx",
      "month_price": 10,
      "quarter_price": null,
      "half_year_price": null,
      "year_price": 20000,
      "two_year_price": null,
      "three_year_price": null,
      "onetime_price": null,
      "reset_price": 1000,
      "reset_traffic_method": null,
      "created_at": 1234567890,
      "updated_at": 1234567890
    }
  ]
}
```

| 参数名                  | 类型        | 描述     |
|----------------------|-----------|--------|
| id                   | number    | 订阅id   |
| group_id             | number    | 权限组id  |
| transfer_enable      | number    | 可用流量   |
| name                 | string    | 套餐名称   |
| show                 | number    | 是否显示   |
| sort                 | string    | 分类     |
| renew                | number    | 开启续费   |
| content              | string    | 套餐描述   |
| month_price          | number    | 月付价格   |
| quarter_price        | number    | 季度价格   |
| half_year_price      | number    | 半年价格   |
| year_price           | number    | 年价格    |
| two_year_price       | number    | 两年价格   |
| three_year_price     | number    | 三年价格   |
| onetime_price        | number    | 一次性价格  |
| reset_price          | number    | 重置价格   |
| reset_traffic_method | number    | 重置流量方式 |
| created_at           | timestamp | 套餐创建时间 |
| updated_at           | timestamp | 套餐更新时间 |