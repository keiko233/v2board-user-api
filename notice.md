## 1.公告信息

> `GET` /user/notice/fetch

- 请求参数 `null`

- 成功返回示例 `json`

```json
{
  "data": [
    {
      "id": 1,
      "title": "xxx",
      "content": "xxx",
      "img_url": null,
      "created_at": 1234567890,
      "updated_at": 1234567890
    }
  ],
  "total": 1
}
```

| 参数名        | 类型        | 描述   |
|------------|-----------|------|
| id         | number    | 公告id |
| title      | string    | 标题   |
| content    | string    | 内容   |
| img_url    | timestamp | 背景图片 |
| created_at | timestamp | 创建   |
| updated_at | timestamp | 更新时间 |
| total      | number    | 总条数  |