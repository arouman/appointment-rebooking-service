# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working in this repository.

## What This Project Is

An AI-powered phone assistant for small medical and trades businesses. When no one is available to answer, callers are handled by an AI that collects appointment information and emails a structured summary to the business so they can follow up.

The service is delivered as a **concierge setup** — the PM (Adam) configures each new client manually. There is no self-serve flow.

## How It Works

1. Client fills out an intake form (Typeform or Google Form)
2. PM fills the system prompt placeholders using the client's answers (~5 minutes)
3. PM loads the filled prompt into Vapi.ai and provisions a phone number
4. Client forwards their existing business number to that Vapi number
5. All missed calls are answered by the AI automatically
6. After each call, a structured email summary is sent to the business

## Placeholder Map

These four placeholders appear in `system-prompt.md` and must be replaced per client before loading into Vapi:

| Placeholder | What It Is | Example |
|---|---|---|
| `[BUSINESS NAME]` | The business's name as callers know it | Green Valley Physio |
| `[BUSINESS TYPE]` | Either `medical` or `trades` | medical |
| `[BUSINESS WEBSITE]` | The business's website URL | greenvalleyphysio.com |
| `[FOLLOW-UP TIMEFRAME]` | How quickly they commit to calling back | within 24 hours |

## File Guide

| File | Purpose |
|---|---|
| `system-prompt.md` | The AI prompt loaded into Vapi — one per client, placeholders filled in |
| `configuration-guide.md` | Step-by-step instructions for setting up a new client from intake to delivery |
| `intake-form-template.md` | Copy-paste questions for the client intake form (Typeform or Google Form) |
| `email-template.md` | Reference for the structured email summary sent after each call |
| `README.md` | Plain-English project overview |

## Key Decisions

- **Platform:** Vapi.ai (free trial for MVP; ~$0.05–0.15/min at scale)
- **No self-serve:** PM configures everything manually per client
- **Two business types:** `medical` and `trades` — the prompt branches behavior for each
- **Medical emergency handling:** The AI immediately redirects to 911 — this is non-negotiable
- **The AI never promises a specific appointment slot** — it only collects info and sets callback expectations

## What to Avoid

- Do not add new placeholders to `system-prompt.md` without updating `intake-form-template.md` and this file's placeholder map
- Do not change the medical emergency redirect behavior
- Do not change the confirmation step — the AI must always read back collected info before closing
