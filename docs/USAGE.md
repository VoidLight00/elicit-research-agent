# Usage Guide

## Basic Usage

Simply ask your OpenClaw agent to search for papers:

```
"논문 검색해줘: [your question]"
"research: [your query]"
"find papers about [topic]"
```

## Korean → English Optimization Tips

The agent automatically translates Korean questions to English academic queries. For best results:

| Instead of... | Try... |
|---------------|--------|
| 커피 좋아? | 카페인 섭취가 건강에 미치는 영향은? |
| 운동하면 좋아지나 | 규칙적인 운동이 우울증 증상 완화에 효과적인가? |
| AI가 일자리 뺏어? | 인공지능 자동화가 고용 시장에 미치는 영향 |

**Tips:**
- Be specific — narrow topics yield better papers
- Include the relationship you're interested in (X → Y)
- Mention the population if relevant (adults, children, elderly)

## Understanding Results

A typical result includes:

### AI Summary
Elicit's AI synthesizes findings across the returned papers. This is not a single paper's conclusion but a cross-paper analysis.

### Paper List
Each paper entry contains:
- **Title** — Click-through to the original paper
- **Authors & Year** — For citation purposes
- **Journal** — Publication venue
- **Citations** — Academic impact indicator
- **Summary** — AI-generated summary of the paper's relevance to your query

### Source Link
The Elicit URL lets you explore further — add columns, filter, or dive into individual papers.

## Obsidian Integration

Save research results to your Obsidian vault:

```
"논문 검색해줘: [질문] — 결과를 옵시디언에 저장해줘"
```

Suggested frontmatter format:

```yaml
---
source: elicit
query: "effects of caffeine on cognitive performance"
date: 2026-02-13
papers: 8
tags: [research, caffeine, cognition]
---
```

## Advanced Queries

**Comparison queries:**
```
"Research: cognitive behavioral therapy vs medication for anxiety disorders"
```

**Mechanism queries:**
```
"Find papers about the mechanism of neuroplasticity in adult learning"
```

**Review queries:**
```
"Research: systematic reviews on Mediterranean diet and cardiovascular health"
```
