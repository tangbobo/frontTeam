# Vue AI Prompts Quick Start

Use this quick guide to choose the right prompt for the task.

## By scenario

### I need to turn a requirement into a frontend plan
Use:
- `frontend-planner-vue.md`
- 中文：`frontend-planner-vue.zh-CN.md`

### I need to design page/component structure
Use:
- `component-generator-vue.md`
- 中文：`component-generator-vue.zh-CN.md`

### I need to plan backend API integration
Use:
- `frontend-api-integrator-vue.md`
- 中文：`frontend-api-integrator-vue.zh-CN.md`

### I need to plan tests
Use:
- `frontend-tester-vue.md`
- 中文：`frontend-tester-vue.zh-CN.md`

### I need to review a Vue implementation or PR
Use:
- `ui-reviewer-vue.md`
- 中文：`ui-reviewer-vue.zh-CN.md`

### I need to refactor legacy Vue code safely
Use:
- `refactor-assistant-vue.md`
- 中文：`refactor-assistant-vue.zh-CN.md`

## Recommended flows

### New feature
1. `frontend-planner-vue.md`
2. `component-generator-vue.md`
3. `frontend-api-integrator-vue.md`
4. `frontend-tester-vue.md`
5. `ui-reviewer-vue.md`

### Refactor existing page/module
1. `refactor-assistant-vue.md`
2. `frontend-planner-vue.md` if scope changes
3. `component-generator-vue.md`
4. `frontend-api-integrator-vue.md` if API changes are involved
5. `frontend-tester-vue.md`
6. `ui-reviewer-vue.md`

## Minimal input checklist

Before using a prompt, try to provide:
- task goal
- route/page context
- current component structure
- API assumptions
- constraints or existing conventions

Better context gives better output.
