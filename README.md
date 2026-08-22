# 销售周会纪要助手

> 这是一个脱敏案例，不包含真实逐字稿、客户名称、销售记录或内部文档。

我做了一套面向销售周会的会议纪要工具。它不只总结逐字稿，还会参考销售人员平时提交的 CRM 日报，核对客户、项目、学校名称以及对应的负责人，从而减少 AI 最容易出现的事实错误。

## 问题

用 AI 整理会议内容本身并不难，真正麻烦的是销售会提到大量新客户、新项目和学校名称。通用模型不了解这些内部信息，经常写错名称，甚至把某项工作记到另一个销售名下，最后仍要找多个人反复核对。

## 我的改进

- 用可复用的 Skill 固定周会纪要格式和整理规则
- 把团队的 CRM 销售日报接入整理流程
- 用日报中的客户和项目信息核对逐字稿
- 检查每项工作是否对应到正确的销售人员
- 输出基本可以直接提交、只需少量修改的会议纪要

## 工作流

```text
会议逐字稿 ─┐
             ├→ 上下文校验 → 结构化周会纪要
CRM 销售日报 ─┘
```

## 我的角色

我先发现问题并不在“总结能力”，而在于 AI 缺少公司的业务背景。随后我联系 CRM 管理员，每周获取区域销售日报，设计了逐字稿与日报交叉核对的流程，并根据真实周会中的错误持续调整这套 Skill。

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
