# Project: [项目名称]

## Tech Stack
- **Framework:** Vue 3 (Vite)
- **UI Library:** Vant 4 (移动端适配)
- **Router:** Vue Router 4
- **PWA:** vite-plugin-pwa
- **Package Manager:** npm

## Design Standards

### Design Skill
所有 UI 实现必须使用 `superpowers:frontend-design` skill，确保设计质量。

### Design Language
- **风格:** Apple 设计风格 — 简洁、留白、圆角、轻量阴影
- **布局:** 卡片式布局为主，信息分组清晰
- **响应式:** 移动端优先（Mobile First），375px 基准，适配至 768px
- **动效:** 轻微过渡动画，不花哨，提升操作反馈感

### Visual Rules
- 圆角统一: 小元素 8px，卡片 12px，弹窗 16px
- 间距系统: 8px 倍数（8, 12, 16, 20, 24, 32）
- 字号层级: 标题 20px, 正文 14-16px, 辅助 12px
- 卡片必须有清晰的视觉边界（背景色差或轻阴影）
- 操作按钮在卡片底部，不超过 2 个主要操作

### Color System
在 `src/styles/theme.css` 中通过 CSS 变量定义，全局引用，禁止硬编码颜色值。

## Architecture

### Directory Structure
```
src/
├── views/          ← 页面（对应路由）
├── components/     ← 可复用组件
├── composables/    ← 组合式函数（业务逻辑）
├── services/       ← 数据服务层（API/缓存/降级）
├── mock/           ← Mock 数据（通过 VITE_USE_MOCK 切换）
├── utils/          ← 工具函数
├── styles/         ← 全局样式和主题变量
└── router/         ← 路由配置
```

### Architecture Rules
- **数据流:** views → composables → services → mock/API
- **组件原则:** views 负责布局和事件，components 是纯渲染器
- **环境切换:** `VITE_USE_MOCK=true` 走 Mock，`false` 走真实 API，切换对上层透明
- **样式隔离:** 组件使用 `<style scoped>`，全局变量在 theme.css

### Mirror Testing Rule
- `src/utils/*.js` → `tests/utils/*.test.js`
- `src/composables/*.js` → `tests/composables/*.test.js`
- `src/services/*.js` → `tests/services/*.test.js`

## Spec-to-Code Mapping

| Spec File | Source Modules | Purpose |
|-----------|----------------|---------|
<!-- 按实际模块填写 -->

## Project-Specific Requirements

<!-- 在此添加项目特定的业务规则 -->
