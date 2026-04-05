# Keang Liu Portfolio — Design System & Rules

## About This Project
- 纯HTML/CSS/JS静态网站，无任何框架
- 部署到 GitHub Pages，域名 keangliu.com
- 文件结构：
  - index.html — 主页
  - casestudies.html — Case Studies子页面
  - icbsc.html — ICBSC竞赛子页面
  - volunteer.html — Volunteer子页面
  - free-resources.html — 资源下载页面

## About Keang
- UCR MBA Candidate，2026毕业
- 求职方向：Marketing Analyst / Digital Marketing / SEO Specialist
- 正在学习 vibe coding（用AI辅助前端开发）
- ICBSC竞赛担任CMO，创建了品牌 Citrion（citrion.site）
- Tableau Public: https://public.tableau.com/app/profile/keang.liu/vizzes

## Typography
- 标题字体：DM Serif Display（Google Fonts，支持italic斜体）
- 正文字体：DM Sans（Google Fonts，weight 300/400/500）
- 每个HTML文件的<head>必须引入：
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:ital,wght@0,300;0,400;0,500&display=swap" rel="stylesheet">
- 标题要大，line-height: 0.92，letter-spacing: -0.02em
- 正文 font-size: 14px，line-height: 1.8，font-weight: 300

## Color System
每个HTML文件的<style>开头必须定义这些CSS变量：

:root {
  --bg: #F7F5F0;        /* 主背景，米白色 */
  --ink: #1A1A18;       /* 主文字，近黑 */
  --muted: #AAAA98;     /* 次要文字 */
  --border: #E8E4DC;    /* 边框颜色 */
  --accent-1: #FF6B6B;  /* 珊瑚红，主强调色 */
  --accent-2: #FFD93D;  /* 明黄 */
  --accent-3: #6BCB77;  /* 活力绿 */
  --accent-4: #4D96FF;  /* 天蓝 */
  --warm: #C8B89A;      /* 暖金，次要装饰 */
  --white: #FFFFFF;
}

强调色（accent-1到4）只用于：标签pill、hover状态、小装饰元素
不要用强调色做大面积背景

## Layout & Spacing
- 页面左右padding: 56px（桌面端）
- Section之间间距：最少120px
- 内容最大宽度：1200px，居中
- 导航栏：固定顶部，logo左对齐，链接右对齐，背景半透明

## Navigation（所有页面统一）
<nav>结构：
- 左：Keang Liu（链接到index.html）
- 右：Work | Skills | Resources | Contact
- 字体：DM Sans 12px，letter-spacing 0.08em，uppercase
- 颜色：默认var(--muted)，hover变var(--ink)

## Hero Section（index.html）
- 大标题：DM Serif Display，italic，超大（clamp(64px, 9vw, 108px)）
- 副标题：DM Sans 13px，uppercase，letter-spacing 0.06em，颜色var(--muted)
- 浮动装饰元素：用SVG绘制，代表不同技能/项目，可拖动
- 背景：var(--bg)加细点阵纹理
- "Drag to explore"提示在左下角

## Floating Elements（Hero装饰）
用SVG绘制以下元素，加缓慢浮动动画（requestAnimationFrame）：
1. Bar chart → 代表Analytics能力
2. Browser mockup → 代表Citrion网站项目
3. Keyword pills → 代表SEO/SEM技能
4. MBA badge → 代表UCR MBA身份
5. Line chart → 代表Case Study数据分析

颜色风格：跳跃活泼，使用accent-1到4，参考portfoliobyshruti.com

## Sub-pages Style（casestudies/icbsc/volunteer页面）
参考ChronoTask landing page风格：
- 白色或var(--bg)背景
- 大量留白
- 内容卡片：白色背景 + 0.5px border（var(--border)）+ border-radius 12px
- 数据表格：clean样式，细边框，无花哨装饰
- 页面顶部有返回主页的链接

## Animation Rules
- 页面加载：元素用 opacity(0→1) + translateY(20px→0) 淡入
  duration: 0.6s，ease: cubic-bezier(0.16, 1, 0.3, 1)
  每个元素stagger: 0.1s delay
- Hover：transition 0.25s ease
- 浮动元素：requestAnimationFrame，振幅6-9px，周期3-5秒，每个元素相位不同

## DO NOT（禁止事项）
- 不用 Bootstrap、Tailwind、或任何CSS框架
- 不用彩虹渐变背景
- 不用玻璃拟态（backdrop-filter/glassmorphism）
- 不用紫色渐变（这是generic AI风格）
- 不用 border-radius 超过 12px 的大圆角
- 不用密集堆叠的内容
- 不用 Inter、Roboto、Arial 等generic字体
- 不用外部图片做装饰，用SVG代替

## Git & Deploy
- 每次改完后：git add . → git commit -m "描述" → git push
- push后1-2分钟自动部署到keangliu.com
