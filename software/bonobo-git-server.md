- 预装条件：https://bonobogitserver.com/prerequisites/
- 安装说明：https://bonobogitserver.com/install/

- 问题1：IIS部署
```bash
# 官网是安装到默认网站的应用程序，测试可直接发布为网站
# 设置IIS_USER用户拥有App_Data文件夹的控制权限
```
- 问题2：不能在此路径中使用此配置节
```bash
# 针对handlers节
%windir%\system32\inetsrv\appcmd unlock config -section:system.webServer/handlers
# 针对modules节
%windir%\system32\inetsrv\appcmd unlock config -section:system.webServer/modules
```
- Windows 10启用asp.net支持
```bash
Turn Windows Features on/off and under IIS
   -> World Wide Web Services
   -> Application Development Features.

打开windows功能 -> WWW/IIS -> 应用程序开发特征
```