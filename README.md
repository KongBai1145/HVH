全网最小上号器 并开源!!!
无毒无害

如果报毒属于正常现象
主要原因：
1. 行为特征匹配木马模式 — 远程下载数据 → 关闭 Steam → 写 loginusers.vdf/local.vdf → DPAPI 加密写入。这正好是盗号木马的完整行为链。
2. 数字签名 — exe 没签名，报毒门槛低。
3. 单文件发布 — 所有 DLL 打包进 exe，沙盒里看起来更像恶意软件。
4. 无知名发行商 — 新 exe 没有信誉积累。
核心问题是 行为本身和木马一样，杀软只看行为不看意图。

# HVH.lat 上号器

最小化卡密 → Steam 登录工具。输入卡密，自动解析账号并写入本地 Steam 客户端。

## 使用

1. 运行 `HVH.exe`
2. 输入卡密，点击「登录 Steam」
3. 程序自动查找 Steam → 写入登录信息 → 可选手动/自动启动 Steam

## 构建

需要 .NET 8 SDK + Windows 10+。

```bash
dotnet publish SteamEyaLite/HVH.csproj -c Release -f net8.0-windows --self-contained false
```

输出在 `bin/Release/net8.0-windows/win-x64/publish/`

## 文件说明

| 文件 | 说明 |
|------|------|
| `Program.cs` | 主程序（UI + 网络 + Steam 操作） |
| `HVH.csproj` | 项目配置 |
| `icon.ico` | 应用程序图标 |

超低价黑卡 https://HVH.lat