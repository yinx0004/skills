---
name: meeting-minutes
description: |
  Generate structured meeting minutes from a meeting transcript or recording text. Use this skill whenever the user provides any transcript, conversation log, or recording text and wants it turned into meeting minutes, a meeting summary, or a formal record of what was discussed. Trigger on: "生成会议纪要", "整理会议内容", "会议总结", "帮我整理一下这段会议", "根据文字稿生成纪要", "这是录音转文字，帮我整理", "meeting minutes", "summarize this meeting", or whenever the user pastes a block of text that looks like a spoken conversation or meeting transcript. Don't wait for the user to use exactly the right keywords — if they hand you a transcript and seem to want a formal document, use this skill.
---

# Meeting Minutes Generator

Your job is to transform a raw meeting transcript into a clean, professional set of meeting minutes. The transcript may be messy — filler words, crosstalk, repeated thoughts, informal speech — and your job is to distill it into something someone who wasn't in the room can act on.

## Step 1: Read the Entire Transcript First

Before writing anything, read the full transcript. You're trying to understand:
- Who was in the room and what their roles seem to be
- What the meeting was actually *for* — not just what was discussed, but why they gathered
- What was decided vs. what was merely floated
- What follow-up anyone committed to

Don't start extracting yet. Build a mental model first.

## Step 2: Clean the Input (Mentally, Not Literally)

You don't need to output a "cleaned transcript" — but as you read, filter out:
- Filler words: 嗯、啊、那个、就是、然后、对对对、好好好 / "um", "uh", "like", "you know"
- Repeated false starts: "I think we should — actually wait, I think we should..."
- Side chatter unrelated to the meeting topic
- Confirmations that add no information: "Yes, exactly, right, mhm"

The goal is to capture the *substance*, not the speech patterns.

## Step 3: Output the Meeting Minutes

Use this exact structure. If a field is genuinely unknown or not mentioned, write `（未提及）` or leave the cell blank — **never fabricate or guess**. A blank is always better than a wrong name or date.

---

# 会议纪要

## 基本信息

| 项目 | 内容 |
|------|------|
| 会议时间 | |
| 会议地点 | |
| 参会人员 | |
| 记录人 | |

## 会议目标

**背景：** （这次会议为什么召开？有什么前置背景或触发事件？）

**目的：** （希望通过这次会议达成什么？）

## 会议内容

按讨论主题分块呈现。每个主题下，概括讨论了什么、各方的核心观点是什么、有没有达成共识。

### 主题一：[主题名称]

[讨论内容摘要]

**各方观点：**
- [发言人]：[观点]
- [发言人]：[观点]

**结论/共识：** [如有]

### 主题二：[主题名称]

（根据实际内容添加更多主题，或删减至只有一个主题）

## 行动项

| 负责人 | 事项 | 截止时间 |
|--------|------|----------|
| | | |

## 备注

（其他需要记录的事项，或在会议纪要中需要特别说明的内容）

---

## Principles to follow

**Don't invent, don't omit what matters.** If someone's name wasn't mentioned, don't guess. If a deadline was mentioned, include it exactly as stated. If a decision was made, record it — even if it seems minor.

**Attribute viewpoints accurately.** When people disagreed, capture both sides. Don't flatten disagreement into a false consensus.

**Action items need an owner.** If someone said "we should do X" without naming a person, write "待定" as the owner rather than guessing. If a deadline was vague ("next week", "ASAP"), record it as-is — don't convert to a date you'd be guessing.

**Topic grouping over chronological order.** Meetings jump around. Group content by theme, not by the order things came up. If the same topic recurred in several parts of the transcript, merge them into one section.

**Chinese or English, match the transcript.** If the meeting was in Chinese, write the minutes in Chinese. If mixed, use Chinese as the primary language and keep key English terms (product names, technical terms) as-is.
