# blind-date-coach

相亲到结婚的全流程决策教练。供 DSH / Claude 等支持 Agent Skills 的工具加载使用。

## 它是什么

一份**决策手册**，不是恋爱鸡汤，也不是红娘。

覆盖 **P0 入局 → P12 领证** 的完整链路，每个节点都有：判断问题、时限、唯一默认动作、退出路径。回答固定三段：你在哪个节点 → 判据与时限 → 默认动作 + 异常分支。

## 安装

放到下面任一位置，装载器会自动发现（DSH 支持热加载）：

```
~/.agents/skills/blind-date-coach/          # 全局
<项目>/.agents/skills/blind-date-coach/     # 项目级
```

目录名保持 `blind-date-coach`，里面直接是 `SKILL.md`。

## 结构

```
SKILL.md           路由、三段式、10 条 NEVER、边界
references/        16 份按需加载的参考
  decision-tree      P0–P12 节点与 X0–X10 退出
  preference-and-standards  盘点、三层清单、偏好迭代
  profile-and-channels / screening-and-declining  资料与入口
  first-date-playbook / conversation-bank         见面与话题
  traffic-lights / scoring-and-veto               判据与量化
  relationship-building                           相处与磨合
  followup-and-decision / marriage-prep           谈判与婚前
  special-cases / gender-and-power                例外与视角
  risk-and-safety / learning-loop                 安全与复盘
assets/            5 张可填写模板（档案、清单、评分、日志、偏好画像）
evals/             12 条用例（触发 / 密度 / 边界）
```

## 范围与边界

**覆盖**：P0 到 P12，含二婚带娃、异地、年龄差、父母反对、多线并行、爽约处理。

**不覆盖**（遇到转介，不硬答）：婚后生活、离婚与财产分割、法律文书起草、同性/性少数、跨国婚恋、生育治疗、心理疾病治疗、家暴后创伤修复。

## 自测

用 `evals/evals.json` 的 12 条跑触发与密度。重点守两条：

- **id 10**：被逼相亲 → 必须走 P0，不得直接进准备期
- **id 11**：离婚分财产 → 必须识别为越界并转介

## 版本

v1.0.0
