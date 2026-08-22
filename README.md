# 上下文感知会议纪要

> 这是一个脱敏案例，不包含真实逐字稿、客户名称、销售记录或内部文档。

我把团队的 CRM 销售日报作为业务上下文，构建了一套准确度更高的周会纪要工作流。

## 问题

通用 AI 总结虽然能维持固定格式，却容易写错陌生的客户、项目与学校名称，或将工作对应到错误的销售人员。多方人工复核抵消了许多提效价值。

## 我的改进

- 用可复用 Skill 统一会议纪要格式
- 引入 CRM 销售日报作为组织专属上下文
- 将提取出的实体与已知客户、项目交叉核验
- 校验销售人员与具体工作的对应关系
- 生成基本可直接提交、只需少量人工修改的纪要

## 工作流

```text
会议逐字稿 ─┐
             ├→ 上下文校验 → 结构化周会纪要
CRM 销售日报 ─┘
```

## 我的角色

我识别了模型缺少业务上下文这一根因，协调获取区域 CRM 导出，设计交叉校验流程，并围绕真实周会持续迭代 Skill。

## 公开范围

仓库当前用于呈现案例，后续将增加模拟逐字稿、CRM 数据和生成结果样例。


---

## English

# Context-Aware Meeting Notes

> A sanitized portfolio case study. No real transcripts, customer names, sales records, or internal documents are included.

I built a more reliable weekly meeting-minutes workflow by grounding transcript processing in the team's CRM sales reports.

## The problem

Generic AI summarization could preserve a meeting format, but it often misspelled unfamiliar customer, project, and school names or assigned work to the wrong salesperson. Manual cross-checking erased much of the efficiency gain.

## What I changed

- Standardized the minutes structure with a reusable skill
- Added CRM sales reports as organization-specific context
- Cross-checked extracted entities against known customers and projects
- Validated the mapping between salespeople and reported work
- Produced submission-ready minutes with much less manual correction

## Workflow

```text
Meeting transcript ─┐
                    ├→ Context validation → Structured weekly minutes
CRM sales reports ──┘
```

## My role

I identified the missing-context problem, coordinated access to the regional CRM export, designed the cross-validation workflow, and iterated the skill around real weekly usage.

## Public portfolio scope

This repository currently documents the case. Synthetic transcript and CRM examples plus a sample generated report are planned.
