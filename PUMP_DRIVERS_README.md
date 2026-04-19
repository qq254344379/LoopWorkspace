# ApexKitBLE & EmbectaKitBLE - 泵驱动说明

## 新增驱动

本分支在 `v3.12.1` 基础上新增了两个胰岛素泵驱动：

### ApexKitBLE（艾普泰克泵）
- **大小**: ApexKitBLE.framework (1.9MB) + ApexKitBLEPlugin.framework (180KB)
- **功能**: 艾普泰克胰岛素泵 BLE 蓝牙驱动
- **类结构**: ApexKitPumpManager, BluetoothManager, ApexEncryption, ApexUICoordinator 等
- **支持**: 完整泵管理（基础率、大剂量、报警等）
- **多语言**: 中文(zh-Hans)、英文

### EmbectaKitBLE（原 BD 泵）
- **大小**: EmbectaKitBLE.framework (2.0MB) + EmbectaKitBLEPlugin.framework (180KB)
- **功能**: Embecta（原 BD）胰岛素泵 BLE 蓝牙驱动
- **类结构**: EmbectaKitPumpManager, BluetoothManager, EmbectaEncryption 等
- **多语言**: 中文(zh-Hans)、英文

## 驱动来源

这两个驱动从定制版 Loop IPA (v3.12.1) 中提取，原作者：
- **作者**: Randall Knutson (rebelning)
- **创建日期**: 2024年3月31日
- **支持群**: https://loop.zulipchat.com/

## Xcode 项目说明

每个驱动包含：
- `ApexKitBLE/` - 主驱动 framework（含编译后的二进制）
- `ApexKitBLEPlugin/` - Xcode 插件 framework
- `project.yml` - XcodeGen 配置（用于生成项目）
- `ApexKitBLE.xcodeproj/` - Xcode 项目文件

## 使用方法

### 方法 1: 在 Xcode 中直接打开
1. Clone 本分支：`git clone --branch=pump-apex-embecta --recurse-submodules https://github.com/qq254344379/LoopWorkspace.git`
2. 打开 `LoopWorkspace.xcworkspace`
3. 在 Xcode 中添加 ApexKitBLE 和 EmbectaKitBLE 目标到 Loop 目标

### 方法 2: 使用 XcodeGen 重新生成项目
```bash
cd ApexKitBLE
xcodegen generate
xcodegen generate  # 运行两次
cd ..
open ApexKitBLE.xcodeproj
```

## 注意事项

⚠️ **重要**：
1. 这些是编译好的二进制 framework，不包含源码
2. 签名与你的 App 不匹配，需要重新签名或移除签名验证
3. Loop 主目标需要添加这两个 framework 的链接
4. Plugin 需要嵌入到主 App 的 Frameworks 中

## 构建步骤

1. 打开 `LoopWorkspace.xcworkspace`
2. 在 **Loop** 目标的 **General** → **Frameworks, Libraries, and Embedded Content** 中添加：
   - `ApexKitBLE.framework` (Embed: Do Not Embed)
   - `ApexKitBLEPlugin.framework` (Embed: Embed Without Signing)
   - `EmbectaKitBLE.framework` (Embed: Do Not Embed)
   - `EmbectaKitBLEPlugin.framework` (Embed: Embed Without Signing)
3. 在 **Build Phases** → **Link Binary With Libraries** 中添加上述 framework
4. 构建 Loop 目标

## 相关链接

- Loop 开源项目: https://github.com/LoopKit/Loop
- LoopWorkspace: https://github.com/LoopKit/LoopWorkspace
- Loop 文档: https://loopkit.github.io/loopdocs/
- Loop Zulipchat: https://loop.zulipchat.com/
