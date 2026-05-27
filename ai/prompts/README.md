# Vue Team AI Prompt Workflow

This repository includes a set of AI prompt templates for Vue frontend teams.

These prompts are designed to help engineers use AI more consistently across planning, implementation, API integration, testing, review, and refactoring work.

## Prompt files

### 1. `ai/prompts/frontend-planner-vue.md`
Use this prompt when turning a product requirement into an implementation-ready frontend plan.

Best for:
- new feature planning
- frontend scope definition
- route/page impact analysis
- component and composable planning
- state and API planning

Typical input:
- PRD
- requirement summary
- product notes
- UX flow notes

Expected output:
- goal
- scope
- user flows
- route/page impact
- component plan
- composables plan
- state plan
- API plan
- UI states
- edge cases
- risks
- suggested tasks
- acceptance checklist

---

### 2. `ai/prompts/component-generator-vue.md`
Use this prompt when generating page/component scaffolding and implementation structure.

Best for:
- page skeleton design
- component breakdown
- props/emits/slots planning
- composables extraction planning
- state ownership design
- implementation task ordering

Typical input:
- frontend plan
- page description
- requirement details
- existing component patterns

Expected output:
- file plan
- component structure
- props/emits/slots plan
- composables plan
- state plan
- data/API plan
- interaction guidance
- UI states
- accessibility/i18n/analytics/responsive requirements
- suggested test cases

---

### 3. `ai/prompts/frontend-api-integrator-vue.md`
Use this prompt when integrating backend APIs into Vue pages or components.

Best for:
- request/response planning
- response mapping design
- loading/error/retry strategy
- state ownership around API calls
- async risk analysis

Typical input:
- API spec
- page requirement
- implementation summary
- backend field documentation

Expected output:
- integration goal
- API surface summary
- request/response assumptions
- data mapping plan
- state plan
- error and retry handling
- UI impact
- API layer organization
- test considerations
- risks and open questions

---

### 4. `ai/prompts/frontend-tester-vue.md`
Use this prompt when preparing frontend test coverage.

Best for:
- unit test planning
- component interaction test planning
- e2e scenario design
- regression checklist design
- async and edge case coverage

Typical input:
- requirement
- implementation summary
- component behavior description
- route/page behavior summary

Expected output:
- test goal
- test scope
- critical user flows
- unit test plan
- component test plan
- e2e test plan
- API/data considerations
- accessibility/i18n/analytics/responsive checks
- edge cases
- regression risks
- merge checklist

---

### 5. `ai/prompts/ui-reviewer-vue.md`
Use this prompt when reviewing Vue code changes before merge.

Best for:
- PR self-review
- reviewer checklist guidance
- Vue engineering quality checks
- component/state/composable review
- maintainability and async risk review

Typical input:
- PR diff
- code snippet
- implementation summary
- changed file list

Expected output:
- summary
- high priority findings
- medium priority suggestions
- Vue-specific review notes
- state/data flow review
- API/async review
- rendering/performance review
- accessibility/i18n/analytics/responsive review
- missing test cases
- merge checklist

---

### 6. `ai/prompts/refactor-assistant-vue.md`
Use this prompt when improving legacy Vue code in a safe and incremental way.

Best for:
- Options API migration planning
- large SFC split planning
- composable extraction planning
- store decoupling
- API/UI decoupling
- styling refactor analysis

Typical input:
- legacy component code
- refactor target description
- architecture pain points
- technical debt notes

Expected output:
- current problems
- refactor goals
- safe refactor strategy
- suggested split plan
- composables extraction opportunities
- state/store review
- API/async refactor opportunities
- styling refactor opportunities
- migration notes
- risks
- incremental task breakdown
- do not change yet

## Recommended workflow

### For new feature development
1. Start with `frontend-planner-vue.md`
2. Move to `component-generator-vue.md`
3. Use `frontend-api-integrator-vue.md` for backend integration details
4. Use `frontend-tester-vue.md` to prepare testing scope
5. Use `ui-reviewer-vue.md` before merge

### For legacy page improvement
1. Start with `refactor-assistant-vue.md`
2. If scope changes, use `frontend-planner-vue.md`
3. Use `component-generator-vue.md` for the new component structure
4. Use `frontend-tester-vue.md` for regression coverage
5. Use `ui-reviewer-vue.md` before merge

## Suggested usage pattern

When using these prompts with AI tools, provide:
- clear requirement context
- current route/page context
- existing constraints
- API assumptions if known
- whether the task is new implementation, review, testing, or refactoring

The better the context, the more actionable the output.

## Team conventions recommendation

To get stable results, keep these conventions consistent in prompts and usage:
- Vue 3
- Composition API
- `<script setup>`
- prefer composables for reusable logic
- avoid unnecessary Pinia state
- keep templates simple
- keep API mapping outside UI components when practical
- always consider loading / empty / error / disabled states
- always consider accessibility, i18n, analytics, and responsive behavior

## Example usage

### Example 1: requirement planning
Use `frontend-planner-vue.md` with:
- feature requirement
- user story
- route context
- API assumptions

### Example 2: component generation
Use `component-generator-vue.md` with:
- approved frontend plan
- page/module requirements
- existing component conventions

### Example 3: PR review
Use `ui-reviewer-vue.md` with:
- PR diff
- changed files
- implementation summary

### Example 4: test planning
Use `frontend-tester-vue.md` with:
- feature summary
- component behavior
- API behavior
- edge cases to protect

## Notes
- These prompts are planning and review aids, not a replacement for engineering judgment.
- Prefer incremental delivery instead of asking AI for large one-shot implementations.
- If repository conventions change, update the prompt templates together.
