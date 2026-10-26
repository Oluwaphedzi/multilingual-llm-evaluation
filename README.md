# Multilingual LLM Evaluation

**Oluwafeyikemi Dahunsi**
AI Data Evaluator | LLM Response Reviewer | Yoruba, English, Korean & Nigerian Pidgin

Lagos, Nigeria | [Email](mailto:dahunsioluwafeyikemi@gmail.com) | [LinkedIn](https://linkedin.com/in/oluwafeyikemi-dahunsi)

---

## Project Overview

Standard LLM benchmarks often fail to capture the nuance of local languages and dialects. As an AI Data Evaluator with 5 years of experience in multilingual data annotation and linguistic QA, I created this portfolio project to demonstrate my method for scoring model responses in **Yoruba, English (Nigerian context), Korean, and Nigerian Pidgin**.

Responses are judged as a native speaker of that language and community would judge them, prioritizing cultural context over direct English translations.

> **Sample work:** The prompts, model responses, and scores in this repository were written for this portfolio to demonstrate my method. They are not client data and not output from a named model.

---

## The Rubric

Each response gets four scores from 1 to 5, plus a written rationale.

| Dimension | 5 means | 3 means | 1 means |
| --- | --- | --- | --- |
| **Fluency** | Natural grammar, spelling, tone marks and word order. Reads like a native writer. | Understandable, but with noticeable errors a native reader would correct. | Broken grammar or missing marks that change meaning. |
| **Cultural accuracy** | Names, customs, money, institutions and politeness levels fit the community. | Mostly fits, with one or two foreign or generic assumptions. | Imports foreign assumptions or offends through wrong register. |
| **Task accuracy** | Answers exactly what was asked, with correct facts. | Gets the main point but misses a detail or is partly wrong. | Misreads the question or states false facts. |
| **Register fit** | Formality matches the relationship in the prompt (elder, boss, friend). | Mostly right, with a slip in formality or a mixed level. | Wrong or mixed formality throughout. |

**Scoring rules**

- **Overall:** mean of the four scores.
- **Cap rule:** if Cultural accuracy or Task accuracy is 2 or below, the overall score is capped at 3.0. Good grammar should not average away a wrong fact or a cultural error.
- **One error, one dimension:** each error is scored under its primary dimension only, so it is never penalized twice.
- **Fix rule:** every score of 3 or below gets a written rationale and a suggested fix.
- **Flag:** any score of 2 or below is marked as a major issue.

---

## Worked Evaluations

### Case 1 · Yoruba

**Task:** Proverb explanation

**Prompt:**
> Ṣàlàyé òwe yìí, kí o sì sọ ìgbà tí a lè lò ó: “Àgbà kì í wà lọ́jà, kí orí ọmọ tuntun wọ́.”

**Model response (sample):**
> Owe yii tumo si pe agba ko gbodo wa ni oja nitori omo tuntun. A le lo o nigba ti eniyan ba fe so pe awon agba ni lati ma to awon omo sona.

| Fluency | Cultural | Task | Register | Overall |
| --- | --- | --- | --- | --- |
| 2/5 (major issue) | 3/5 | 3/5 | 4/5 | **3.0** |

**Rationale:**
The model gets the moral right: elders are responsible for guiding the young. The literal reading is shaky, because the proverb is about an elder who is present and watching so that a newborn's head is shaped properly, not about elders being forbidden from the market. That error is scored under Task accuracy. All tone marks and under-dots are missing, which makes words like *agba* and *owe* ambiguous. That is scored under Fluency, which drops to 2.

**Suggested fix:** Restore diacritics and explain the image of the elder who stays present to guide a child.

### Case 2 · English (Nigerian context)

**Task:** Tenancy message

**Prompt:**
> Write a polite message to my landlord in Ibadan asking to pay the remaining rent two weeks late.

**Model response (sample):**
> Dear Landlord, I hope you are well. I am writing to request a two-week extension on my remaining rent. I will send the full amount by Zelle on the new date. Thank you for your understanding.

| Fluency | Cultural | Task | Register | Overall |
| --- | --- | --- | --- | --- |
| 5/5 | 2/5 (major issue) | 4/5 | 3/5 | **3.0** (capped from 3.5) |

**Rationale:**
The English is clean. Zelle is not available in Nigeria, and a Nigerian tenant would offer a bank transfer; this is scored under Cultural accuracy. The greeting is scored separately under Register: "Dear Landlord" feels cold for this relationship, where a respectful form such as "Good afternoon, Sir/Ma" is normal. Task accuracy loses one point because the message never names the new payment date. The cultural error triggers the cap rule, so the overall score is held at 3.0 even though the mean is 3.5.

**Suggested fix:** Replace Zelle with "bank transfer", add a respectful greeting and name the new date.

### Case 3 · Korean

**Task:** Workplace etiquette

**Prompt:**
> 부장님이 회식에 오라고 하셨는데 가기 어려워요. 정중하게 거절하는 방법을 알려 주세요.

**Model response (sample):**
> 이렇게 말해 보세요. “부장님, 초대해 주셔서 감사합니다. 죄송하지만 개인 사정이 있어 이번에는 참석하기 어려울 것 같습니다. 다음에는 꼭 참석하겠습니다.” 가까운 동료에게는 “미안, 이번엔 못 가요”라고 해도 됩니다.

| Fluency | Cultural | Task | Register | Overall |
| --- | --- | --- | --- | --- |
| 5/5 | 5/5 | 5/5 | 3/5 | **4.5** |

**Rationale:**
The main script to the boss is correct: it thanks, apologizes, gives a vague reason and promises next time, which is the expected pattern. The last sentence mixes casual "미안" with polite "-요", an uneasy blend. Since the problem is formality level, not grammar, it is scored once, under Register.

**Suggested fix:** Use "미안해요, 이번엔 못 갈 것 같아요" for close colleagues, or keep one consistent level.

### Case 4 · Nigerian Pidgin

**Task:** Slang explanation

**Prompt:**
> Explain wetin "japa" mean for Pidgin, make e simple.

**Model response (sample):**
> "Japa" mean say person don run comot from Nigeria go abroad to find better life. Plenty people dey japa because of work, school or the way things dey hard for house. Furthermore, e don turn big matter for Naija.

| Fluency | Cultural | Task | Register | Overall |
| --- | --- | --- | --- | --- |
| 5/5 | 5/5 | 5/5 | 4/5 | **4.8** |

**Rationale:**
The meaning of *japa* as emigrating in search of a better life is correct and the Pidgin is mostly natural. "Furthermore" is a formal, textbook English connector that breaks the spoken feel of Pidgin. It is a register problem, so it is scored once, under Register.

**Suggested fix:** Replace "Furthermore" with "And", or "Even so".

---

## Summary of Per-Case Scores

These are scores from one sample case per language. They illustrate the method and are not a ranking of how well models handle each language.

| Language | Fluency | Cultural | Task | Register | Overall |
| --- | --- | --- | --- | --- | --- |
| Yoruba | 2 | 3 | 3 | 4 | **3.0** |
| English (NG) | 5 | 2 | 4 | 3 | **3.0** (capped) |
| Korean | 5 | 5 | 5 | 3 | **4.5** |
| Pidgin | 5 | 5 | 5 | 4 | **4.8** |

**Observation:**
In these samples, the Yoruba response failed on orthography (missing tone marks) and the English response failed on borrowed cultural assumptions (Zelle). Both are errors that fluent-looking output can hide from a reviewer who does not speak the language or know the context, which is why I evaluate as a native speaker.

---

*Methodology: rubric scoring with a written rationale and suggested fix for every score of 3 or below. Scores of 2 or below are flagged as major issues.*
