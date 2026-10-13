# Reelio 桌面端发布仓库

本仓库仅存放 Reelio 桌面端安装包与自动更新文件（由私有源码仓库的 CI 自动发布），不包含源代码。

## 📦 下载

前往 [Releases](https://github.com/P-an02/reelio-release/releases/latest) 下载适合你设备的安装包：

| 你的设备 | 文件 |
| --- | --- |
| 💻 Windows（64 位） | `reelio-<版本号>-Setup.exe` |
| 🍎 Mac（Intel 芯片） | `stable-macos-x64-reelio.dmg` |

**只下载安装包即可。** 同目录下的 `*.tar.zst` 与 `*-update.json` 是软件内「检查更新」自动下载用的，**不要删除**，否则自动更新会失败。

安装后可在应用内「检查更新」自动升级。

## 🚀 安装说明

- 💻 **Windows**：双击安装包，按提示完成安装。
- 🍎 **Mac**：打开 dmg，将 `reelio.app` 拖入“应用程序”，再从“应用程序”打开。

### macOS 提示“无法验证开发者”

本版 Mac 安装包未做开发者签名，首次打开会有安全提示，按以下顺序处理：

1. **先尝试打开一次** `reelio.app`，再前往「系统设置 → 隐私与安全性」，找到 Reelio 被阻止的提示，点击**「仍要打开」**并确认（[Apple 官方说明](https://support.apple.com/zh-cn/102445)）。
2. 若仍打不开，在终端执行：
   ```bash
   sudo xattr -rd com.apple.quarantine /Applications/reelio.app
   ```
3. 最后手段：终端执行 `sudo spctl --master-disable`，再在「隐私与安全性」中选「任何来源」。此操作会放宽所有 App 的安全限制，完成后建议改回“App Store 和被认可的开发者”。

> 🍎 **M 系列芯片**：当前为 Intel 包，首次运行会提示安装 Rosetta，允许即可。后续会提供签名版 Apple Silicon 安装包。
