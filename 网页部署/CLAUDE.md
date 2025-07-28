# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个数学教学课程的静态网页项目，专注于小学数学计算应用题的教学。项目包含16个独立的HTML课程页面，涵盖从基础整数计算到复杂应用问题的完整教学体系。

## 项目结构

```
网页部署/
├── L01 整数巧算.html          # 第1讲：整数计算技巧
├── L02 等差数列.html          # 第2讲：等差数列概念和计算
├── L03 分数教学.html          # 第3讲：分数的认识及基本计算
├── L04 小数教学.html          # 第4讲：小数运算
├── L05 等量代换.html          # 第5讲：等量代换问题
├── L06 一元一次方程.html      # 第6讲：一元一次方程
├── L07 二元一次方程.html      # 第7讲：二元一次方程
├── L08 定义新运算.html        # 第8讲：定义新运算
├── L09 和差倍问题.html        # 第9讲：和差倍问题
├── L10 年龄问题.html          # 第10讲：年龄问题
├── L11 周期问题.html          # 第11讲：周期问题
├── L12 鸡兔同笼.html          # 第12讲：鸡兔同笼问题
├── L13 平均数问题.html        # 第13讲：平均数问题
├── L14 盈亏问题.html          # 第14讲：盈亏问题
├── L15 牛吃草问题.html        # 第15讲：牛吃草问题
└── L16 列方程解应用题.html    # 第16讲：列方程解应用题
```

## 技术架构

### 前端技术栈
- **HTML5**: 现代语义化标记
- **CSS3**: 响应式设计，使用CSS变量系统
- **JavaScript**: 原生ES6+，无框架依赖
- **Tailwind CSS**: 实用优先的CSS框架 (CDN: v2.2.19)
- **Font Awesome**: 图标库 (CDN: v6.4.0)
- **Animate.css**: CSS动画库 (CDN: v4.1.1)

### 数学公式渲染
- **MathJax 3**: 数学公式渲染引擎
- 支持LaTeX语法: `\(inline\)` 和 `\[display\]` 模式
- 配置支持中文环境和自定义样式

### 动画和交互
- **GSAP**: 高性能动画库 (v3.12.2)
- **ScrollTrigger**: 滚动触发动画
- **Typed.js**: 打字机效果 (v2.0.12)
- 自定义粒子动画系统

### 字体系统
- **主字体**: Noto Sans SC (Google Fonts)
- **辅助字体**: Noto Serif SC
- **fallback**: 系统中文字体栈

## 设计系统

### 色彩变量系统
```css
:root {
  --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  --accent-gradient: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  --dark-gradient: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
  --glass-effect: rgba(255, 255, 255, 0.1);
}
```

### 间距系统
基于黄金比例 (1.618) 的间距系统：
```css
--space-unit: 1.618rem;
--space-xs: calc(var(--space-unit) * 0.382);
--space-sm: calc(var(--space-unit) * 0.618);
--space-md: var(--space-unit);
--space-lg: calc(var(--space-unit) * 1.618);
--space-xl: calc(var(--space-unit) * 2.618);
```

### 动画系统
```css
--transition-smooth: cubic-bezier(0.4, 0, 0.2, 1);
--transition-bounce: cubic-bezier(0.68, -0.55, 0.265, 1.55);
```

## 核心功能特性

### 1. 双版本系统
每个课程页面包含：
- **学生版**: 仅显示题目，用于练习
- **教师版**: 包含详细解析、提示和教学指导
- 通过JavaScript动态切换显示内容

### 2. 响应式设计
- 移动优先设计原则
- 断点: 768px (tablet), 1024px (desktop)
- 所有组件都支持触摸交互

### 3. 交互功能
- 平滑滚动导航
- 进度条指示器
- 知识点卡片悬停效果
- 自测题目点击展开答案
- 主题切换 (深色/浅色模式)
- 返回顶部按钮

### 4. 教学特色功能
- **搭小桥方法**: 等差数列的可视化教学方法
- **概念卡片**: 知识点的模块化展示
- **范例讲解**: 循序渐进的例题系统
- **知识自测**: 交互式自测功能

## 页面结构模式

每个HTML文件遵循统一的结构模式：

```html
<!DOCTYPE html>
<html lang="zh-CN" class="scroll-smooth">
<head>
  <!-- Meta信息和SEO -->
  <!-- 样式框架链接 -->
  <!-- 字体系统 -->
  <!-- MathJax配置 -->
  <!-- 交互增强库 -->
  <!-- 内联样式系统 -->
</head>
<body>
  <!-- 进度指示器 -->
  <!-- Hero区域 (标题+动画背景) -->
  <!-- 知识导航区域 -->
  <!-- 技巧总结区域 -->
  <!-- 范例讲解区域 -->
  <!-- 知识自测区域 -->
  <!-- Footer -->
  <!-- 悬浮按钮 -->
  <!-- JavaScript功能 -->
</body>
</html>
```

## 开发和维护

### 本地开发
由于这是纯静态HTML项目，无需构建步骤：
1. 直接在浏览器中打开HTML文件
2. 使用Live Server等工具获得更好的开发体验
3. 所有依赖都通过CDN加载，确保网络连接

### 内容更新
- 数学公式使用MathJax LaTeX语法
- 新增范例需要同时创建学生版和教师版内容
- 保持一致的CSS类命名和结构模式

### 性能优化
- 所有外部资源都使用CDN
- 图片和媒体文件应该压缩优化
- CSS和JavaScript已经内联，减少HTTP请求
- 粒子动画使用requestAnimationFrame优化性能

### 教学内容特点
- 面向小学数学应用题教学
- 强调可视化和互动性
- 包含完整的教学解析
- 支持自主学习和课堂教学两种场景

## 品牌信息
- **作者**: 魔渊国际数学教研团队
- **联系方式**: 
  - 微信: MoYuanGuoJi
  - GitHub: github.com/usyd2020
  - 邮箱: 8ai4kid@gmail.com
- **版权**: © 2025 魔渊国际. 保留所有权利.