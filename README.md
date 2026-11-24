<div align="center">

# LumiVision · 机器视觉智能打光方案设计台

[![立即在线使用软件](https://img.shields.io/badge/立即在线使用-22d3ee?style=for-the-badge)](https://algsn1386.github.io/lumivision-lighting-advisor/)

[![答辩指挥中心](https://img.shields.io/badge/答辩指挥中心-a78bfa?style=for-the-badge)](https://algsn1386.github.io/lumivision-lighting-advisor/defense-command-center.html)

</div>

> 面向机器视觉工程的打光方案辅助决策工具。选择产品类型、表面特性与检测任务，规则引擎即可实时推荐最优光源方案，并给出光路结构示意、选型建议与调试要点。

纯前端单文件应用，**无需安装、无需联网、无需后端**，双击 HTML 即可在浏览器中运行。

---

## ✨ 功能特性

- **场景化配置**：8 类产品 × 6 种表面特性 × 6 类检测任务，覆盖常见工业视觉检测场景
- **智能方案推荐**：内置 7 类光源知识库与 0~3 评分矩阵，综合匹配度计算主推 / 备选方案
- **光路结构可视化**：动态绘制相机、光源、工件的相对位置示意图（SVG）
- **成像效果预览**：模拟不同打光方式下的成像差异
- **专业选型建议**：输出光源型号、波长颜色、偏振片建议、滤光片、镜头配置
- **调试要点提示**：针对镜面眩光、颜色检测等场景给出实操注意事项
- **快速预设**：内置 5 个典型检测场景（镜面金属划痕、玻璃瓶字符、PCB 元件定位等），一键演示
- **方案导出**：支持一键复制方案文本、打印 / 导出 PDF
- **深色科技风界面**：响应式布局，适配不同屏幕尺寸

## 🚀 快速开始

直接用浏览器打开 `machine-vision-lighting-advisor.html` 即可使用。

如需在线访问，可在本仓库启用 **GitHub Pages**（Settings → Pages → Deploy from a branch → main），然后通过以下地址查看：

```
https://<你的用户名>.github.io/<仓库名>/machine-vision-lighting-advisor.html
```

## 🧠 推荐逻辑

引擎根据三类输入对每种光源评分：

| 输入维度 | 说明 |
| --- | --- |
| 产品类型 | 金属、玻璃、塑料、PCB、印刷、薄膜、陶瓷、食品 |
| 表面特性 | 镜面高反光、半光泽、粗糙漫反射、透明、凹凸纹理、深色吸光 |
| 检测任务 | 缺陷划痕、尺寸测量、字符 OCR、颜色色差、定位计数、3D 轮廓 |

每类光源在「表面适配度」和「任务适配度」两个评分矩阵上打分，加权求和后排序，得出主推方案与备选方案，再结合成像参数（视场 FOV、工作距离 WD、产线速度）给出修正建议。

内置光源知识库：同轴光、低角度环形光、穹顶积分球光、背光源、环形光、条形光、多色 / 三色光。

## 📁 项目结构

```
.
├── machine-vision-lighting-advisor.html   # 核心应用：智能打光方案设计台
├── defense-command-center.html            # 附加：项目答辩指挥中心
└── README.md
```

> 应用图标与图形元素均以 SVG 内联实现，无需额外资源文件。

## 🛠️ 技术栈

纯 HTML + CSS + JavaScript，零依赖。所有图形与图标以内联 SVG 实现。

## 📄 License

本项目仅供学习与交流使用。
