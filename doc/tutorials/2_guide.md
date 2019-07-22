## 操作步骤

### 1. 创建扩展程序目录(必须)
- 在`系统盘\Users\用户名\AppData\Local`路径下创建`\iWorks\Extensions\插件名称`文件夹。例如：`C:\Users\ryan\AppData\Local\iWorks\Extensions\HelloWorld\`

### 2. 创建菜单按钮
在扩展程序目录，创建一个`LdnExternalCommands.xml`，例如:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<MENU>
	<TAB NAME="Demo测试">
		<BLOCK NAME="第一个测试" JSPLUGIN="{6660DBD9-4EDA-47B5-9189-EDD62B420723}">
			<BUTTON NAME="测点管理" TYPE="Button" PLUGIN="{6660DBD9-4EDA-47B5-9189-EDD62B420723}" USERGUID="GUID1" CMDNAME="测点管理" TIP="HelloWorld" IMAGE_LARGE="menupic\cost1.png" IMAGE_SMALL="" URL="web\html\index.html"/>
			<BUTTON NAME="预消警管理" TYPE="Button" PLUGIN="{6660DBD9-4EDA-47B5-9189-EDD62B420723}" USERGUID="GUID2" CMDNAME="预消警管理" TIP="HelloWorld" IMAGE_LARGE="menupic\cost1.png" IMAGE_SMALL="" URL="web\html\index2.html"/>
			<BUTTON NAME="工序管理" TYPE="Button" PLUGIN="{6660DBD9-4EDA-47B5-9189-EDD62B420723}" USERGUID="GUID3" CMDNAME="工序管理" TIP="HelloWorld" IMAGE_LARGE="menupic\cost1.png" IMAGE_SMALL="" URL="web\html\index3.html"/>
		</BLOCK>
	</TAB>
</MENU>
```
其中:
- 节点：
  - TAB:表示添加的页签
  - BLOCK：表示命令分组
  - BUTTON：表示命令

- 属性
  - JSPLUGIN、PLUGIN：表示SDK的别名，暂定为`{6660DBD9-4EDA-47B5-9189-EDD62B420723}`
  - TYPE：表示菜单按钮类型
  - NAME：表示命令名，平台显示使用
  - CMDNAME：表示命令名，平台内部使用
  - USERGUID：表示用户自定义字段，此字段+CMDNAME作为平台内命令的身份ID，建议此处采用GUID
  - IMAGE_LARGE：命令显示图标
  - URL：系统装载此命令的引导页面文件，此处是相对`扩展程序目录`的路径

### 3. 编写命令默认页面
- 页面的头部首先需要引入`lbsdk.min.js`（必须）
- 重写全局回调函数（必须）：
为了获取到平台实时反馈数据，需要重写callback模块中的全局回调函数，对应的接口在lbcallback.js中。
```javascript
initRecvdMsgCallback(onRecvdMsgCallBack, function(bRet) {
    if (bRet === true) {
        //初始化成功
    }
});

onRecvdMsgCallBack：详见lbcallback.js 的格式要求
```
- 设置调试模式
引入lbconfigApi.js，调用`setSystemMode`
