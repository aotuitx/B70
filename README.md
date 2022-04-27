### 路由管理地址：http://openwrt.lan 或者 http://10.0.0.1

### 用户名：root   密码： password

### 无线名称无密码：Openwrt 

![image](https://github.com/aotuitx/B70/blob/main/Images/Router1.png?raw=true)

### Bypass + AdGuard Home 的食用方法记录：

### 如果想一起用，首先 AdGuard Home 的转发端口不能用：53 ；如果不用Bypass，那端口是哪个就无所谓了。

### AdGuard Home 设置：

#### 1、先去 AdGuard Home 配置里把端口改成：5353 (本镜像已包含)

![image](https://github.com/aotuitx/B70/blob/main/Images/AdGuardHome1.png?raw=true)

#### 2、接着去 AdGuard Home 控制台---基本设置---5353重定向---重定向53端口到AdGuardHome，完事了保存，运行。

![image](https://github.com/aotuitx/B70/blob/main/Images/AdGuardHome2.png?raw=true)

### DHCP/DNS 设置：

#### 3、去 网络---DHCP/DNS---基本设置---DNS 转发 那里填上：127.0.0.1:5353（5353端口是AdGuard Home 的转发端口。）

![image](https://github.com/aotuitx/B70/blob/main/Images/DHCP.png?raw=true)

### Bypass 设置：

#### 如果启用 Bypass 直接按下图设置就行了，运行模式那里不要选：智能模式，这个模式总是搞成全局。

![image](https://github.com/aotuitx/B70/blob/main/Images/Bypass.png?raw=true)


### Credits
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub Actions](https://github.com/features/actions)
- [OpenWrt](https://github.com/openwrt/openwrt)
- [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)
- [tmate](https://github.com/tmate-io/tmate)
- [mxschmitt/action-tmate](https://github.com/mxschmitt/action-tmate)
- [csexton/debugger-action](https://github.com/csexton/debugger-action)
- [Cowtransfer](https://cowtransfer.com)
- [WeTransfer](https://wetransfer.com/)
- [Mikubill/transfer](https://github.com/Mikubill/transfer)
- [softprops/action-gh-release](https://github.com/softprops/action-gh-release)
- [ActionsRML/delete-workflow-runs](https://github.com/ActionsRML/delete-workflow-runs)
- [dev-drprasad/delete-older-releases](https://github.com/dev-drprasad/delete-older-releases)
- [peter-evans/repository-dispatch](https://github.com/peter-evans/repository-dispatch)


### 信息记录：
    自定义文件 “files 大法”是把你自定义的配置编译到固件里。这样升级或恢复出厂设置都不需要保留配置，缺省值就是自定义的配置。
    如你现在的network设置编译进固件：首先提取路由固件下的\etc\config\network 然后在项目根目录下创建files目录并push 到 \files\etc\config\network ，
    最后编译出来的固件就是现在设置的Network。
