# Vue 团队 AI Prompt 使用说明

本目录提供一套面向 Vue 前端团队的 AI Prompt 模板。

它们的目标不是替代工程判断，而是帮助团队在需求拆解、组件设计、API 联调、测试规划、代码评审和渐进式重构中，更稳定地使用 AI。

---

## Prompt 清单

### 1. `frontend-planner-vue.md`
用于把产品需求转成可执行的前端方案。

适用场景：
- 新功能需求规划
- 页面/路由影响分析
- 组件拆分设计
- composables 拆分判断
- 状态管理与 API 组织方案

典型输入：
- PRD
- 需求摘要
- 产品说明
- 用户流程说明
- 交互设计备注

典型输出：
- 目标
- 范围
- 用户流程
- 路由/页面影响
- 组件方案
- composables 方案
- 状态方案
- API 方案
- UI 状态清单
- 边界情况
- 风险点
- 任务拆分
- 验收清单

---

### 2. `component-generator-vue.md`
用于生成 Vue 页面/组件骨架与实现结构。

适用场景：
- 页面骨架设计
- 组件树拆分
- props / emits / slots 设计
- composables 设计
- 状态边界设计
- 实现顺序规划

典型输入：
- 前端方案
- 页面描述
- 需求细节
- 现有组件规范

典型输出：
- 文件计划
- 组件结构
- props / emits / slots 方案
- composables 方案
- 状态方案
- 数据 / API 方案
- 模板与交互建议
- UI 状态说明
- 可访问性 / i18n / 埋点 / 响应式要求
- 建议测试点

---

### 3. `frontend-api-integrator-vue.md`
用于把后端 API 接入 Vue 页面或组件。

适用场景：
- API 请求设计
- 响应映射设计
- 错误 / 重试处理方案
- 接口状态管理设计
- 异步风险分析

典型输入：
- API 文档
- 页面需求
- 实现说明
- 后端字段说明

典型输出：
- 接入目标
- API 清单
- 请求/响应假设
- 数据映射方案
- 状态方案
- 错误与重试处理
- UI 影响说明
- API 层组织建议
- 测试注意点
- 风险与待确认项

---

### 4. `frontend-tester-vue.md`
用于规划前端测试方案。

适用场景：
- 单测规划
- 组件交互测试规划
- e2e 场景设计
- 回归测试清单设计
- 异步与边界情况覆盖

典型输入：
- 功能需求
- 实现说明
- 组件行为说明
- 页面行为摘要

典型输出：
- 测试目标
- 测试范围
- 核心用户流程
- 单测计划
- 组件测试计划
- e2e 计划
- API/数据测试注意点
- 可访问性 / i18n / 埋点 / 响应式检查点
- 边界情况
- 回归风险
- 合并前检查清单

---

### 5. `ui-reviewer-vue.md`
用于在合并前 review Vue 代码改动。

适用场景：
- PR 自检
- reviewer 检查辅助
- Vue 工程实践 review
- 组件 / 状态 / composable 设计 review
- 可维护性与异步风险 review

典型输入：
- PR diff
- 代码片段
- 实现摘要
- 改动文件列表

典型输出：
- 总结
- 高优先级问题
- 中优先级建议
- Vue 专项观察
- 状态/数据流 review
- API/异步 review
- 渲染/性能 review
- 可访问性 / i18n / 埋点 / 响应式 review
- 缺失测试点
- 合并前检查清单

---

### 6. `refactor-assistant-vue.md`
用于对老 Vue 代码做保守、渐进式重构建议。

适用场景：
- Options API 迁移规划
- 巨型 SFC 拆分
- composables 抽离规划
- store 解耦
- API/UI 解耦
- 样式重构分析

典型输入：
- 老组件代码
- 重构目标描述
- 架构问题说明
- 技术债说明

典型输出：
- 当前问题
- 重构目标
- 安全重构策略
- 拆分方案
- composables 抽取机会
- 状态/store 评审
- API/异步重构建议
- 样式重构建议
- 迁移注意点
- 风险清单
- 分步任务拆解
- 暂时不要动的部分

---

## 推荐工作流

### 新功能开发
1. 先使用 `frontend-planner-vue.md`
2. 再使用 `component-generator-vue.md`
3. 接口联调时使用 `frontend-api-integrator-vue.md`
4. 测试规划使用 `frontend-tester-vue.md`
5. 合并前使用 `ui-reviewer-vue.md`

### 老页面/老模块改造
1. 先使用 `refactor-assistant-vue.md`
2. 如果范围或结构变化较大，再使用 `frontend-planner-vue.md`
3. 再使用 `component-generator-vue.md`
4. 如果涉及接口改造，再使用 `frontend-api-integrator-vue.md`
5. 使用 `frontend-tester-vue.md` 做回归规划
6. 合并前使用 `ui-reviewer-vue.md`

---

## 如何使用

在使用这些 Prompt 时，建议尽量提供完整上下文：

- 需求���标
- 页面/路由背景
- 当前组件结构
- 现有技术限制
- API 假设
- 当前任务属于规划、实现、联调、测试、review 还是重构

上下文越完整，AI 输出越可执行。

---

## 推荐团队约定

为了获得更稳定的输出，建议团队围绕这些默认前提统一使用：

- Vue 3
- Composition API
- `<script setup>`
- 可复用逻辑优先抽 composables
- 避免不必要的 Pinia 全局状态
- 保持 template 简洁
- API 映射逻辑尽量不要直接塞进 UI 组件
- 默认补齐 loading / empty / error / disabled 状态
- 默认检查可访问性、i18n、埋点、响应式适配

---

## 示例用法

### 示例 1：需求拆解
使用 `frontend-planner-vue.md`，输入：
- 功能需求
- 用户故事
- 页面路由背景
- API 假设

### 示例 2：组件设计
使用 `component-generator-vue.md`，输入：
- 已确认的前端方案
- 页面/模块需求
- 现有组件规范

### 示例 3：接口联调
使用 `frontend-api-integrator-vue.md`，输入：
- 接口文档
- 前端页面需求
- 错误/权限处理假设

### 示例 4：PR Review
使用 `ui-reviewer-vue.md`，输入：
- PR diff
- 改动文件
- 实现摘要

### 示例 5：测试规划
使用 `frontend-tester-vue.md`，输入：
- 功能摘要
- UI 行为
- API 行为
- 关键回归风险

### 示例 6：重构规划
使用 `refactor-assistant-vue.md`，输入：
- 老组件代码
- 已知痛点
- 希望改进的范围

---

## 说明

- 这些 Prompt 更适合作为规划和评审辅助，而不是替代工程判断。
- 建议优先采用渐进式交付，而不是一次性让 AI 生成大而全实现。
- 如果团队规范发生变化，建议统一更新这批 Prompt。
- 建议保持各 Prompt 结构一致，降低团队学习成本。
