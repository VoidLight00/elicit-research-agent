# Elicit Research Agent Skill

## Overview

OpenClaw browser automation skill for [Elicit.com](https://elicit.com) — searches 138M+ academic papers and extracts AI-powered summaries.

## Prerequisites

- Elicit account (Google login recommended)
- OpenClaw browser (`profile="openclaw"`) with active Elicit session
- Elicit free tier (uses "Find papers" feature)

## Trigger Phrases

- `"논문 검색해줘: [질문]"`
- `"research: [query]"`
- `"[topic]에 대한 연구 찾아줘"`
- `"find papers about [topic]"`

### Korean → English Query Optimization

When the user asks in Korean, convert to an English academic query:

- "카페인이 인지에 미치는 영향" → "Effects of caffeine on cognitive performance"
- "수면 부족과 기억력" → "Effects of sleep deprivation on memory consolidation"
- "명상과 스트레스" → "Effects of meditation on stress reduction"

## Automation Steps

### Step 1: Login Check

```
1. browser navigate → https://elicit.com (profile="openclaw")
2. browser snapshot (refs="aria")
3. Check for "Sign in" or "Sign up" button
   - Found → Click "Sign in" → Click "Continue with Google" → auto-login
   - Not found (search bar visible) → Already logged in
```

### Step 2: Select "Find papers" Mode & Search

```
1. Click "Find papers" button on main page
   ⚠️ IMPORTANT: Default mode is "Research report" — must switch!
2. Type query into textbox ("Ask a research question...")
3. Verify source is set to "Research papers"
4. Click "Search" button
5. Wait for results (10-15 seconds)
```

> ⚠️ **Critical**: The default search mode generates a "Research report" dialog.
> Always click **"Find papers"** first to switch modes before searching.

### Step 3: Result Scraping

```
1. Capture result page with snapshot (refs="aria", compact=true)
2. Extract:
   - AI Summary: First message in the chat panel (paragraph/strong tags)
   - Paper list: From row elements
     - Title: link text
     - Authors/Year/Journal/Citations: gridcell text
     - Summary: Summary column gridcell text
   - URL: window.location.href
```

### Step 4: Format Output

```markdown
## 🔬 Elicit Research Results: [query]

### AI Summary
[Extracted AI summary from chat panel]

### Key Papers
1. **[Title]** ([Authors], [Year])
   - Journal: [Journal] | Citations: [N]
   - Key finding: [Summary column content]

2. ...

> 🔗 Source: [Elicit URL]
```

## UI Element Reference (Aria Selectors)

| Element | Description | Location |
|---------|-------------|----------|
| `button "Find papers"` | Mode switch button | Main page Tools section |
| `textbox "Ask a research question..."` | Search input | Main area |
| `button "Search"` | Execute search | Next to search box |
| `button "Source Research papers"` | Source type | Below search box |
| `row` → `gridcell` | Paper info | Results table |
| `paragraph > strong` | AI summary highlights | Chat panel |
| `paragraph` (following) | AI detailed explanation | Chat panel |

## Troubleshooting

### Login Failure
- **Google session expired**: Manually re-login to Google in the OpenClaw browser
- **CAPTCHA appears**: Manual intervention required during "Continue with Google"

### Search Failure
- **"Research report" dialog appears**: Close it (Cancel/Close), then click "Find papers" to switch modes
- **Search button disabled**: Verify text was properly entered in the search box

### Pro Feature Required
- **Pro-only features**: Extract data, Systematic review, General research agent
- **Free features**: Find papers, Paper chat, Research report (Fast option)

### Few Results
- Default shows ~10 sources
- Scroll to load additional papers
- Use "Add a column" to show Abstract, Year, etc.

## Constraints

- Must use `profile="openclaw"`
- Free tier only — no Pro features
- No report generation — use Find papers + AI chat summary
- Maximum ~10 papers per search (free tier)
