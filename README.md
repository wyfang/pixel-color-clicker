# 屏幕颜色触发点击器

适用于 macOS 与 Windows 11 的原生自动点击工具，在目标颜色匹配或监控区域变化时执行鼠标点击。

## 功能

- 监控 `1×1` 至 `10×10` 屏幕区域
- 匹配多个 `#RRGGBB` 目标颜色，或检测区域平均颜色变化
- 为每个目标设置延时、点击次数与间隔
- RGB 三通道容差可调
- 在监控位置或触发瞬间的鼠标位置点击
- 使用全局 `Esc` 紧急停止
- Windows 版支持全局启动热键、UAC 重启与参数持久化

颜色持续匹配时只触发一次；离开目标范围后再次匹配才会重新触发。延时期间颜色消失、切换或按下 `Esc` 会取消待执行点击。

## macOS

支持 macOS 13 或更高版本。首次使用需要授权：

- 屏幕录制：读取所选区域颜色
- 辅助功能：模拟点击并监听停止按键

源码构建只需要 Xcode Command Line Tools：

```bash
./build_app.sh
```

应用生成在 `outputs/像素变化点击器.app`。

## Windows 11

Windows 版本位于 `Windows11/`，需要 x64 .NET Desktop Runtime 10。GitHub Actions 会生成包含 `PixelColorClicker.exe` 与 `settings.json` 的发布目录。

## 使用边界

应用不连接网络，也不上传屏幕内容。请只在有权自动化的场景中使用；游戏、网站或服务可能禁止自动点击，应遵守其规则。

## 版权说明

原创代码依据 [Apache License 2.0](./LICENSE) 发布。个人品牌和素材不在许可范围内。
