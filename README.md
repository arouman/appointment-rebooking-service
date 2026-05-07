# Appointment Rebooking Assistant

An AI-powered phone assistant for small medical and trades businesses. When no one is available to answer, the AI handles the call — collecting the caller's name, number, and appointment details — then emails a structured summary to the business so they can follow up.

## How It Works

Clients forward their existing business phone number to a dedicated number provisioned through [Vapi.ai](https://vapi.ai). When a call comes in on that number, the AI answers using a customized script and collects appointment information. After the call ends, the business receives an email with everything the caller provided.

No new equipment. No apps. The only change for the client is setting up call forwarding — which takes about two minutes.

## What the AI Does

- Answers missed calls with a professional, on-brand greeting
- Collects caller name, callback number, nature of the request, and preferred appointment time
- Adapts its language and urgency handling based on the type of business (medical or trades)
- Redirects medical emergencies to 911 immediately
- Reads back all collected information to the caller before closing
- Sends a structured email summary to the business after every call

## What the AI Does Not Do

- Book, confirm, or change appointments
- Access any schedules or records
- Promise specific callback times beyond the general follow-up commitment

## Setup Overview (for the PM)

1. Client completes the intake form
2. PM fills in the four placeholders in `system-prompt.md`
3. PM loads the filled prompt into Vapi and provisions a phone number
4. PM sends the client their forwarding number with setup instructions
5. Done — the system handles all missed calls automatically

See `configuration-guide.md` for the full step-by-step process.

## Repository Contents

| File | What It Is |
|---|---|
| `system-prompt.md` | The AI script loaded into Vapi — one copy per client, customized with their details |
| `configuration-guide.md` | How to onboard a new client from intake form to live system |
| `intake-form-template.md` | The questions to send new clients before setup |
| `email-template.md` | The format of the email summary sent after each call |
| `CLAUDE.md` | Context for Claude Code when working in this repo |

## Platform

Built on [Vapi.ai](https://vapi.ai). Free trial credits cover the initial pilot. At scale, cost is approximately $0.05–$0.15 per minute of call time.
