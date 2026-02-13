# Setup Guide

## 1. Create an Elicit Account

1. Go to [elicit.com](https://elicit.com)
2. Click **"Sign up"**
3. Select **"Continue with Google"** (recommended for seamless browser automation)
4. Complete the signup process

> 💡 Google login is recommended because OpenClaw browser can maintain the Google session, enabling automatic re-login.

## 2. Login via OpenClaw Browser

The skill uses OpenClaw's built-in browser (`profile="openclaw"`) for automation.

**First-time setup:**

Tell your OpenClaw agent:

```
"Open elicit.com in the OpenClaw browser and log in with my Google account"
```

The agent will:
1. Navigate to elicit.com
2. Click "Sign in" → "Continue with Google"
3. Complete the Google OAuth flow

**Session persistence:** The OpenClaw browser maintains cookies between sessions. You typically only need to log in once.

## 3. Install the Skill

### Option A: Copy SKILL.md

```bash
git clone https://github.com/VoidLight00/elicit-research-agent.git
mkdir -p ~/.openclaw/workspace/skills/elicit-research/
cp elicit-research-agent/SKILL.md ~/.openclaw/workspace/skills/elicit-research/SKILL.md
```

### Option B: Manual

1. Download `SKILL.md` from this repository
2. Place it at `~/.openclaw/workspace/skills/elicit-research/SKILL.md`

## 4. Verify

Test with a simple query:

```
"Research: effects of caffeine on sleep quality"
```

You should receive a structured summary with AI analysis and paper citations within 30 seconds.

## Updating

When Elicit updates their UI, the aria selectors in SKILL.md may need updating. Pull the latest version:

```bash
cd elicit-research-agent
git pull
cp SKILL.md ~/.openclaw/workspace/skills/elicit-research/SKILL.md
```
