### 开发调试
- 在你的web project项目中，调用lbconfigApi.js模块下的setSystemMode接口
```javascript
<script>
    setSystemMode(ESystemMode.DebugMode);
</script>
```
- `ESystemMode.DebugMode`ESystemMode.DebugMode参数表示开启调试模式，此时，在命令页面单击右键，	在菜单中选择devTool，开启进程内调试工具
- `ESystemMode.ReleaseMode`参数表示关闭调试模式，此时，命令页面将不再弹出右	键菜单，平台默认ReleaseMode状态
