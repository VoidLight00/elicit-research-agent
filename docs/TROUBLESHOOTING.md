# Troubleshooting

## Login Issues

### "Sign in" button keeps appearing
**Cause:** Google session expired in the OpenClaw browser.
**Fix:** Ask the agent to manually re-login:
```
"OpenClaw 브라우저에서 elicit.com 다시 로그인해줘"
```

### CAPTCHA during Google login
**Cause:** Google detected automated login attempt.
**Fix:** Log in manually through the OpenClaw browser, then retry.

### "Continue with Google" not working
**Cause:** Google account popup blocked or session conflict.
**Fix:**
1. Clear OpenClaw browser cookies for google.com
2. Re-login to Google first, then Elicit

## Search Issues

### "Research report" dialog appears instead of paper list
**Cause:** The agent searched in the default "Research report" mode.
**Fix:** This is handled automatically — the skill clicks "Find papers" first. If it still happens, the UI may have changed. Report an issue.

### Search returns no results
**Cause:** Query too specific or unusual topic.
**Fix:**
- Broaden the query
- Use English instead of Korean
- Try simpler terms

### Search button is disabled
**Cause:** Text wasn't properly entered in the search box.
**Fix:** The agent will retry. If persistent, Elicit may be experiencing issues.

## Pro Feature Errors

### "Upgrade to Pro" popup
**Cause:** Accidentally triggered a Pro-only feature.
**Free features:** Find papers, Paper chat, Research report (Fast)
**Pro-only:** Extract data, Systematic review, General research agent

**Fix:** Close the popup and ensure "Find papers" mode is selected.

## Result Issues

### Only 2-3 papers returned
**Cause:** Niche topic or very specific query.
**Fix:** Broaden the search terms or try related queries.

### Missing summaries for some papers
**Cause:** Elicit couldn't generate summaries for those papers (often older or less-cited papers).
**Fix:** This is normal — not all papers get AI summaries.

### Results are in wrong language
**Cause:** Query language mismatch.
**Fix:** The skill auto-translates Korean to English. Results are always from English-language papers.

## Performance

### Search takes more than 60 seconds
**Cause:** Slow network or Elicit server load.
**Fix:** Wait and retry. Typical search takes 15-30 seconds.

### Browser timeout
**Cause:** OpenClaw browser session disconnected.
**Fix:** Restart the OpenClaw browser and retry:
```
"OpenClaw 브라우저 재시작하고 다시 검색해줘"
```

## FAQ

**Q: Is this free?**
A: Yes, the "Find papers" feature is free and unlimited on Elicit.

**Q: How many papers can I get per search?**
A: About 10 papers per search on the free tier.

**Q: Can I use this without OpenClaw?**
A: No, this skill requires OpenClaw's browser automation.

**Q: Does this work with Elicit's API?**
A: Not currently. This skill uses browser automation only.
