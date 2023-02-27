# 仔细阅读！！！！

# 仔细阅读！！！！

# 仔细阅读！！！！

# 仔细阅读！！！！

# 仔细阅读！！！！

!!! 不要在这个项目上作业！
!!! Fork 一个自己的项目，在自己的项目上作业（点击左上角 Fork）
!!! 也可以自己创建 本地 vue 项目，提交 github 或者地址

# =================================================================

# 题目一：重构下面设计稿

### 设计稿

https://i.ibb.co/5vjC9Lw/We-Chat-Work-Screenshot-e8373491-b157-4954-9720-52b62b075ada.png

### 色彩

- #262F3E
- #C1C6C8

### ICON 字体或图片（可整个库引入）

- 箭头 https://fontawesome.com/icons/angle-down?s=solid&f=classic
- 邮箱 https://fontawesome.com/icons/envelope?s=regular&f=sharp
- 二维码 https://fontawesome.com/icons/qrcode?s=solid&f=sharp
- 头像 https://i.ibb.co/FJGtc8J/user-normal.png

### 要求

- header 高度为 64px
- 尽量还原设计稿

# 题目二：优化下面代码（需要完成使用 Promise 优化和 async/await 两种优化方式）

```js
axios.get('https://jsonplaceholder.typicode.com/posts/1', function (err, response1) {
  if (err) {
    console.error(err);
  } else {
    axios.get('https://jsonplaceholder.typicode.com/comments?postId=' + response1.data.id, function (err, response2) {
      if (err) {
        console.error(err);
      } else {
        axios.get('https://jsonplaceholder.typicode.com/users/' + response2.data[0].userId, function (err, response3) {
          if (err) {
            console.error(err);
          } else {
            axios.get('https://jsonplaceholder.typicode.com/todos?userId=' + response3.data.id, function (err, response4) {
              if (err) {
                console.error(err);
              } else {
                // Do something with the data
                const data1 = response1.data;
                const data2 = response2.data;
                const data3 = response3.data;
                const data4 = response4.data;
                const allData = [data1, data2, data3, data4];
                localStorage.setItem('allData', JSON.stringify(allData));
              }
            });
          }
        });
      }
    });
  }
});

```

# 题目三：Vue 项目题

1、使用 Vue2/3 创建的示例代码，包含了两个页面（Signup 和 NotFound），使用 Antdv 组件，并在路由进入之前需要调用一个 API 接口来验证用户的权限；

2、调用 API 时候需要在请求头 加入 `Authorization: Bearer xxxxxx`；

3、如果用户有权限访问（role = admin） Signup 页面，则继续渲染该页面，否则将其重定向到 NotFound 页面；

4、Signup 页面使用 Antdv 来实现两个 input， email 和 phone（只允许输入以 186、135 的 11 位数字输入），并且需要校验用户输入的合法性，当 input 失焦时去校验输入的合法性；

5、（加分项）通过 Vue3 + TS + Composition API 来实现。

### 下面是一些帮助信息

Antdv 组件地址：https://antdv.com/components/overview

模拟用户鉴权接口 https://your-api.com/user/role，返回

```json
{
  code: 200,
  msg: 'OK',
  data: {
    role: 'admin'
  }
}
```

# 题目四：JS 题目

实现一个方法 JS 方法，针对给定的两个数组进行去重并根据年龄分组

```js
// 例如输入：

const arr1 = [{name: 'Facebook', age: 24}, {name: 'Github', age: 18}, {name: 'OpenAI', age: 18}];
const arr2 = [{name: 'Google', age: 24}, {name: 'Copilot', age: 20}, {name: 'John', age: 24}];

console.log(groupByAge(arr1, arr2))

// 输出
{
    [
        {
            "name": "Github",
            "age": 18
        },
        {
            "name": "OpenAI",
            "age": 18
        }
    ],
    [
        {
            "name": "Copilot",
            "age": 20
        }
    ],
    [
        {
            "name": "Facebook",
            "age": 24
        },
        {
            "name": "Google",
            "age": 24
        }
    ]
}
```
