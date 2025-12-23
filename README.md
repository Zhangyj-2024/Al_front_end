# Three.js 手势驱动 3D 粒子系统

双手张合控制粒子群的缩放与扩散，UI 面板可切换爱心 / 花朵 / 土星 / 佛像 / 烟花造型，并可选粒子颜色，支持全屏按钮。

## 运行方式

需要本地静态服务器（浏览器出于安全策略，摄像头只允许 http/https）。

```bash
# 使用 npm 自带 http-server（如无可先安装）
cd threejs-hand-particles
npx http-server -p 5173
# 或：python -m http.server 5173
```

然后访问：`http://localhost:5173/`

首次进入浏览器会询问摄像头授权，允许即可。

## 手势交互
- 双手张开 → 粒子放大并扩散
- 双手合拢 → 粒子收缩并聚拢
- 无手时自动回到默认尺寸

## UI 控件
- 造型选择：爱心 / 花朵 / 土星 / 佛像 / 烟花
- 颜色：颜色选择器实时更新粒子颜色
- 粒子大小：滑杆调整点大小
- 全屏按钮：右上角 “全屏”

## 文件说明
- `index.html`：入口，加载 MediaPipe Hands、主模块
- `src/main.js`：Three.js 场景、手势映射、UI 控制
- `src/shapes.js`：各造型的点云采样生成器
- `src/styles.css`：界面样式

## 依赖（CDN）
- three.js
- lil-gui
- MediaPipe Hands & Camera Utils

## 调试提示
- 如果摄像头无法打开，检查浏览器是否允许访问摄像头，以及是否通过 http/https 打开页面。
- 性能不足时可在 `main.js` 中降低 `PARTICLE_COUNT`。
