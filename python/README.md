## 开发依赖

安装Web服务器框架`tornado`(实测版本为v4.5.2)
```
    pip install tornado
```

为了从IntoYun平台获取设备的实时数据并通过websocket协议推送到浏览器端, 我们需要安装如下的依赖
```
    pip install pycrypto
    pip install kafka-python
```

如果你当前使用的是Python2, 那么还需额外安装`futures`库
```
    pip install futures (for Python2)
```

如果你不想使用Cookie保存用户登录的信息，那么可以设置session存放到Redis中(可选，非必须)
```
    pip install redis (for Redis)
```


## 启动服务

- 替换configs/system.py文件中的`YOUR_DOMAIN_NAME`为你的域名或者IP地址(影响到VHOST和COOKIE_DOMAIN两个变量);
- 修改configs/system.py文件中的`PORT`变量，指定监听端口，默认使用8080端口;
- 替换configs/intoyun.py文件中的`YOUR_SERVER_AUTH_ID`和`YOUR_SERVER_AUTH_SECRET`为你的服务器授权标识和授权密钥;

启动服务: `python server.py`


## 测试功能

### 获取实时数据(Websocket)

- 安装依赖：
```
    pip install websocket-client
    pip install requests
```
- 进入test/wsClient目录;
- 替换wsClient.py文件中的`YOUR_DOMAIN_NAME`为你的服务器域名或者IP地址;
- 修改wsClient.py文件中的`port`变量，指定服务器使用的端口，默认为8080端口;

启动客户端: `python wsClient.py`


