# oto8进展

项目|任务|子任务|4月1周|4月2周|4月3周|4月4周|5月1周|5月2周|5月3周|5月4周|6月1周|6月2周|6月3周|6月4周
-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----
系统组||||||||||||
系统组||||||||||||
系统组||||||||||||
**多窗口组**||||||||||||
**多窗口**||||||||||||
||||||||||||
**应用适配**||||||||||||
**设置移植**||||||||||||
systemUI组||||||||||||
systemUI组||||||||||||
systemUI组||||||||||||
systemUI组||||||||||||
**应用组**|||||||||||||
**文件管理器**|云服务||||||||||
||网上邻居||||||||||
||回收站|||||||||||
||本地磁盘分区|||||||||||
||U盘|||||||||||
UI组||||||||||||
UI组||||||||||||
UI组||||||||||||
测试组||||||||||||
测试组||||||||||||
测试组||||||||||||
测试组||||||||||||



#### oto8界面
- UI界面，包括：开始菜单、任务栏、通知中心、窗口样式（重叠半透明模糊窗口，参照windows）等------------正在修改ui设计
- 当前分辨率过大


#### 多窗口
- 窗口最大化拖动标题栏变为小窗口------------正在改
- 全屏后再最大化，窗口会固定为全屏，无法变为窗口
- 部分应用强制竖屏全屏显示（比如剪绳子的广告）-----------需要和刘总确认需求
- 鼠标在窗口外较远的地方仍然可以拖动窗口-----------2019-03-08新增
- 应用适配
   - 微软office登录页面下窗口模式时没有标题栏
   - Sparkle Free在窗口模式下鼠标点击位置偏移
   - 2048左上角第一个方格总是显示被选中的蓝色，pcmark等应用也有此问题，oto2无此问题
   - 泰瑞呢、开心消消乐画面显示不全，默认窗口下一半不全的画面一半黑屏
   - 泰瑞呢、buttons and scissors、剪绳子、开心消消乐、模拟炒股、学堂在线等应用标题栏无手机桌面模式切换按钮
   - 狂野飙车8、央视影音、佳能打印打开闪退
   - bilibili首次打开时选择感兴趣的内容页面超出窗口

#### 设置
- 休眠后无法唤醒------------暂时使用临时方案：默认用不休眠；根本解决方案需要等待系统组配合
- 以太网、蓝牙、休眠、分辨率、云服务、打印等功能均未移植 -----------肖、张、苗在做 
   - 分析蓝牙扫描不到设备的原因-----------定位到问题出在HAL层,正在向黄Sir寻求帮助
   - 以太网系统底层支持------------肖已确认为UI层面的问题，需要等设置功能移植后解决
   - seafile demo及其依赖库移植到aosp8.1------------已完成，需要王之旭修改UI才能开始测试
   - 用C重新实现seaf-cli------------已完成，需要王之旭修改UI才能开始测试
- 系统软重启后无法连接wifi

#### systemUI
- 无法正常回到桌面-----------alt+tab返回桌面已解决，正在看任务栏返回桌面按钮
- 部分对话框无法点击（比如无法通过开始菜单的右键选项卸载应用）-----------正在看
- 通知中心下方的按钮除了设置以外均无效  
- 在任务栏固定4个图标然后重启，点击第一个图标再关闭，此时第一个图标变为白底-----------2019-03-11新增

#### 桌面
- 桌面上使用右键(点击空白或新建文件等)，整个屏幕会闪一下
- 桌面上对文字（比如回收站图标下的Recycle）使用右键会弹出两个右键菜单，一黑一白-----------2019-03-07新增

#### 其它应用
- 云服务移植的系统底层支持
   - seafile demo及其依赖库移植到aosp8.1-----------已完成，需要王之旭修改UI才能开始测试
   - 用C重新实现seaf-cli-----------已完成，需要王之旭修改UI才能开始测试
- 基于chrome的浏览器，要达到和基于firefox的相同效果
   - 完成了源码的下载、编译-----------已完成
   - 设置浏览器的默认页为openthos.org-----------30％
- 应用商店安装应用时卸载应用，系统会直接软重启
- 图片管理器无法正常查看图片，一直显示同一张图片
- 解决最新版微信的问题-----------已完成，待提交
- 微信弹出菜单位置不正确-----------已完成，待提交
- 快捷键功能移植  
- ota升级功能未移植  
- 首次配置未移植  
- 键盘映射未移植  
- 任务管理器未移植  
- 权限管理器未移植  
- 文本编辑器未移植  
- VLC未移植
- mopria打印功能未移植  
- 打开vpn后通知中心不断打开，提示google play服务请求，之后弹出google play屡次停止运行的提示-----------2019-03-08新增
- 自带的chrome浏览器在github上无法提交文档的修改，提示不支持浏览器-----------2019-03-08新增
- 无法通过adb命令连接到其它android设备（但可以ping通）-----------2019-03-08新增
- multiwindow合并到android8.1
   - 去掉ubuntu style initrd.img，直接从andriod init启动-----------可以启动,但屏幕无显示,正在分析原因
   
#### openthos cloud-----------[OPENTHOS云安卓端未完成项目列表](https://github.com/openthos/app-testing-results/blob/master/%E6%B5%8B%E8%AF%95%E5%86%85%E5%AE%B9%E5%8F%8A%E7%BB%93%E6%9E%9C/%E5%8A%9F%E8%83%BD%E6%B5%8B%E8%AF%95%E7%9B%B8%E5%85%B3/%E4%BA%91%E6%9C%8D%E5%8A%A1/OPENTHOS_CLOUD/android%E7%AB%AF%E6%9C%AA%E5%AE%8C%E6%88%90%E9%A1%B9%E7%9B%AE%E5%88%97%E8%A1%A8.md)
- 左侧资料库的右键菜单位置界面等仍需调整，此外点击“个人”选项应用会崩溃-----------待完成基本功能后再修改
