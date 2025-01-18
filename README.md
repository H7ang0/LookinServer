以下是更新后的 README 文件，加入了免越狱使用说明和 Telegram 群组信息：

LookinServer 插件调试 iOS UI

通过本项目，您可以使用 LookinServer 在 macOS 上调试 iOS 应用程序的界面。只需注入自签名的 LookinServer.dylib，即可快速启动调试模式，实时查看和修改应用的 UI 布局。

功能简介
	1.	实时调试 UI：支持在 macOS 上实时查看和调整 iOS 应用的界面布局。
	2.	零配置快速启动：只需注入动态库，打开 Lookin 即可开始调试。
	3.	免越狱支持：无需越狱设备，也可以通过开发者工具进行调试。

使用步骤

1. 下载 LookinServer.dylib

访问 Releases 页面，下载最新版本的 LookinServer.dylib 文件。

2. 自签名动态库

使用以下命令为动态库进行自签名：

codesign -f -s "你的签名证书名称" --entitlements entitlements.plist LookinServer.dylib

	如果尚未创建证书，请参考 如何生成 iOS 调试证书。

3. 注入动态库

将自签名的 LookinServer.dylib 注入到目标应用：

设备已越狱

使用以下命令注入动态库：

yololib TargetApp.app/TargetApp LookinServer.dylib

免越狱设备
	1.	将目标应用重新签名并注入动态库：

ipainject TargetApp.ipa LookinServer.dylib


	2.	使用开发者账号将修改后的应用安装到设备。

4. 启动 Lookin 调试
	1.	打开目标应用。
	2.	在 macOS 上启动 Lookin，自动检测并连接目标设备。
	3.	开始调试 UI。

注意事项
	1.	免越狱设备需要开发者账号和目标设备的信任配置。
	2.	注入后，可能影响应用的运行稳定性，仅限调试使用。
	3.	如果遇到连接问题，请检查设备网络和 Lookin 设置，确保在同一局域网内。

参与讨论

欢迎加入 Telegram 群组与我们交流：
👉 HyanguChat

开发者
	•	作者: Hyangu
	•	官网: youkebing.com
	•	联系邮箱: support@youkebing.com

尽情享受高效的 UI 调试体验！
