# Setup Guide

## 0. Install OpenClaw

If you don't have OpenClaw installed yet:

```bash
npm install -g openclaw
```

Then start the gateway:

```bash
openclaw gateway start
```

For detailed setup (API keys, channel config, etc.), see the [OpenClaw docs](https://docs.openclaw.ai).

> 💡 **Already have OpenClaw?** Skip to step 1.

---

## 1. Create an Elicit Account & Login

The agent will handle this automatically on first use.

**What happens:**
1. Agent opens [elicit.com](https://elicit.com) in the OpenClaw browser
2. Checks if already logged in
3. If not logged in → **asks you for your Elicit credentials**:
   - Login method: Google (recommended) or email/password
   - If Google: agent clicks "Continue with Google" (requires Google session in browser)
   - If email: agent asks for your **email** and **password**, then types them into Elicit's login form
4. Completes login and confirms success

> ⚠️ **Privacy:** Your credentials are only used to type into Elicit's login page via the browser. They are NOT stored anywhere by the skill.

> 💡 **Google login recommended** — If your Google account is already signed in on the OpenClaw browser, login is fully automatic with no credentials needed.

**Session persistence:** The OpenClaw browser maintains cookies between sessions. You typically only need to log in once. When the session expires, the agent will ask for credentials again.

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
