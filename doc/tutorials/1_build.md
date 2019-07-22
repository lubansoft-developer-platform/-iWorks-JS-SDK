### 目录结构

```
/iWorks JS SDK
|
|----/sdk
|    |
|    |----lbsdk.min.js
|    |
|    \
|
|----/doc
|    |
|    |----index.html
|    |
|    \
|
|----/demo
|    |
|    |----/web
|    |    |
|    |    |----*.*
|    |    |
|    |    \
|    |
|    |----LdnExternalCommands.xml
|    |
|    |----/menupic
|    |    |
|    |    |----*.*
|    |    |
|    |    \
|    |
|    \
|
\
```
#### sdk
    sdk文件夹下存放了iWorks JS SDK 提供的所有js扩展库

- lbsdk.min.js

```ini
iWorks JS SDK主入口文件
```

#### doc
    doc文件夹下存放了iWorks JS SDK的离线版接口文档

- index.html

```ini
iWorks JS SDK离线版接口文档入口文件
```

#### demo
    demo文件夹中提供了基于iWorks JS SDK开发的示例demo

---
### 环境搭建

```javascript
1. 建立你自己的web project
2. 将sdk中的所有文件移动到你的project中，并确保他们位于相同的路径下
3. 在你的project中使用如下语句<script type='text/javascript' src='lbsdk.min.js'></script>将sdk库引入到你的project中
4. 将您的project文件夹移动到 `系统盘\Users\用户\AppData\Local\bim产品名称\ Extensions`下
5. 创建`LdnExternalCommands.xml`,设置菜单
6. 根据您的实际情况编写对应命令的引导页面
7. 运行iWorks.exe，并开启你的开发之旅
```

---
### 官方Demo使用

```javascript
1. 在 系统盘\Users\用户名\AppData\Local`路径下创建`\iWorks\Extensions\HelloWorld 文件夹。例如：C:\Users\ryan\AppData\Local\iWorks\Extensions\HelloWorld
2. 将demo文件夹下的所有文件直接复制到HelloWorld目录下
如:
/HelloWorld
|    |
|    |----/web
|    |    |
|    |    \
|    |
|    |----LdnExternalCommands.xml
|    |
|    |----/menupic
|    |    |
|    |    \
|    |
|    \
|
\
3. 运行iWorks.exe
```



