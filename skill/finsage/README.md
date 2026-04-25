# FinSage Skill — Install Guide (MVP)

A pure prompt-driven skill. **No code, no dependencies, no API keys.** Copy one folder, restart your AI tool, done.

---

## Install in Claude Code

```bash
# macOS / Linux
cp -r skill/finsage ~/.claude/skills/finsage

# Windows (PowerShell)
Copy-Item -Recurse skill\finsage $env:USERPROFILE\.claude\skills\finsage

# Windows (Git Bash)
cp -r skill/finsage "$USERPROFILE/.claude/skills/finsage"
```

Restart Claude Code. The skill activates automatically when the user mentions a ticker, asks for security research, or types `/finsage`.

---

## Install in OpenClaw

Same skill folder structure works. Place `skill/finsage/` into OpenClaw's skills directory (consult OpenClaw docs for the exact path on your installation).

---

## Quick Test

Open Claude Code in any folder and type:

```
Analyze TSLA from a portfolio manager's view
```

or

```
帮我用 FinSage 分析 700.HK
```

You should get a structured 7-section research output ending with the disclaimer.

---

## Uninstall

```bash
rm -rf ~/.claude/skills/finsage     # macOS / Linux
Remove-Item -Recurse $env:USERPROFILE\.claude\skills\finsage    # Windows PS
```

---

## Notes

- This MVP is **prompt-only**. It does not fetch live prices, filings, or news. The model reasons from training data.
- For live data, future versions will add MCP-server integrations (Finnhub, Alpha Vantage, etc.).
- See [`SKILL.md`](SKILL.md) for the full skill definition.

---

⚠️ **Not investment advice.** This skill produces research output for educational purposes only. Always consult a licensed investment advisor before making investment decisions.
