<div align="center">

# Cuelara

### The AI prompts toolkit and prompt book

Fix, build, shorten and find the perfect prompt for ChatGPT, Claude and Gemini.

[![Live site](https://img.shields.io/badge/Live_site-cuelara.com-4F46E5?style=for-the-badge&logo=googlechrome&logoColor=white)](https://cuelara.com)
[![Tools](https://img.shields.io/badge/Try_the_tools-/tools-10B981?style=for-the-badge)](https://cuelara.com/tools)
[![Prompt book](https://img.shields.io/badge/Prompt_book-/cookbook-F59E0B?style=for-the-badge)](https://cuelara.com/cookbook)
[![Extension](https://img.shields.io/badge/Browser_extension-/extension-D946EF?style=for-the-badge)](https://cuelara.com/extension)

</div>

---

## About this repository

This is the public showcase of **Cuelara**, a full-stack web application I designed and built on my own. The complete source code is kept in a **private repository** to protect it from being copied or reused.

**Professors and reviewers are very welcome to read the code.** Send me a short email and I will add you as a collaborator with read access:

[![Request access](https://img.shields.io/badge/Request_code_access-aliyanfaisal15%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:aliyanfaisal15@gmail.com?subject=Cuelara%20repository%20access%20request&body=Hello%20Aliyan%2C%0A%0AI%20would%20like%20read%20access%20to%20the%20private%20Cuelara%20repository.%0A%0AMy%20GitHub%20username%3A%20)

Please include your GitHub username in the email. The private repository is here (you will see a 404 until access is granted):
[github.com/aliyanfaisal/Cuelara-AI-Prompt-Optimizer-Debugger-Token-Reducer](https://github.com/aliyanfaisal/Cuelara-AI-Prompt-Optimizer-Debugger-Token-Reducer)

---

## The problem

Most people get weak answers from AI tools because the prompt is weak, and they don't know what is wrong with it. Cuelara starts from the problem the person actually has ("my prompt isn't working", "I need a prompt written", "my prompt costs too much") and routes them to the right tool, which runs on the same page.

## What it does

### A guided "what do you need?" flow on the homepage
A visitor types their problem in plain words, or picks one of the common situations. Cuelara matches it to the best tool using text embeddings, shows other tools that could help, and lists any ready-made prompts that fit, all without leaving the page.

### A toolkit grouped by job

| Job | Tool | What it does |
| --- | --- | --- |
| **Build a prompt** | [Prompt Builder](https://cuelara.com/tools/prompt-builder) | Turns a rough idea into a complete, ready-to-paste prompt |
| | [Prompt Template Generator](https://cuelara.com/prompt-template-generator) | Fill in a ready-made template and copy a finished prompt |
| **Fix and perfect a prompt** | [Prompt Optimizer](https://cuelara.com/tools/prompt-optimizer) | Rewrites a vague prompt so the AI understands it |
| | [Prompt Debugger](https://cuelara.com/tools/prompt-debugger) | Finds contradictions, gaps and ambiguity |
| | [Prompt Formatter](https://cuelara.com/tools/prompt-formatter) | Structures a wall of text into clean Markdown, XML or JSON |
| | [Intelligence Score](https://cuelara.com/tools/intelligence-score) | Grades a prompt from 0 to 100 and says what to improve |
| **Save tokens and cost** | [Token Optimizer](https://cuelara.com/tools/token-optimizer) | Shortens a prompt, checked against real token counts |
| | [Diff & Cost Estimate](https://cuelara.com/tools/compare-estimate) | Compares two versions and shows the token and cost difference |
| **Add context** | [Context Extractor](https://cuelara.com/tools/context-extractor) | Pulls only the relevant parts out of large documents (retrieval) |
| | [Site to Prompt](https://cuelara.com/tools/site-to-prompt) | Turns a website's design into a prompt that recreates it |

### The prompt book
A library of ready-made prompts, each with a worked example. An **Edit this prompt** button opens a fill-in-the-blanks editor so a visitor can customise a prompt and copy the finished version. Search is semantic, not only keyword based.

### A browser extension and an MCP server
- A [browser extension](https://cuelara.com/extension) adds a button to the chat box on ChatGPT, Claude, Gemini and other AI sites, so a prompt can be improved in place.
- An [MCP server](https://cuelara.com/docs/mcp) lets tools such as Claude and Cursor use the toolkit directly.

### An admin back office
Admins manage users, plans, roles, the cookbook, the blog and the tools. Each tool can be switched on or off, reordered and re-worded from the admin without a deploy, and the change shows up across the menus, footer, homepage, sitemap and the tool-matching search.

---

## How it is built

| Area | Technology |
| --- | --- |
| Framework | Next.js 16 (App Router, Turbopack), React 19, TypeScript |
| Styling and motion | Tailwind CSS 4, Framer Motion |
| Database | PostgreSQL on Neon, accessed through Prisma 7 |
| AI | Google Gemini (generation and text embeddings), with a pool of provider keys and fallback models |
| Auth and billing | NextAuth, Paddle |
| Extension | Browser extension built with its own build script |
| Quality | Automated tests with the Node test runner, including database tests that run on an in-memory Postgres |

### Design decisions worth reading about

- **One tool registry.** The navbar, sidebar, footer, sitemap, homepage and the matching search all read a single list, so adding a tool is one entry plus its page. Admin-editable fields live in the database; what a tool *is* stays in code.
- **Matching through embeddings.** Each tool and each prompt-book entry is embedded once. A visitor's sentence is embedded and compared, so common paths cost one cheap lookup and nothing is hard-coded to keywords.
- **Fails soft.** If the database or an AI provider is unavailable, pages fall back to safe defaults instead of showing an error.
- **Abuse and cost controls.** Per-plan usage limits, rate limiting and a bot check protect the free tools.
- **Test-backed content rules.** Tests check that every tool is reachable from the homepage, that routes and the sitemap stay consistent, and that settings are applied correctly.

---

## Screenshots and walkthroughs

> _Coming soon: screenshots, a short demo video and flow diagrams of the main journeys (ask, match, run, take it further)._

---

## Contact

**Aliyan Faisal**
Email: [aliyanfaisal15@gmail.com](mailto:aliyanfaisal15@gmail.com)
GitHub: [@aliyanfaisal](https://github.com/aliyanfaisal)

---

<sub>© Aliyan Faisal. All rights reserved. This repository is for viewing only. The Cuelara name, design and source code may not be copied, modified, redistributed or used without written permission.</sub>
