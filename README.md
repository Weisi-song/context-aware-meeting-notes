# 部门周会纪要助手

> 本仓库为项目脱敏展示版，不包含真实逐字稿、客户名称、销售记录或内部文档。

## 项目背景

部门每周一召开销售周会，回顾上周工作并确认本周计划。会后需要形成结构清楚、可以直接提交给领导的会议纪要。

用 AI 把逐字稿整理成固定格式并不难。真正棘手的是会议中会出现大量新客户、新项目和学校名称，而通用模型不了解公司的业务背景，很容易把专有名称听错、写错，或者把某项工作记到另一个销售名下。

## 第一版为什么不够

我最初做的 Skill 主要统一纪要结构，包括每位销售的上周进展、本周计划和需要跟进的事项。它解决了格式问题，但没有解决事实准确性：模型只能根据逐字稿猜测陌生名称。

如果最后仍要找销售、经理和记录人员逐项核对，AI 带来的效率提升就非常有限。因此我把问题重新定义为：不是“怎样总结得更好”，而是“怎样让 AI 获得足够的公司业务背景”。

## 我找到的新信息源

我发现销售每天都会在 CRM 中提交日报，其中已经包含他们拜访过的客户、正在推进的项目和对应关系。这些日报正好可以成为会议纪要的核对依据。

我主动联系 CRM 管理员，请他每周单独导出本区域的销售日报，再把日报作为背景材料接入会议纪要流程。

## 我做的流程

- 用固定模板整理每位销售的上周工作和本周计划
- 从逐字稿中提取客户、项目、学校、负责人和行动事项
- 用 CRM 日报核对名称是否存在、写法是否正确
- 检查具体工作与销售人员是否出现错配
- 对无法确认的内容保留提示，而不是让模型自行补全
- 输出基本可以直接提交、只需少量人工检查的周会纪要

## 系统如何运转

```text
会议逐字稿 ─────────┐
                    ├→ 提取人员、客户、项目和行动项
区域 CRM 销售日报 ──┘
                              ↓
                    名称核对 + 人员关系核对
                              ↓
                    按固定格式生成周会纪要
                              ↓
                        人工快速确认后提交
```

## 从反馈中怎么改

这套流程每周都会遇到新名称和新表达。我把实际使用中出现的错误持续归类：是名称本身没有背景、销售和项目关系判断错误，还是纪要结构没有准确体现团队习惯。随后针对性调整字段、校验顺序和 Prompt，而不是只在成品上逐字修改。

经理关注的是纪要能否准确反映团队工作并便于向上汇报，销售关注的是自己的客户和计划有没有被写错。这两个视角共同决定了最终输出标准。

## 我的角色

我主导完成了从 0 到 1 的整个过程：设计纪要 Skill、识别第一版的根本问题、寻找可用的内部信息源、协调 CRM 数据导出、设计交叉核对流程，并根据每周真实使用持续迭代。

CRM 管理员提供数据导出，经理和销售提供使用反馈；问题识别、产品方案、规则设计和最终落地由我负责。

## 带来的变化

原来最费时间的多方核对被压缩为最后的快速确认。现在把逐字稿和当周日报交给系统后，就能生成结构统一、客户和项目名称更可靠、人员对应关系更准确的会议纪要。

## 公开范围

公开仓库目前呈现案例和工作流。后续将加入模拟逐字稿、模拟销售日报、核对结果和最终纪要示例；真实会议与 CRM 数据保持私有。

---

## English

# Context-Aware Meeting Notes

> This is a sanitized portfolio case study. No real transcripts, customer names, sales records, or internal documents are included.

## Context

The department holds a sales meeting every Monday to review the previous week and confirm the next week's plan. The output must be a structured set of minutes ready for management.

Generic AI could organize the transcript, but unfamiliar customer, project, and school names were frequently misspelled or assigned to the wrong salesperson.

## Why the first version was insufficient

My first Skill standardized the format for previous-week progress, next-week plans, and follow-up actions. It solved structure but not factual accuracy because the model still had to guess unfamiliar names from the transcript alone.

I reframed the problem from better summarization to supplying the AI with reliable company context.

## The missing context source

Salespeople already submitted daily CRM reports containing the customers they had visited, projects they were pursuing, and the ownership relationships among them. I coordinated with the CRM administrator to export the regional reports each week and added them as grounding context.

## What I built

- A fixed structure for each salesperson's progress and plan
- Extraction of people, customers, projects, schools, and actions
- Name validation against CRM daily reports
- Validation of salesperson-to-project ownership
- Explicit uncertainty when information cannot be confirmed
- Submission-ready minutes requiring only a quick human check

## Workflow

```text
Meeting transcript ─┐
                    ├→ Extract people, entities, and actions
CRM daily reports ──┘
                              ↓
                     Validate names and ownership
                              ↓
                     Generate structured minutes
                              ↓
                         Quick human confirmation
```

## Feedback and iteration

Each week introduced new names and phrasing. I categorized real errors by missing entity context, incorrect ownership, or mismatch with the team's reporting structure, then changed fields, validation order, and prompts rather than manually repairing only the final text.

Managers cared about accurate team reporting; salespeople cared that their customers and plans were represented correctly. Both perspectives shaped the output standard.

## My role

I led the workflow from zero to one: designing the original Skill, diagnosing its fundamental limitation, finding an internal context source, coordinating CRM exports, building cross-validation, and iterating around weekly use.

The CRM administrator supplied exports and users supplied feedback; I owned the problem definition, product design, rules, and delivery.

## Outcome

Multi-person manual verification became a short final review. A transcript plus the week's CRM reports could now produce consistent minutes with more reliable names and ownership mappings.

## Public scope

This repository currently documents the case and workflow. Synthetic transcripts, CRM reports, validation examples, and output minutes are planned. Real meeting and CRM data remain private.
