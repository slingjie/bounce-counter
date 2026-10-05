# 拍球计数器（Bounce Counter）

用手机麦克风识别拍球落地声、自动计数并语音报数的单文件网页工具，给小朋友练球用。

- GitHub Pages 在线地址：https://slingjie.github.io/bounce-counter/
- 在 iPhone Safari 打开 → 分享 → 添加到主屏幕，可作为 PWA 全屏独立运行（离线可用）。

## 技术说明

- 纯前端、零外部依赖：`index.html` 单文件（含检测核心），无 CDN、无后端。
- 检测链路：60–320Hz 低频能量门 → 起振时间/频谱质心初检 → 150ms 衰减校验 → 浊音否决（归一化自相关检语音周期性）。
- 源码与单测见 `../detector-core.js` / `../test-detector.cjs`（构建：`template.html` 中 `//__DETECTOR_CORE__` 占位替换）。

## 文件

| 文件 | 说明 |
|---|---|
| `index.html` | 页面本体（由 `../dist/index.html` 复制） |
| `manifest.json` | PWA manifest |
| `sw.js` | 离线缓存 Service Worker |
| `icon-192.png` / `icon-512.png` / `apple-touch-icon.png` | PWA 图标 |
