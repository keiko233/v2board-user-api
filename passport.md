## 1.获取配置

> `GET` /passport/comm/config

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": {
    "tos_url": "https://xxx.com",
    "is_email_verify": 0,
    "is_invite_force": 0,
    "email_whitelist_suffix": 0,
    "is_recaptcha": 0,
    "recaptcha_site_key": "xxx",
    "app_description": "Hallo!",
    "app_url": "https://xxx.com"
  }
}
```

| 参数名                    | 类型                 | 描述      |
|------------------------|--------------------|---------|
| tos_url                | string             | 条款链接    |
| is_email_verify        | number             | 邮件验证    |
| is_invite_force        | number             | 强制邀请注册  |
| email_whitelist_suffix | number or string[] | 邮件白名单后缀 |
| is_recaptcha           | number             | 人机验证    |
| recaptcha_site_key     | string             | 人机验证校验码 |
| app_description        | string             | 站点说明    |
| app_url                | string             | 站点地址    |

## 2.登入校验

> `GET` /passport/auth/check

- 请求参数
  `null`

- 成功返回示例 `json`

```json
{
  "data": {
    "is_login": false
  }
}
```

| 参数名      | 类型      | 描述   |
|----------|---------|------|
| is_login | boolean | 是否登入 |

## 3.登入账号

> `POST` /passport/auth/login

- 请求参数 `json`

```json
 {
  "email": "xxxx@xx.com",
  "password": "1234567890"
}
```

| 参数名      | 类型     | 必填  | 描述   |
|----------|--------|-----|------|
| email    | string | ✔︎  | 邮箱地址 |
| password | string | ✔︎  | 密码   |

- 成功返回示例 `json`

```json
{
  "data": {
    "token": "xxx",
    "auth_data": "xxx"
  }
}
```

| 参数名       | 类型     | 描述            |
|-----------|--------|---------------|
| token     | string | 用户 token      |
| auth_data | string | base64(邮箱:密码) |

## 4.发送邮箱验证码

> `POST` /passport/comm/sendEmailVerify

- 请求参数 `json`

```json
 {
  "email": "xxxx@xx.com"
}
```

| 参数名   | 类型     | 必填  | 描述   |
|-------|--------|-----|------|
| email | string | ✔︎  | 邮箱地址 |

- 成功返回示例 `json`

```json
{
  "data": true
}
```

| 参数名  | 类型      | 描述     |
|------|---------|--------|
| data | boolean | 是否发送成功 |

## 5.注册账号

> `POST` /passport/auth/register

- 请求参数 `json`

```json
 {
  "email": "xxxx@xx.com",
  "password": "123456789",
  "email_code": 333333,
  "invite_code": "",
  "recaptcha_data": ""
}
```

| 参数名            | 类型     | 必填  | 描述     |
|----------------|--------|-----|--------|
| email          | string | ✔︎  | 邮箱地址   |
| password       | string | ✔︎  | 密码     |
| email_code     | number | ✖︎  | 邮箱验证码  |
| invite_code    | string | ✖︎  | 邀请码    |
| recaptcha_data | string | ✖︎  | 人机验证数据 |

- 成功返回示例 `json`

```json
{
  "data": {
    "token": "xxx",
    "auth_data": "xxx"
  }
}
```

| 参数名       | 类型     | 描述            |
|-----------|--------|---------------|
| token     | string | 用户 token      |
| auth_data | string | base64(邮箱:密码) |

## 6.重置密码

> `POST` /passport/auth/forget

- 请求参数 `json`

```json
{
  "email": "xxxx@xx.com",
  "password": "123456789",
  "email_code": 333333
}
```

| 参数名        | 类型     | 必填  | 描述    |
|------------|--------|-----|-------|
| email      | string | ✔︎  | 邮箱地址  |
| email_code | number | ✔︎  | 邮箱验证码 |
| password   | string | ✔︎  | 用户密码  |

- 成功返回示例 `json`

```json
{
  "data": true
}
```

| 参数名  | 类型      | 描述     |
|------|---------|--------|
| data | boolean | 是否重置成功 |
