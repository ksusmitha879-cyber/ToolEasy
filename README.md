# ToolEasy
# 🧒 Explain Like I'm 5 (ELI5)

An educational AI simplifier that breaks down highly complex, academic, or jargon-heavy topics into relatable analogies and plain language that anyone can understand — with a "Simplify Further" button that goes even deeper.

![Powered by Claude](https://img.shields.io/badge/Powered%20by-Claude%20AI-7F77DD?style=flat-square) ![Netlify](https://img.shields.io/badge/Deployed%20on-Netlify-00C7B7?style=flat-square)

---

## Demo

> **Input:** Quantum Entanglement
>
> **Output:** "Imagine you have two magical dice. No matter how far apart they are — if you roll a 6 on one, the other one instantly shows a 6 too. They are connected by an invisible, instant link. Scientists call this quantum entanglement, and even Einstein thought it was spooky! Fun fact: we actually use this to build unhackable communication systems."

---

## Deployed Link - https://5easytool.netlify.app

## Features

- Giant minimal search bar — the whole UI is one input
- 8 topic quick-fill buttons to get started instantly
- 3-level simplification — Normal → Simpler → Pure analogy only
- "Simplify Further" button re-prompts at an even lower level
- Search history chips to revisit recent topics
- Every explanation ends with a surprising fun fact
- Copy to clipboard
- Warm yellow/orange theme on dark background

---

## Project Structure

```
07-eli5-tool/
├── index.html
├── .gitignore
└── netlify/
    └── functions/
        └── generate.js
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [Netlify CLI](https://docs.netlify.com/cli/get-started/) — `npm install -g netlify-cli`
- An [Anthropic API key](https://console.anthropic.com/)

### Local Development

```bash
git clone https://github.com/yourusername/eli5-tool.git
cd eli5-tool
netlify login
netlify dev
```

Open [http://localhost:8888](http://localhost:8888)

### Environment Variables

```
ANTHROPIC_API_KEY=sk-ant-your-key-here
```

---

## Deployment

```bash
netlify deploy --prod
```

Add `ANTHROPIC_API_KEY` in **Netlify Dashboard → Site configuration → Environment variables**, then redeploy.

---

## How It Works

```
User types a complex topic and presses Enter
        ↓
index.html builds prompt with current simplification level
        ↓
generate.js adds API key → forwards to Anthropic
        ↓
Claude explains using a single everyday analogy, no jargon
        ↓
Explanation displayed with Simplify Further button
        ↓
If user clicks Simplify Further → level increases → new prompt sent
        ↓
Up to 3 levels of progressive simplification
```

---

## Simplification Levels

| Level | Instruction to Claude |
|---|---|
| 0 | Explain as if I am a curious 5-year-old |
| 1 | Explain as if I am a toddler — even simpler |
| 2 | Use only toy, food, or animal comparisons — pure analogy |

---

## Prompt Template

```
Explain the following concept: [Topic].
Assume I am a 5-year-old.
Do not use any industry jargon.
Use exactly one everyday analogy involving toys, food, or animals.
End with one surprising Fun fact sentence.
Keep it under 150 words.
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| Icons | Tabler Icons |
| AI Model | Claude Sonnet (claude-sonnet-4-6) |
| Backend | Netlify Serverless Functions |
| Hosting | Netlify |

---

## License

MIT
