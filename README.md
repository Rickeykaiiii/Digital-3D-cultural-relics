# 赛博考古：三星堆数字遗产粒子系统

> 将 WebGL 视觉表现力、计算机视觉交互能力与 AI 生成内容相结合，打造沉浸式"赛博考古"体验。

[![Live Demo](https://img.shields.io/badge/demo-live-brightgreen)](https://rickeykaiii.github.io/Digital-3D-cultural-relics/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## 📖 项目简介

这是一个创新的 Web 应用，通过粒子系统将三星堆文物以数字化形式呈现。用户可以通过手势控制与 3D 模型进行实时交互，体验从混沌星云到文物实体的动态变形过程。

### 核心特性

- **🌌 粒子系统**：15 万个粒子，使用自定义 GLSL Shader 实现从混沌形态到文物形态的平滑变形
- **👋 手势识别**：基于 MediaPipe Hands 的实时手势控制，支持缩放、旋转、模型切换
- **🎨 双渲染模式**：粒子模式与实体网格模式无缝切换
- **📱 响应式设计**：完整的移动端适配，触摸友好的交互体验
- **✨ 后处理效果**：Bloom 发光效果，营造赛博朋克美学

## 🛠 技术栈

### 核心技术

- **Three.js** `v0.160.0` - WebGL 3D 渲染引擎
  - 粒子系统 (Points + ShaderMaterial)
  - OBJ/MTL 模型加载
  - 后处理 (UnrealBloomPass)
  - OrbitControls 相机控制

- **MediaPipe Hands** - 实时手势识别
  - 21 个手部关键点追踪
  - 双手检测支持
  - 自定义手势识别算法

- **Tailwind CSS** - 样式框架
  - 响应式布局
  - Glassmorphism UI 设计

### 开发工具

- 单文件架构 (index.html)
- ES6 模块化
- Google Fonts (Noto Serif SC + Orbitron)

## 🎮 手势控制

| 手势 | 功能 | 说明 |
|------|------|------|
| ✊ ↔ ✋ | 缩放 | 单手握拳最小，完全张开最大 |
| 👍 (1.5s) | 切换模型 | 竖大拇指持续 1.5 秒 |
| 👌 (2s) | 渲染模式 | OK 手势持续 2 秒，切换粒子/实体 |

## 📁 项目结构

```
Digital-3D-cultural-relics/
├── index.html                 # 主应用文件（包含所有 HTML/CSS/JS）
├── assets/
│   ├── objs/                  # 3D 模型文件
│   │   ├── standing-man.obj   # 青铜大立人像 (34MB)
│   │   ├── golden-mask.obj    # 金面罩青铜人头像 (34MB)
│   │   └── bronze-mask.obj    # 青铜大面具 (34MB)
│   ├── texture/               # PBR 材质纹理
│   │   ├── standing-man/
│   │   ├── golden-mask/
│   │   └── bronze-mask/
│   └── introduction/          # 文物简介文案
│       ├── standing-man.md
│       ├── golden-mask.md
│       └── bronze-mask.md
└── README.md
```

## 🚀 快速开始

### 本地运行

```bash
# 克隆仓库
git clone https://github.com/Rickeykaiiii/Digital-3D-cultural-relics.git
cd Digital-3D-cultural-relics

# 启动本地服务器（需要 HTTP 服务器以支持 ES6 模块）
python3 -m http.server 8000

# 访问 http://localhost:8000
```

### 在线体验

访问 [https://rickeykaiii.github.io/Digital-3D-cultural-relics/](https://rickeykaiii.github.io/Digital-3D-cultural-relics/)

## 🎨 视觉设计

- **配色方案**：深色背景 (#000406) + 青色/金色渐变
- **粒子颜色**：混沌状态（青色/蓝色）→ 文物状态（金色/铜色）
- **UI 风格**：Glassmorphism（玻璃态）+ 赛博朋克
- **字体**：Noto Serif SC（中文）+ Orbitron（英文/数字）

## 📊 性能优化

- **粒子数量**：150,000（兼顾视觉效果与性能）
- **移动端优化**：
  - 降低摄像头分辨率（240x180）
  - 使用轻量级手势识别模型（modelComplexity: 0）
  - 响应式 UI 布局
- **预加载机制**：页面显示前加载所有模型，避免切换延迟

## 🔧 配置参数

```javascript
CONFIG = {
  particleCount: 150000,        // 粒子数量
  gesture: {
    PINCH_THRESHOLD: 0.12,      // 捏合判定距离
    SCALE_MIN: 0.3,             // 最小缩放
    SCALE_MAX: 4.0,             // 最大缩放
  }
}
```

## 📝 开发日志

- **2026-03-17**: 添加移动端收起简介按钮
- **2026-03-17**: 修复实体模式下切换模型黑屏问题
- **2026-03-17**: 优化移动端体验（响应式布局 + 性能优化）
- **2026-03-17**: 新增青铜大面具模型
- **2026-03-17**: 实现模型预加载机制
- **2026-03-16**: 完成手势控制系统重构

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📄 许可证

MIT License

## 🙏 致谢

- 三星堆博物馆提供的文物资料
- Three.js 社区
- MediaPipe 团队
