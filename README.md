## @hyoga/uni-socket

项目源自：[weapp.socket.io](https://github.com/10cella/weapp.socket.io)，该项目作者已经两年没有维护，出现bug无法修复。

最近需要在uni-app中用到socket.io，遇到bug没有人修复很是头疼，所以基于weapp.socket.io新起一个项目。

### 介绍

重写socket.io-client的engin.io-client处理件，h5依旧使用原生WebSocket，APP与小程序使用uni-app的WebSocket协议，所以h5端任然可以支持长轮询等方式，APP与小程序只能支持WebSocket协议。

### 安装

```
// 建议使用npm或yarn包形式引入以保证插件的更新迭代
npm i @hyoga/uni-socket.io --save
// yarn add @hyoga/uni-socket.io
```

### 使用

```
import io from '@hyoga/uni-socket.io';
// import io from '/yourpath/uni-socket.io'; //直接引入文件方式

io('your websocket path', {
  query: {},
  transports: [ 'websocket', 'polling' ],
  timeout: 5000,
});

socket.on('connect', () => {
  console.log('ws 已连接);
});

socket.on('error', (msg: any) => {
  console.log('ws error', msg);
});
```

更多使用方法，请参考[socket.io-client](https://github.com/socketio/socket.io-client)写法即可。

### API

参考[官网API](https://socket.io/docs/client-api/)