### frontend前端接口 

> 项目前端文档接口说明



[TOC]



### 用户登录

> user/login.do 

+ 参数

  - username 	必填	用户名
  - password      必填        密码

+ 返回值

  - 正确

    ```
    {
        "status": 0,
        "msg": "登录成功",
        "data": {
            "id": 22,
            "username": "chencong",
            "password": "",
            "email": "",
            "phone": "",
            "question": "问题",
            "answer": "答案",
            "role": 1,
            "createTime": 1519781140000,
            "updateTime": 1519782351000
        }
    }
    ```

  - 错误

    ```
    {
        "status": 1,
        "msg": "密码错误"
    }
    ```

    

### 用户注册

> user/register.do 

+ 参数

  - username   用户名
  - password    密码
  - email           邮箱
  - phone         电话
  - question    问题
  - answer       答案

+ 返回值

  - 正确

  ```
  {
      "status": 0,
      "msg": "注册成功"
  }
  ```

  - 用户名已存在

  ```
  {
      "status": 1,
      "msg": "用户名已存在"
  }
  ```



### 登出

> user/logout.do 

+ 参数 

  > 无

+ 返回值

  - 正确

    ```
    {
        "status": 0
    }
    ```

    

### 字段检查

> user/check_valid.do 

+ 参数

  - str      字段
  - type    类型

+ 返回值

  - 正确

  > 用户名

  ```
  {
      "status": 1,
      "msg": "用户名已存在"
  }
  ```

  > 邮箱

  ```
  {
      "status": 1,
      "msg": "email已存在"
  }
  ```

  - 错误

  >用户名

  ```
  {
      "status": 0,
      "msg": "校验成功"
  }
  ```

  > 邮箱

  ```
  {
      "status": 0,
      "msg": "校验成功"
  }
  ```

### 获取用户信息

> user/get_user_info.do 

+ 参数

  > 无

+ 返回值

  - 正确

  ```
  {
  "status": 0,
  "data": {
  "id": 25,
  "username": "scx",
  "password": "",
  "email": "scx@qq.com",
  "phone": "1521111111",
  "question": "问题",
  "answer": "答案",
  "role": 0,
  "createTime": 1525658607000,
  "updateTime": 1525658607000
  }
  }
  ```

  - 错误

  ```
  {"status":1,"msg":"用户未登录,无法获取当前用户的信息"}
  ```

### 用户密保问题

> user/forget_get_question.do 

+ 参数

  - username        用户名

+ 返回值

  - 正确

  ```
  {
      "status": 0,
      "data": "问题"
  }
  ```

  - 错误

  ```
  {
      "status": 1,
      "msg": "用户不存在"
  }
  ```

### 用户密保问题检测

>user/forget_check_answer.do 

+ 参数

  - username       用户名
  - question         问题
  - answer            答案

+ 返回值

  - 正确

  ```
  {
      "status": 0,
      "data": "73143b22-ae59-45fb-b14e-18a7886585e3"
  }
  ```

  - 错误

  ```
  {
      "status": 1,
      "msg": "问题的答案错误"
  }
  ```

### 重置密码（未登录）

> user/forget_reset_password.do 

+ 参数

  - username            用户名
  - passwordNew     新密码
  - forgetToken         返回数据

+ 返回值

  - 正确

  ```
  {
      "status": 0,
      "msg": "修改密码成功"
  }
  ```

  - 错误

  ```
  {
      "status": 1,
      "msg": "token错误,请重新获取重置密码的token"
  }
  ```

### 重置密码（已登录）

> user/reset_password.do 

+ 参数

  - passwordOld          原有密码
  - passwordNew         新密码

+ 返回值

  - 正确

  ```
  {"status":0,"msg":"密码更新成功"}
  ```

  - 错误

  ```
  {
      "status": 1,
      "msg": "用户未登录"
  }
  ```

### 信息更新

> user/update_information.do 

- 参数
  - username   用户名
  - password    密码
  - email           邮箱
  - phone         电话
  - question    问题
  - answer       答案
- 返回值

### 获取用户信息

> user/get_information.do 

+ 参数

  > 无

+ 返回值

  - 正确

  ```
  {
  "status": 0,
  "data": {
  "id": 25,
  "username": "scx",
  "password": "",
  "email": "scx@qq.com",
  "phone": "1521111111",
  "question": "问题",
  "answer": "答案",
  "role": 0,
  "createTime": 1525658607000,
  "updateTime": 1525658607000
  }
  }
  ```

  - 错误

  ```
  {
      "status": 10,
      "msg": "未登录,需要强制登录status=10"
  }
  ```

  