<div align="center">

<img src="assets/banner.svg" alt="Cuelara: AI toolkit and prompt book" width="100%" />

<br />

**An AI toolkit and prompt book that helps people get better results from AI.**
<br />
Designed, built and run end to end by one person: the product, the tools, the extension, the admin and the data.

<br />

[![Open the live site](https://img.shields.io/badge/%E2%86%92_Open_the_live_site-cuelara.com-4F46E5?style=for-the-badge&labelColor=1e1b4b)](https://cuelara.com)
[![Try the tools](https://img.shields.io/badge/Try_the_tools-10B981?style=for-the-badge&labelColor=064e3b)](https://cuelara.com/tools)
[![Prompt book](https://img.shields.io/badge/Prompt_book-F59E0B?style=for-the-badge&labelColor=78350f)](https://cuelara.com/cookbook)
[![Extension](https://img.shields.io/badge/Browser_extension-D946EF?style=for-the-badge&labelColor=701a75)](https://cuelara.com/extension)

</div>

---

> ### Professors and reviewers: want to read the code?
> The full source is available to academic reviewers. Send a short email with your GitHub username and I will add you as a collaborator with read access.
>
> [![Request access](https://img.shields.io/badge/Request_code_access-aliyanfaisal15%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:aliyanfaisal15@gmail.com?subject=Cuelara%20code%20access%20request&body=Hello%20Aliyan%2C%0A%0AI%20would%20like%20read%20access%20to%20the%20Cuelara%20repository.%0A%0AMy%20GitHub%20username%3A%20%0AMy%20name%20and%20institution%3A%20)

---

## In one minute

AI tools are only as good as the instructions they are given, and most people were never taught how to write them. The result is generic answers, wasted money and a lot of trial and error.

**Cuelara starts from the problem the person actually has**, in their own words, and puts the right tool in front of them. It is not one tool. It is a growing toolkit, a library of ready-made prompts, a browser extension and an API, behind one guided experience.

## The problems it solves

| What people say | What is really wrong | How Cuelara helps |
| --- | --- | --- |
| "The AI keeps giving me generic answers." | The prompt is vague or missing key details. | **Optimizer** rewrites it. **Score** shows what is weak. |
| "It ignores half of what I asked." | Instructions conflict or are ambiguous. | **Debugger** finds each flaw and how to fix it. |
| "I do not know how to ask for this." | A blank page is hard. | **Builder** and the **Prompt book** start you off. |
| "My prompts are long and expensive." | Wording is padded and repeats itself. | **Token Optimizer** shortens it. **Diff & Cost** proves the saving. |
| "My document is too big to paste." | Whole files waste tokens and cause mistakes. | **Context Extractor** pulls out just the relevant parts. |
| "I want something that looks like that website." | Design is hard to put into words. | **Site to Prompt** measures the real page and writes the prompt. |
| "I do not know which tool I need." | Too many options, no guidance. | **Guided start** matches your problem to the right tool. |

## The whole platform at a glance

```mermaid
flowchart TB
    subgraph PEOPLE["Who uses it"]
        P1["Everyday AI users"]:::in
        P2["Developers and builders"]:::in
        P3["Teams"]:::in
    end
    subgraph ENTRY["Ways in"]
        E1["The website"]:::in
        E2["Browser extension<br/>inside ChatGPT, Claude, Gemini"]:::in
        E3["MCP server and API<br/>for Claude, Cursor and apps"]:::in
    end
    subgraph CORE["The product"]
        direction TB
        H["Guided start<br/>describe your problem,<br/>get the right tool"]:::ai
        T["Toolkit<br/>build, fix, save tokens,<br/>add context"]:::ai
        B["Prompt book<br/>ready-made prompts<br/>and an editor"]:::ai
    end
    subgraph ACCOUNT["Accounts and plans"]
        A1["History and<br/>saved prompts"]:::out
        A2["Free and paid plans<br/>with daily limits"]:::out
        A3["Team workspaces<br/>and a shared library"]:::out
    end
    subgraph ADMIN["Behind the scenes"]
        D1["Admin back office<br/>tools, content, users, plans"]:::warn
        D2["Database<br/>and AI services"]:::warn
    end
    P1 --> E1
    P2 --> E2
    P2 --> E3
    P3 --> E1
    E1 --> H
    E2 --> T
    E3 --> T
    H --> T
    H --> B
    T --> A1
    B --> A1
    A1 --> A2
    A2 --> A3
    D1 --> T
    D1 --> B
    D2 --> T
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>Light boxes are what visitors touch, purple is the guided and AI-powered core, green is what an account adds, amber is what runs behind the scenes.</sub>

## How a visit starts

A visitor types their problem, or picks a common situation. If they type, Cuelara uses **text embeddings** to match the meaning of their words to the right tool and to any ready-made prompts that fit. If they pick a situation, they go straight to the tools for it.

```mermaid
flowchart LR
    A["Visitor describes a problem<br/>in plain words"]:::in --> B{{"Match by meaning<br/>using text embeddings"}}:::ai
    A2["...or picks a<br/>common situation"]:::in --> T
    B -->|"closest tool"| T["Best tool,<br/>runs on the same page"]:::out
    B -->|"closest prompts"| P["Ready-made prompts<br/>that fit"]:::out
    T --> R["Use the tool and<br/>get your results"]:::out
    P --> R
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** every tool description and every prompt in the book is turned into a meaning fingerprint (an embedding) once. The visitor's sentence gets one on request and the closest meaning wins, so nothing depends on exact keywords.</sub>

---

## The toolkit, tool by tool

Each tool is shown the same way: the pain it removes, the journey from input to result, and a line on how it works inside. The set of tools keeps growing; these are the current ones.

### 1. Prompt Builder

> **The pain:** You know what you want from the AI, but not how to ask for it, so you stare at an empty box.

**What you get:** Describe the idea in plain words and get a complete, structured prompt, written the way your chosen AI likes to be asked. &nbsp;[Try it live ↗](https://cuelara.com/tools/prompt-builder)

```mermaid
flowchart LR
    A["Your idea<br/>in plain words"]:::in --> B["Pick the AI,<br/>the use case<br/>and the detail"]:::in
    B --> C["Cuelara adds the writing<br/>rules for that AI"]:::ai
    C --> D["AI drafts a structured<br/>prompt"]:::ai
    D --> E["Ready-to-paste prompt"]:::out
    E --> F["Copy it, or send it on to<br/>Optimizer / Score / Shorten"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** each target AI has its own guidance: Claude gets XML-tagged sections, ChatGPT gets Markdown with numbered steps, coding editors get scope and acceptance criteria. Use cases (coding, writing, marketing, business, research) change which sections are included.</sub>

### 2. Prompt Template Generator

> **The pain:** A blank page is slow, and a template full of blanks is easy to leave half-filled.

**What you get:** Pick a ready-made prompt, fill in the highlighted blanks, add your own points, and copy a finished prompt in seconds. &nbsp;[Try it live ↗](https://cuelara.com/prompt-template-generator)

```mermaid
flowchart LR
    A["Pick a ready-made<br/>prompt from the book"]:::in --> B["Blanks are found<br/>and highlighted"]:::ai
    B --> C["You fill them in<br/>and choose options<br/>like tone and length"]:::in
    C --> D["You add your own<br/>extra points"]:::in
    D --> E["Finished prompt<br/>assembled instantly"]:::out
    E --> F["Copy"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** no AI call is involved: placeholders written as [WORDS IN CAPITALS] are detected by rules, and your choices are appended as a short requirements block. It is instant, free and works offline.</sub>

### 3. Site to Prompt

> **The pain:** You love how a website looks but cannot describe its design well enough for an AI to recreate it.

**What you get:** A design prompt that captures the real colours, fonts, spacing and layout, ready for tools like v0, Bolt, Claude or Midjourney. &nbsp;[Try it live ↗](https://cuelara.com/tools/site-to-prompt)

```mermaid
flowchart LR
    A["Open any website<br/>and click the Cuelara<br/>extension"]:::in --> B["The extension measures the<br/>real page: colours, fonts,<br/>sizes, spacing, layout"]:::in
    B --> C["Sent to Cuelara"]:::in
    C --> D["Colours ranked by how much<br/>they are really used<br/>brand colours picked out"]:::ai
    C --> E["Layout summarised in<br/>plain language, section<br/>by section"]:::ai
    D --> F["AI writes the<br/>design prompt"]:::ai
    E --> F
    F --> G["Paste into your AI<br/>design or coding tool"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** measuring happens in your own browser, so it sees the page as you see it, including pages behind a login. Colour and layout facts are computed by rules first, which keeps the AI step short, cheap and consistent.</sub>

### 4. Context Extractor

> **The pain:** Your document is too big to paste into the AI, and pasting all of it is expensive and invites made-up answers.

**What you get:** Upload a document, ask a question, and get only the passages that matter, ready to paste, with the tokens you saved. &nbsp;[Try it live ↗](https://cuelara.com/tools/context-extractor)

```mermaid
flowchart LR
    A["Upload a document<br/>PDF, Word, text, Markdown,<br/>CSV or JSON"]:::in --> B["Cuelara reads<br/>the text"]:::ai
    B --> C["Splits it into<br/>small passages"]:::ai
    C --> D["Turns each passage<br/>into a meaning fingerprint<br/>(embedding)"]:::ai
    E["You ask a question"]:::in --> F["The question gets<br/>a fingerprint too"]:::ai
    D --> G["Find the passages<br/>closest in meaning"]:::ai
    F --> G
    G --> H["Only the relevant parts,<br/>ready to paste"]:::out
    H --> I["Tokens saved<br/>shown to you"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** this is retrieval by meaning, not keyword search, so a question can find a passage that uses different words. Uploaded documents expire automatically and are cleaned up on later uploads.</sub>

### 5. Prompt Optimizer

> **The pain:** Your prompt is vague or messy, so the AI answers generically or off-target.

**What you get:** A rewritten prompt with a clear role, steps, constraints and an output format, streamed to you as it is written. &nbsp;[Try it live ↗](https://cuelara.com/tools/prompt-optimizer)

```mermaid
flowchart LR
    A["Paste the prompt<br/>that is not working"]:::in --> B["Choose a mode<br/>General, Coding, Writing,<br/>Business, Research"]:::in
    B --> C["Choose the detail<br/>Concise to Comprehensive"]:::in
    C --> D["AI rewrites it using a<br/>proven prompt structure"]:::ai
    D --> E["Result appears live,<br/>word by word"]:::out
    E --> F["Copy it, score it,<br/>or shorten it"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** each mode carries a hand-written example of a strong prompt in that field. They set the quality bar, but the AI writes a fresh prompt for your input instead of filling in a form.</sub>

### 6. Prompt Debugger

> **The pain:** The AI ignores part of your instructions, contradicts itself or behaves differently each time, and you cannot see why.

**What you get:** A report of what is wrong, how serious it is and exactly how to fix it, plus the checks your prompt already passes. &nbsp;[Try it live ↗](https://cuelara.com/tools/prompt-debugger)

```mermaid
flowchart LR
    A["Paste the prompt"]:::in --> B["Choose how strict<br/>Standard, High, Paranoid"]:::in
    B --> C["Choose a focus<br/>everything, contradictions,<br/>edge cases, bias and tone"]:::in
    C --> D["AI audits the prompt"]:::ai
    D --> E{"Clean report<br/>received?"}:::warn
    E -->|"no"| D
    E -->|"yes"| F["Issues marked critical<br/>or warning, each with<br/>an explanation and a fix"]:::out
    F --> G["Optional: rewrite the prompt<br/>with every fix applied"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** the audit must come back as a structured report; if it does not, it is asked again with a sharper reminder. The same engine also powers the public API.</sub>

### 7. Prompt Formatter

> **The pain:** Your prompt is one long wall of text that is hard to read, hard to edit and easy for the AI to misread.

**What you get:** The same prompt, organised into clear labelled sections in the format your AI prefers. &nbsp;[Try it live ↗](https://cuelara.com/tools/prompt-formatter)

```mermaid
flowchart LR
    A["Paste the<br/>wall of text"]:::in --> B["Choose a format<br/>Markdown, XML or JSON"]:::in
    B --> C["Choose indentation"]:::in
    C --> D["AI sorts it into sections<br/>role, task, constraints,<br/>output format"]:::ai
    D --> E["Clean, structured prompt"]:::out
    E --> F["Copy"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** XML suits Claude, Markdown suits most chat models, and JSON suits API use. Each format has its own strict output rules, so you do not get a mix of styles.</sub>

### 8. Intelligence Score

> **The pain:** You cannot tell if your prompt is any good until you have already sent it and been disappointed.

**What you get:** A 0 to 100 score for how clear, precise and efficient your prompt is, with a prioritised list of what to improve. &nbsp;[Try it live ↗](https://cuelara.com/tools/intelligence-score)

```mermaid
flowchart LR
    A["Paste the prompt"]:::in --> B["Choose how to judge it<br/>Standard, Strict (production)<br/>or Creative"]:::in
    B --> C["Choose the target AI"]:::in
    C --> D["AI judges three things<br/>clarity, precision, density"]:::ai
    D --> E["Overall score 0 to 100<br/>and a tier"]:::out
    D --> F["Recommendations ranked<br/>high, medium, low"]:::out
    F --> G["Fix them with the<br/>Optimizer"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** the same prompt can score differently under different criteria on purpose: a production pipeline needs strict output rules, while a creative brief should not be penalised for lacking them.</sub>

### 9. Token Optimizer

> **The pain:** Long prompts cost money on every call and can hit the AI's length limit.

**What you get:** A shorter prompt that keeps every instruction, with the real before-and-after token counts. &nbsp;[Try it live ↗](https://cuelara.com/tools/token-optimizer)

```mermaid
flowchart LR
    A["Paste a long prompt"]:::in --> B["Choose how hard to squeeze<br/>Low, Medium or Aggressive"]:::in
    B --> C["Choose whether to<br/>keep formatting"]:::in
    C --> D["AI compresses it"]:::ai
    D --> E{"Did it actually<br/>get shorter?"}:::warn
    E -->|"barely"| D
    E -->|"yes"| F["Real token count<br/>before and after"]:::out
    F --> G["Shorter prompt<br/>and the saving"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** levels aim for roughly 15 to 25 percent (Low), 35 to 45 percent (Medium) and 50 percent or more (Aggressive). Savings are measured with real token counting, not estimated, and one automatic retry happens if the first pass barely shrinks the prompt. The same engine is used by the MCP server.</sub>

### 10. Diff & Cost Estimate

> **The pain:** You rewrote a prompt but cannot see exactly what changed, or whether it really got cheaper.

**What you get:** A side-by-side comparison of two versions with the token difference and what each costs on popular AI models. &nbsp;[Try it live ↗](https://cuelara.com/tools/compare-estimate)

```mermaid
flowchart LR
    A["Original prompt"]:::in --> C["Side-by-side<br/>visual diff"]:::ai
    B["New version"]:::in --> C
    C --> D["Token count<br/>for each version"]:::ai
    D --> E["Cost on popular AI models<br/>using published prices"]:::ai
    E --> F["What changed, how many tokens<br/>and how much money it saves"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** prices come from each provider's published rates, kept in one table with the date they were last checked, so estimates stay honest and easy to update.</sub>

---

## The prompt book

**The pain:** people want a starting point, not a lecture on prompt writing.

A library of ready-made prompts for everyday jobs, each with a worked example. Visitors browse by category or search, open a prompt, press **Edit this prompt**, fill in the blanks and copy a finished version.

```mermaid
flowchart LR
    A["Browse by category,<br/>search, or arrive from<br/>the guided start"]:::in --> B["Open a prompt<br/>with a worked example"]:::in
    B --> C["Edit this prompt:<br/>fill in the blanks"]:::in
    C --> D["Finished prompt"]:::out
    D --> E["Copy it, or open it in<br/>the Template Generator"]:::out
    F["Admin adds or edits prompts"]:::warn --> G["Meaning fingerprint<br/>refreshed automatically"]:::ai
    G --> A
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** the library has its own keyword search, and each published prompt also carries a meaning fingerprint so the guided start can recommend it.</sub>

## The browser extension

**The pain:** switching tabs to improve a prompt breaks your flow.

A small button appears in the chat box on ChatGPT, Claude, Gemini and other AI sites. Pick a tool and the prompt is improved in place. The same extension powers **Site to Prompt**. Nothing is sent until the user chooses a tool, it works without an account, and it can be turned off for any site.

```mermaid
flowchart LR
    A["You type a prompt<br/>in ChatGPT, Claude or Gemini"]:::in --> B["Click the Cuelara button<br/>in the chat box"]:::in
    B --> C["Pick a tool<br/>optimize, build, shorten,<br/>format, debug"]:::in
    C --> D["Cuelara improves it"]:::ai
    D --> E["Your prompt is replaced<br/>in the chat box"]:::out
    F["Account connected?"]:::warn -->|"yes"| G["Higher plan limits"]:::out
    F -->|"no"| H["Works anyway<br/>with free limits"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

## For developers: MCP server and API

**The pain:** developers want these tools inside the AI apps and code they already use.

The same engines behind the web tools are available to **Claude, Cursor and other MCP clients**, and as a **REST API** for building, optimizing, debugging, formatting and compressing prompts.

```mermaid
flowchart LR
    A["Claude, Cursor<br/>or another MCP client"]:::in --> C["Personal access token"]:::warn
    B["Your own app<br/>calling the API"]:::in --> C
    C --> D["Same engines as the<br/>website tools"]:::ai
    D --> E["Result returned<br/>to your app or editor"]:::out
    C --> F["Plan limits<br/>and usage tracking"]:::warn
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

## Accounts, plans and teams

**The pain:** good prompts get lost in old chats, and teams keep rewriting the same ones.

```mermaid
flowchart LR
    A["Visit without an account"]:::in --> B["Free daily limits<br/>per tool"]:::warn
    C["Create an account"]:::in --> D["History of past runs<br/>and saved prompts"]:::out
    D --> E["Free or paid plan<br/>higher limits, more history"]:::out
    E --> F["Team workspace<br/>shared prompt library,<br/>activity and analytics"]:::out
    E --> G["Eligible plans can<br/>bring their own AI keys"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

## Behind the scenes: the admin back office

What visitors see is kept fresh from a simple admin area, without waiting for a new release.

```mermaid
flowchart LR
    A["Admin signs in"]:::warn --> B["Tools<br/>switch on or off, reorder,<br/>reword, no deploy"]:::warn
    A --> C["Content<br/>prompt book and blog"]:::warn
    A --> D["People and plans<br/>users, roles, subscriptions"]:::warn
    A --> E["Health<br/>errors, emails, messages,<br/>usage analytics"]:::warn
    B --> F["Menus, footer, homepage, sitemap<br/>and tool matching update everywhere"]:::out
    classDef in fill:#eef2ff,stroke:#6366f1,color:#1e1b4b
    classDef ai fill:#f5f3ff,stroke:#8b5cf6,color:#2e1065
    classDef out fill:#ecfdf5,stroke:#10b981,color:#064e3b
    classDef warn fill:#fffbeb,stroke:#f59e0b,color:#78350f
```

<sub>**Under the hood:** what a tool *is* (its page and behaviour) lives in code; what an admin may change (on or off, wording, order) lives in the database. If the database is unreachable the site falls back to safe defaults instead of an error page.</sub>

---

## What this project demonstrates

- **Product thinking:** a journey that starts from the user's problem instead of a list of features.
- **Applied AI:** meaning-based matching and retrieval, prompt design, real token accounting and cost-aware model use.
- **Full-stack delivery:** a public site, accounts and billing, an admin back office, a browser extension and an API, built and shipped by one person.
- **Data and operations:** careful, additive database changes on a live product, caching, and graceful failure.

---

<div align="center">

**Aliyan Faisal**

[![Email](https://img.shields.io/badge/Email-aliyanfaisal15%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:aliyanfaisal15@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-aliyanfaisal-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/aliyanfaisal)
[![Live site](https://img.shields.io/badge/Website-cuelara.com-4F46E5?style=flat-square&logo=googlechrome&logoColor=white)](https://cuelara.com)

<sub>© Aliyan Faisal. All rights reserved. This repository is an overview for viewing only. The Cuelara name, design and source code may not be copied, modified, redistributed or used without written permission.</sub>

</div>
