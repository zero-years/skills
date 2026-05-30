---
name: git-commit
description: Git 提交规范、先重置工作流程以及常用命令快速参考。针对任何与 Git 相关的问题（如提交、分支、重置、撤销、冲突等）均可触发此服务。
---

# Git 提交信息

## 概览

生成语义准确的提交信息。
当通用规范与仓库的提交规范冲突时，优先使用仓库规范。

## 工作流程

1. 先检查更改，再书写提交信息

2. 优先读取项目仓库中的规则，如果仓库中没有规则，则使用以下的规范书写提交信息

```
<type>(<scope>): <subject>
```

3. 选择最准确的 `type`
   优先读取仓库中的 type 类型，如果仓库中没有 type 类型，则 type 只能为:

```
feat 、fix 、style 、docs 、perf 、chore 、revert 、build 、refactor
```

4. 按 `Angular` 风格撰写 `subject。`
   保持祈使语气、语义具体、结尾不加句号。
   除非遇到专有名词、品牌名或标识符，否则 `type(scope):` 后的 subject 尽量使用小写开头。

5. 返回前先对照项目仓库自检，如果仓库没有自检规则，则按照以下规则自检:

- `subject` 长度必须在 `1-50` 个字符之间。
- 允许在 breaking change 中使用 `type!:` 与 `type(scope)!:`。
- `scope` 是可选的；如果不能提升可读性，就省略。
- 仅当本次提交确实是在回滚之前的提交时，才使用 `revert: ` 前缀。

## type 类型

| 类型       | 使用场景                                       |
| ---------- | ---------------------------------------------- |
| `feat`     | 新增分支或新增内容                             |
| `fix`      | 修复 bug 或 报错                               |
| `style`    | 修改样式，格式，不更改逻辑                     |
| `docs`     | 仅限修改文档                                   |
| `perf`     | 优化性能                                       |
| `chore`    | 无法找到具体类型的修改                         |
| `revert`   | 回滚修改或分支                                 |
| `build`    | 修改构建流程、打包逻辑、构建工具或依赖构建步骤 |
| `refactor` | 重构代码，不产生新的功能 和 修复问题代码       |

## subject 规范

- 使用 `type(scope): subject` 或 `type(scope)!: subject` 结构。
- 小写，无句号，祈使语气
- 保持简洁、易读
- 如果本次更改包含了多个内容，应通知拆分 commit
- 避免 `update file` 、`add file` 、`fix bug` 等空泛表达
- 仅当变更引入 breaking API、breaking behavior 或 breaking contract 时才使用 `!`。

## 案例

```
feat(auth): add JWT token refresh mechanism
```

```
fix: resolve race condition in database connection pool
```
