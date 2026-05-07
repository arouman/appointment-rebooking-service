# Intake Form Template

These are the questions to include in the client intake form (Typeform or Google Form). Copy them in order. The right column shows which system prompt placeholder each question feeds.

---

## Questions

| # | Question | Type | Maps To |
|---|---|---|---|
| 1 | What is your business name? | Short text | `[BUSINESS NAME]` |
| 2 | Is this a medical practice or a trades business? | Multiple choice: Medical / Trades | `[BUSINESS TYPE]` |
| 3 | What is your business website? | Short text (URL) | `[BUSINESS WEBSITE]` |
| 4 | What is your current business phone number? | Short text | Call forwarding setup (not in prompt) |
| 5 | What email address should appointment summaries be sent to? | Email | Vapi email delivery target (not in prompt) |
| 6 | How quickly do you typically follow up with callers? | Short text (e.g., "within 24 hours", "the next business day") | `[FOLLOW-UP TIMEFRAME]` |
| 7 | Is there anything specific callers should know? (optional) | Long text | Supplemental context — PM reviews and incorporates manually if relevant |

---

## Notes for the PM

- Question 4 (current phone number) is for your reference during setup only — it's how you know what number the client needs to forward from.
- Question 5 (summary email) goes into Vapi's end-of-call email settings, not into the system prompt itself.
- Question 7 is optional and open-ended. Review the response before setup. If the client provides something meaningful (e.g., "we're closed on Wednesdays" or "we only serve existing patients"), incorporate it as a short additional instruction at the end of the system prompt.

---

## Suggested Form Header

> **Getting started with your AI phone assistant**
>
> This short form gives us everything we need to set up your assistant. It takes about 5 minutes. Once we receive your responses, we'll have everything ready within [X] business days and will send you your call forwarding number.
