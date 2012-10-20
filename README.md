# a2um 

基于nodeclub/nodejs的社区系统
服务密西根大学以及安娜堡周边的华人社区

# 以下是关于a2um的架构

## 介绍

Node Club 是用 **Node.js** 和 **MongoDB** 开发的新型社区软件，界面优雅，功能丰富，小巧迅速，
已在Node.js 中文技术社区 [CNode](http://cnodejs.org) 得到应用，但你完全可以用它搭建自己的社区。

## 安装部署

```bash
// install node npm mongodb
// run mongod
$ npm install
$ cp config.default.js config.js
// modify the config file as yours
$ node app.js
```

## TEST

```bash
$ make test
```

jscoverage

```bash
$ make test-cov
```

* test results: [test_results.md](https://github.com/cnodejs/nodeclub/blob/master/test_results.md)
* jscoverage: [**31%**](http://fengmk2.github.com/coverage/nodeclub.html)
    
## 其它

小量修改了两个依赖模块：node-markdown，express
 
* node-markdown/lib/markdown.js  

allowedTags 添加：

```
embed  //支持 flash 视频
table|thead|tbody|tr|td|th|caption  //支持表格
```
   
allowedAttributes 添加：

```
embed:'src|quality|width|height|align|allowScriptAccess|allowFullScreen|mode|type'
table: 'class'
```

* express/node_modules/connect/lib/middleware/csrf.js 添加：

```javascript
if (req.body && req.body.user_action === 'upload_image') return next();
```

## License

( The MIT License )

Copyright (c) 2012 muyuan, fengmk2 and other nodeclub contributors

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
