<div align="center">

<img src="assets/banner.svg" alt="Cuelara: AI toolkit and prompt book" width="100%" />

<br />

**A full-stack AI platform I designed, built and run on my own.**
<br />
A growing toolkit, a searchable prompt library, a browser extension and an MCP server, behind one guided experience.

<br />

[![Open the live site](https://img.shields.io/badge/%E2%86%92_Open_the_live_site-cuelara.com-4F46E5?style=for-the-badge&labelColor=1e1b4b)](https://cuelara.com)
[![Try the tools](https://img.shields.io/badge/Try_the_tools-10B981?style=for-the-badge&labelColor=064e3b)](https://cuelara.com/tools)
[![Prompt book](https://img.shields.io/badge/Prompt_book-F59E0B?style=for-the-badge&labelColor=78350f)](https://cuelara.com/cookbook)
[![Extension](https://img.shields.io/badge/Browser_extension-D946EF?style=for-the-badge&labelColor=701a75)](https://cuelara.com/extension)

![Next.js](https://img.shields.io/badge/Next.js_16-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React_19-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma_7-2D3748?style=flat-square&logo=prisma&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind_4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-8E75B2?style=flat-square&logo=googlegemini&logoColor=white)

</div>

---

> ### Professors and reviewers: want to read the code?
> The full source is available to academic reviewers. Send a short email with your GitHub username and I will add you as a collaborator with read access, usually within a day.
>
> [![Request access](https://img.shields.io/badge/Request_code_access-aliyanfaisal15%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:aliyanfaisal15@gmail.com?subject=Cuelara%20code%20access%20request&body=Hello%20Aliyan%2C%0A%0AI%20would%20like%20read%20access%20to%20the%20Cuelara%20repository.%0A%0AMy%20GitHub%20username%3A%20%0AMy%20name%20and%20institution%3A%20)

---

## The idea

Most people get weak answers from AI because the prompt is weak, and they cannot tell what is wrong with it. Cuelara starts from the problem a person actually has, in their own words, and routes them to the right tool, which runs on the same page.

<table>
<tr>
<td width="25%" align="center"><h3>Fix</h3>Find out why a prompt fails and rewrite it</td>
<td width="25%" align="center"><h3>Build</h3>Turn a rough idea into a finished prompt</td>
<td width="25%" align="center"><h3>Save</h3>Cut tokens and cost without losing meaning</td>
<td width="25%" align="center"><h3>Add context</h3>Give the AI the right material to work from</td>
</tr>
</table>

## How a visit works

```mermaid
flowchart LR
    A["Visitor describes a problem<br/>in plain words"] --> B{"Match"}
    B -->|"text embeddings"| C["Best tool"]
    B -->|"semantic search"| D["Ready-made prompts"]
    C --> E["Runs on the same page"]
    D --> E
    E --> F["Copy the result, or send it<br/>on to another tool"]
```

Nothing in the matching is hard-coded to keywords: each tool and each prompt is embedded once, the visitor's sentence is embedded on request, and the closest meaning wins.

## What is inside

| | | |
|:--|:--|:--|
| **Guided homepage flow**<br/>Ask, match, run, in three steps. | **Toolkit**<br/>Tools grouped by the job they do: build, fix, save, add context. It keeps growing. | **Prompt book**<br/>Searchable prompts with worked examples and a fill-in-the-blanks editor. |
| **Browser extension**<br/>Improve a prompt in place on ChatGPT, Claude, Gemini and more. | **MCP server**<br/>Use the toolkit from Claude, Cursor and other MCP clients. | **Admin back office**<br/>Users, plans, roles, content and per-tool on/off, order and wording, with no deploy. |

<details>
<summary><b>See the current tools</b> (the list grows over time)</summary>

<br />

| Job | Tool | What it does |
| --- | --- | --- |
| Build | [Prompt Builder](https://cuelara.com/tools/prompt-builder) | Turns an idea into a complete, ready-to-paste prompt |
| Build | [Prompt Template Generator](https://cuelara.com/prompt-template-generator) | Fill in a ready-made template and copy a finished prompt |
| Fix | [Prompt Optimizer](https://cuelara.com/tools/prompt-optimizer) | Rewrites a vague prompt so the AI understands it |
| Fix | [Prompt Debugger](https://cuelara.com/tools/prompt-debugger) | Finds contradictions, gaps and ambiguity |
| Fix | [Prompt Formatter](https://cuelara.com/tools/prompt-formatter) | Structures a wall of text into clean Markdown, XML or JSON |
| Fix | [Intelligence Score](https://cuelara.com/tools/intelligence-score) | Grades a prompt from 0 to 100 and says what to improve |
| Save | [Token Optimizer](https://cuelara.com/tools/token-optimizer) | Shortens a prompt, checked against real token counts |
| Save | [Diff & Cost Estimate](https://cuelara.com/tools/compare-estimate) | Compares two versions and shows the token and cost difference |
| Context | [Context Extractor](https://cuelara.com/tools/context-extractor) | Pulls only the relevant parts out of large documents |
| Context | [Site to Prompt](https://cuelara.com/tools/site-to-prompt) | Turns a website's design into a prompt that recreates it |

</details>

## Architecture at a glance

```mermaid
flowchart TB
    subgraph Client["Browser"]
        W["Next.js 16 / React 19 site"]
        X["Browser extension"]
        M["MCP clients"]
    end
    subgraph Server["Next.js server"]
        R["Route handlers and server actions"]
        T["Tool registry + admin settings"]
        Q["Matching: embeddings and ranking"]
    end
    subgraph Data["Data and services"]
        P[("PostgreSQL on Neon<br/>via Prisma")]
        G["Google Gemini<br/>generation and embeddings"]
        Y["Auth and billing"]
    end
    W --> R
    X --> R
    M --> R
    R --> T
    R --> Q
    T --> P
    Q --> P
    Q --> G
    R --> G
    R --> Y
```

## Engineering highlights

<table>
<tr>
<td width="50%" valign="top">

**One source of truth for tools**<br/>
Navigation, footer, sitemap, homepage and search all read a single registry. Adding a tool is one entry plus its page. What an admin may change (on/off, wording, order) lives in the database, so it changes without a deploy.

**Fails soft**<br/>
If the database or an AI provider is unavailable, pages fall back to safe defaults instead of an error screen, and builds never depend on a live database.

</td>
<td width="50%" valign="top">

**Cost and abuse controls**<br/>
Per-plan usage limits, rate limiting and a bot check protect the free tools. Provider keys are pooled with fallback models.

**Tested behaviour**<br/>
Automated tests cover routing, the tool registry, admin settings, the sitemap and database logic, using an in-memory Postgres so tests need no external services.

</td>
</tr>
</table>

## What this project demonstrates

- **Full-stack product engineering:** public site, authenticated dashboard, admin back office, extension and API, built and shipped by one person.
- **Applied AI:** embeddings for matching and search, prompt design, token accounting and cost-aware model use.
- **Data modelling:** Prisma schema design, additive migrations on a live database, caching and revalidation strategy.
- **Product thinking:** a flow that starts from the user's problem, not from a list of features.

## Roadmap

- [x] Guided homepage flow and tool matching
- [x] Prompt book with a fill-in editor
- [x] Browser extension and MCP server
- [x] Admin-managed tools
- [ ] More tools, added through the registry
- [ ] Flow diagrams and a walkthrough video in this repository

---

<div align="center">

**Aliyan Faisal**

[![Email](https://img.shields.io/badge/Email-aliyanfaisal15%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:aliyanfaisal15@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-aliyanfaisal-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/aliyanfaisal)
[![Live site](https://img.shields.io/badge/Website-cuelara.com-4F46E5?style=flat-square&logo=googlechrome&logoColor=white)](https://cuelara.com)

<sub>© Aliyan Faisal. All rights reserved. This repository is an overview for viewing only. The Cuelara name, design and source code may not be copied, modified, redistributed or used without written permission.</sub>

</div>
