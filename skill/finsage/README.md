# FinSage Skill — Install Guide (MVP)

A prompt-driven skill. **No code, no dependencies, no API keys of its own.** Copy one folder and your AI tool picks it up. For live figures, the skill uses whatever market-data or web tools your session already has (see [Notes](#notes)).

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
/finsage 0700.HK
```

You should get a structured 10-section research memo that opens with a data stamp (price date, latest fiscal period, sources) and ends with the disclaimer. If no web or market-data tools are available, the memo opens with a "Memory-only mode" banner and omits specific figures.

---

## Uninstall

```bash
rm -rf ~/.claude/skills/finsage     # macOS / Linux
Remove-Item -Recurse $env:USERPROFILE\.claude\skills\finsage    # Windows PS
```

---

## Notes

- This skill is **prompt-only** and ships no data connectors. At run time it uses, in order: market-data or financial-data tools configured in your session, then web tools (primary sources such as SEC EDGAR and company filings), and otherwise falls back to a memory-only qualitative mode with no specific figures.
- Every figure in the output carries a source and an as-of date, or is marked `unverified`.
- Planned: dedicated MCP-server integrations (Finnhub, Alpha Vantage, etc.).
- See [`SKILL.md`](SKILL.md) for the full skill definition.

---

⚠️ **Not investment advice.** This skill produces research output for educational purposes only. Always consult a licensed investment advisor before making investment decisions.
