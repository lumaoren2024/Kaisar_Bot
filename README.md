# kaisar 自动挂机机器人教程
我的脚本key申请地址：https://lumao.us.kg/index.php
UUID生成网站：https://www.wetools.com/uuid
我的邀请连接：https://zero.kaisar.io/register?ref=EfNGVM999

## 1、获取token
进入https://zero.kaisar.io注册，并且登录。
在chrome下使用f12 进入开发者->控制台
```javascript
// 重写 fetch 方法来捕获请求并打印 Authorization 头
let originalFetch = window.fetch;
window.fetch = function(...args) {
  // 获取请求的 URL 和 headers
  const url = args[0];
  const options = args[1];

  // 打印请求的 URL 和请求头
  console.log('Request URL:', url);
  if (options && options.headers) {
    console.log('Request Headers:', options.headers);

    // 检查是否包含 Authorization 头
    const authorizationHeader = options.headers.get('Authorization');
    if (authorizationHeader) {
      console.log('Authorization Header:', authorizationHeader);
    } else {
      console.log('No Authorization Header found');
    }
  }

  // 调用原始的 fetch 方法
  return originalFetch.apply(this, args);
};
```
点击结果复制,我们只要Bearer后面的，然后放到config.json文件中，其他的修改相对应的配置！
```txt
Authorization: "Bearer ey..."
```

## 2、config.json 讲解
```json
{
    "tokens": [
        "eyJ...",
        "eyJ..."
    ],
    "ids": [
        "db9bb1ea-6d3d-4362-bc26-90a5c0084a81",
        "ee36eea5-21e0-45c7-b220-01574d782525"
    ],
    "proxies": [
        "http://127.0.0.1:7890",
        "http://127.0.0.1:7890"
    ]
}
```

## 3、玩法
我们通过json文件可以看到几个玩法

1、单号多ip

token不变。其他的变。

2、单号单ip

就是默认的配置了

3、多号多IP

复制多组{}然后直接按照单号多ip来写！




