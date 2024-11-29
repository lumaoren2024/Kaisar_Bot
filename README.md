# kaisar 自动挂机机器人教程
我的脚本key申请地址：https://lumao.us.kg/index.php

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
    "accounts": [
        {
            "email": "账号邮箱",
            "token": "第一步获取的token",
            "proxy_enabled": true, 这里是代理开关，你是要跑本地ip还是代理ip
            "proxy_type": "SOCKS5", 这里是http或者是socks5，记住全部大写
            "proxy_address": "127.0.0.1", 代理ip
            "proxy_port": 7890 端口
        },
        {
            "email": "账号2@gmail.com",
            "token": "ey.....",
            "proxy_enabled": false,
            "proxy_type": "HTTP",
            "proxy_address": "192.168.2.7",
            "proxy_port": 7890
        },
        {
            "email": "账号3@gmail.com",
            "token": "ey.....",
            "proxy_enabled": true,
            "proxy_type": "SOCKS5",
            "proxy_address": "FqqUB3CM2J9:2YvbWHLByMNZ@101.47.74.24",
            "proxy_port": 20000
        },
        {
            "email": "账号4@gmail.com",
            "token": "ey.....",
            "proxy_enabled": true,
            "proxy_type": "SOCKS5",
            "proxy_address": "xUmm1VuSlQJi:CJrzaAxcqGjz@101.47.140.112",
            "proxy_port": 20000
        }
    ]
}
```

## 3、玩法
我们通过json文件可以看到几个玩法
1、单号多ip
email和token不变。其他的变。
2、单号单ip
就是默认的配置了
3、多号多IP
复制多组{}然后直接按照单号多ip来写！




