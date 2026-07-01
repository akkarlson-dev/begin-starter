# iN Starter Kit

A personal capture pipeline. Built by Amy Karlson, packaged for people she trusts.

You get a Google Form on your iPhone home screen, a Drive folder for screenshots and voice transcripts, and a script that enriches everything with Claude Haiku every 15 minutes and writes it to a Google Sheet.

---

## Architecture

```
CAPTURE
  iPhone home screen
    └─ iN Form (3 fields)  ──┐
  iPhone Drive app           │
    └─ IN/captures/  ────────┤
  Voice transcript (file)    │
    └─ IN/captures/  ────────┤
                             ▼
                    Google Sheets
                    (your data, your account)
                             │
                    Apps Script trigger
                    (every 15 min, runs in your account)
                             │
                    Claude Haiku API
                    (~$0.002 per capture)
                             │
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
         Captures         Resources       Tasks
           tab              tab            tab
        (all entries)    (links +        (actionable
                         summaries)       items)
```

Your data never leaves your Google account. The only external call is to the Anthropic API for enrichment.

---

## What you need

**Google account — free**
A standard Google account is all you need. The pipeline runs on Google Forms, Sheets, Drive, and Apps Script — all free. You do not need Google One AI Premium or any paid Google tier for this.

**Anthropic account — ~$5 to start, ~$1-5/month**
Go to [platform.anthropic.com](https://platform.anthropic.com), create an account, add a credit card, and buy a small credit top-up ($5 covers months of light pipeline use). Then create an API key. This account covers two things: the pipeline script (Claude Haiku enriches your captures) and Claude Code in VS Code (which walks you through setup).

**VS Code — free**
Download at [code.visualstudio.com](https://code.visualstudio.com). Install the Claude Code extension from the VS Code marketplace. Sign in with your Anthropic account.

---

## Three steps

1. Clone this repo and open the folder in VS Code
2. Claude Code reads `CLAUDE.md` automatically and starts the setup conversation
3. Follow along. You'll have something running in under an hour.

---

## Three ways to capture

**Form** — the main path. Tap the iN icon on your home screen, fill three fields, submit. Works anywhere, no app install required.

**Drive drop** — for screenshots, photos, PDFs, and voice transcripts. On iPhone: Share → Save to Files → Google Drive → IN/captures. The pipeline picks up anything dropped here.

**Links** — paste a URL into the form's Context field. The pipeline fetches the page title and a short summary automatically and writes it to the Resources tab.

---

## Voice users

If you dictate long captures using WhisperSpeak, Superwhisper, or a similar tool:
- If your tool saves transcripts as files: point it at `IN/captures/` in Google Drive. Fully hands-free.
- If your tool outputs to clipboard: paste into the form. The native iOS keyboard mic also works directly in the form for shorter captures.

---

## Pilot

This went to five people first: Chris, Ben, Sarah, Arturo, James.

---

*iN / begiN · Amy K. Karlson · July 2026*
*[beginin.substack.com](https://beginin.substack.com)*
