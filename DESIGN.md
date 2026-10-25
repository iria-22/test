---
version: alpha
name: OC 角色银行设计系统
---

## Overview

「角色银行」是 OC 生态平台（参考《MVP_细化方案》与《OC生态平台项目方案》）的 Web Demo，面向 OC 主人管理自己的角色资产：档案、外貌锚点、视觉资产层、OC 生平、关系网与 AI 临摹拆解。

信息架构要点（2025 修订）：
- 导航只保留「主页 / 我的 OC / OC 生平 / 练习区」四个大模块，模板系统不作为独立板块。
- 相似度监测是系统内置程序：保存时自动运行，仅当综合相似度 ≥ 85%（1 级）或 ≥ 95%（2 级）时向用户发出提示，平时保持静默。
- 模板在「创建 OC」时三选一：系统基础模板 / 我的自创模板 / 模板社区，也可不套模板从空白档案开始。

设计基调：淡紫 + 浅蓝的柔和双主色，安静、专业、带一点创作平台的梦幻感，但不做卡通化处理。界面为高频操作型工作台（密度偏高），不做营销落地页。

- 主色：淡紫 `#7C6BE6`（导航激活、主按钮、强调渐变）
- 辅色：浅蓝 `#6FA9E4`（次级信息、图表/渐变收尾、标签）
- 底色：`#F7F6FC`；卡片纯白，边界用极淡紫灰线
- 中文优先字体栈，无 letter-spacing（CJK 排版规则）

## colors

- background: #F7F6FC
- surface: #FFFFFF
- surface-alt: #FBFAFF
- accent: #7C6BE6
- accent-deep: #5748C4
- accent-soft: #EFEBFF
- sky: #6FA9E4
- sky-soft: #E6F1FC
- line: #E7E3F6
- line-strong: #D6CFF0
- text: #2E2B45
- text-muted: #8A86A6
- success: #4FA88B
- warning: #D9925B
- danger: #D2607E

## typography

- font-family: "PingFang SC", "Noto Sans SC", "Source Han Sans SC", system-ui, sans-serif
- 页面标题 26px / 700；区块标题 15.5px / 700；正文 15px / 1.75；辅助 13px；最小字号 11.5px（仅用于徽标与刻度）
- CJK 不使用 letter-spacing；数字使用 tabular-nums

## rounded

- 基准半径 16px（卡片）
- 控件 11px；按钮 9px（小号）；胶囊 999px（搜索、标签、刻度）
- 头像 50%（圆形）或 12px（品牌标记）

## spacing

- 基准间距 16px，卡片内边距 18–20px，区块间距 16px
- 密度可调（--ocd-tweak-density），影响 gap 与部分内边距

## components

- 侧边导航：分组标签 + 图标 + 计数徽标；激活态同时使用底色、边框、字重与左侧强调条
- 顶栏：面包屑 + 标题 + 搜索胶囊 + 主操作按钮
- OC 卡片：渐变插画区 + 头像 + 名称/别名 + 简介 + 标签 + 权限与相似度元信息
- 锚点条目：左标签（76px）+ 右正文，浅底圆角行
- 相似度条：淡紫轨道 + 渐变填充，85% / 95% 处带刻度线与标注
- 徽标 chips：lav / sky / ok / warn / danger 五种语义色
- 时间轴：左侧渐变竖线 + 空心节点 + 卡片
- 模态表单：单列 + 必要处两列，底部操作条
- Toast：底部居中，深紫底白字
- 监测提示条（monitor-note）：内置监测的说明/结果条，蓝底=说明，橙底=1 级提示，粉底=2 级提示
- 模板来源切换（src-tabs）：分段控件 + 模板选项卡（tpl-option），社区模板以行式列表呈现并标注来源作者
