# Configuration Guide

How to onboard a new client from intake form to live system. End to end, this takes about 30 minutes.

---

## Step 1 — Receive the Intake Form

Send the client the intake form (see `intake-form-template.md`). You need their answers before doing anything else.

Once you have their responses, collect these four values — you'll use them in Step 2:

| What You Need | Where It Comes From |
|---|---|
| Business name | Intake form |
| Business type (`medical` or `trades`) | Intake form |
| Business website | Intake form |
| Follow-up timeframe (e.g., "within 24 hours") | Intake form |
| Summary email address | Intake form |

---

## Step 2 — Fill In the System Prompt

1. Open `system-prompt.md` and make a copy — name it something like `[client-name]-system-prompt.md`
2. Find and replace all four placeholders with the client's actual values:

| Placeholder | Replace With |
|---|---|
| `[BUSINESS NAME]` | The business's name |
| `[BUSINESS TYPE]` | Either `medical` or `trades` |
| `[BUSINESS WEBSITE]` | Their website URL |
| `[FOLLOW-UP TIMEFRAME]` | How quickly they follow up (e.g., "within 24 hours") |

3. Read through the filled prompt once to confirm it sounds natural with their details in place.

---

## Step 3 — Set Up Vapi

1. Log in to [Vapi.ai](https://vapi.ai)
2. Create a new **Assistant**
3. Paste the filled system prompt into the assistant's system prompt field
4. Under the assistant's settings, set the **end-of-call email** delivery target to the client's summary email address
5. Save the assistant

---

## Step 4 — Provision a Phone Number

1. In Vapi, go to **Phone Numbers** and provision a new number
2. Assign it to the assistant you just created
3. Copy the provisioned number — you'll give this to the client

---

## Step 5 — Test the Setup

Before handing anything to the client, call the Vapi number yourself and run through these scenarios:

- [ ] Normal call: give a name, number, and routine request — confirm the email summary arrives correctly
- [ ] Caller doesn't know preferred time — confirm the AI notes "flexible" and moves on
- [ ] **Medical accounts only:** Say something like "I think I'm having a heart attack" — confirm the AI immediately redirects to 911 and does not continue collecting information
- [ ] **Trades accounts only:** Describe a flooding emergency — confirm the AI flags urgency and sets honest expectations without promising a specific arrival time
- [ ] Confirm the AI reads back all collected info before closing
- [ ] Confirm the AI does not promise a specific appointment slot

Do not deliver the number to the client until all checks pass.

---

## Step 6 — Deliver to the Client

Send the client:

1. Their Vapi forwarding number
2. Call forwarding instructions for their phone system or carrier (see below)
3. A brief explanation of what to expect (the AI answers, they get an email after each call)

**Generic call forwarding instructions** (exact steps vary by carrier):

- **iPhone:** Settings → Phone → Call Forwarding → enter the Vapi number
- **Android:** Phone app → Settings → Calls → Call Forwarding → Always Forward
- **Landline / VoIP:** Varies by carrier — most have a `*72` forward-all code; client should check with their provider

---

## Step 7 — File the Client Record

Save the filled system prompt file to this repo in a `clients/` folder:

```
clients/
  [client-name]-system-prompt.md
```

Note the client name, setup date, Vapi assistant ID, provisioned number, and summary email in a simple log so you can find it again later.

---

## Making Changes After Go-Live

If a client needs to update their follow-up timeframe, email address, or any other detail:

1. Edit their copy of the system prompt
2. Paste the updated prompt into their Vapi assistant and save
3. Call the number to confirm the change took effect
