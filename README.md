# 🔬 Elicit Research Agent

**Automated academic paper search & AI summarization through browser automation.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-Skill-blue)](https://openclaw.com)
[![Elicit](https://img.shields.io/badge/Elicit-138M%20papers-green)](https://elicit.com)

An OpenClaw skill that automates [Elicit.com](https://elicit.com) to search 138M+ academic papers and extract AI-powered summaries — no API key required.

---

## ✨ Features

- 🌐 **Browser Automation** — Fully automated Elicit interaction via OpenClaw browser
- 🔄 **Auto Query Optimization** — Korean/English questions → optimized academic queries
- 📊 **Structured Extraction** — Paper titles, authors, year, journal, citations, summaries
- 🤖 **AI Summary** — Elicit's built-in AI synthesis included in results
- 🔗 **Source Links** — Direct Elicit URLs for further exploration
- 💰 **Free Tier Compatible** — Works entirely within Elicit's free plan

## 🔄 How It Works

```
User: "카페인이 인지에 미치는 영향은?"
         │
         ▼
┌─────────────────────────┐
│  Query Optimization     │  Korean → English academic query
│  "Effects of caffeine   │  + keyword expansion
│   on cognitive function" │
└────────────┬────────────┘
             ▼
┌─────────────────────────┐
│  Browser Automation     │  Navigate → Login check →
│  (OpenClaw browser)     │  Find papers → Search →
│                         │  Wait for results
└────────────┬────────────┘
             ▼
┌─────────────────────────┐
│  Result Extraction      │  AI summary + paper list
│  & Formatting           │  + metadata + URLs
└────────────┬────────────┘
             ▼
📄 Structured research summary with 5-10 papers
```

## 🚀 Quick Start

### Option A: One-Line Install (Recommended)

Just send this message to your OpenClaw agent:

> **이 스킬 설치해줘: https://github.com/VoidLight00/elicit-research-agent**

Your agent will clone the repo, install the skill, and set everything up automatically.

### Option B: Manual Install

```bash
git clone https://github.com/VoidLight00/elicit-research-agent.git
mkdir -p ~/.openclaw/workspace/skills/elicit-research
cp elicit-research-agent/SKILL.md ~/.openclaw/workspace/skills/elicit-research/SKILL.md
```

### Then: Login to Elicit

Sign up at [elicit.com](https://elicit.com) (free) and log in via OpenClaw browser:

```
"OpenClaw 브라우저로 elicit.com 열어서 로그인해줘"
```

### Start Searching

```
"논문 검색해줘: 간헐적 단식이 체중 감량에 효과적인가?"
```

> See [docs/SETUP.md](docs/SETUP.md) for detailed setup instructions.

## 📋 Requirements

| Requirement | Details |
|-------------|---------|
| **OpenClaw** | `npm install -g openclaw` ([docs](https://docs.openclaw.ai)) |
| **Elicit Account** | Free tier works ([elicit.com](https://elicit.com)) |
| **Browser Session** | Elicit login maintained in OpenClaw browser |

## ⚙️ Configuration

No API keys or environment variables needed. The skill uses browser automation with your existing Elicit session.

1. **Create an Elicit account** at [elicit.com](https://elicit.com) (Google login recommended)
2. **Sign in** via the OpenClaw browser (`profile="openclaw"`)
3. **Keep the session alive** — the browser persists login state

## 💡 Usage Examples

**English:**
```
"Research: effects of sleep deprivation on memory consolidation"
"Find papers about intermittent fasting and weight loss"
```

**Korean (auto-translated):**
```
"논문 검색해줘: 카페인이 수면의 질에 미치는 영향"
"연구 찾아줘: 명상이 스트레스 감소에 효과적인가"
```

> See [docs/USAGE.md](docs/USAGE.md) for advanced usage and tips.

## 🏗️ Architecture

```
┌──────────────────────────────────────┐
│           OpenClaw Agent             │
│  ┌────────────┐  ┌───────────────┐  │
│  │ Query      │  │ Result        │  │
│  │ Optimizer  │→ │ Formatter     │  │
│  └─────┬──────┘  └───────▲───────┘  │
│        │                 │          │
│  ┌─────▼─────────────────┴───────┐  │
│  │     Browser Controller        │  │
│  │     (profile="openclaw")      │  │
│  └─────────────┬─────────────────┘  │
└────────────────┼─────────────────────┘
                 │
        ┌────────▼────────┐
        │   Elicit.com    │
        │  138M+ papers   │
        └─────────────────┘
```

**Key Components:**

- **Query Optimizer** — Translates and refines user questions into effective academic search queries
- **Browser Controller** — Navigates Elicit UI: login check → mode selection → search → result extraction
- **Result Formatter** — Structures raw scraped data into clean markdown with citations

## ⚠️ Limitations

- **Browser-dependent** — UI changes on Elicit may break automation (fixable by updating SKILL.md selectors)
- **Free tier limits** — Basic search is unlimited; reports limited to ~10/month
- **Speed** — Browser automation takes 15-30 seconds per search
- **No batch search** — One query at a time
- **Session expiry** — Google/Elicit session may expire; manual re-login needed occasionally
- **Pro features excluded** — Extract data, Systematic review, General research agent require Elicit Pro

## 🤝 Contributing

Contributions are welcome! Areas where help is appreciated:

1. **Selector updates** — When Elicit UI changes, update aria selectors in SKILL.md
2. **Query optimization** — Better translation/expansion strategies for non-English queries
3. **Documentation** — Usage examples, troubleshooting tips
4. **Language support** — Query optimization for more languages

### How to contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feat/your-feature`)
3. Commit your changes (`git commit -m "feat: description"`)
4. Push and open a Pull Request

## 📄 License

[MIT](LICENSE) — use it however you want.

---

*Built with [OpenClaw](https://openclaw.com) 🐙*
