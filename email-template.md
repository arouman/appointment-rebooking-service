# Email Summary Template

This is the format of the email the business receives after each AI-handled call. It is embedded in the system prompt as an internal instruction — the AI structures its output to match this format, and Vapi delivers it to the business's designated email address.

---

## Email Format

**Subject line:**
```
New Appointment Request — [BUSINESS NAME]
```

**Body:**
```
NEW APPOINTMENT REQUEST — [BUSINESS NAME]
──────────────────────────────────────────
Caller Name:           [full name provided by caller]
Callback Number:       [phone number provided by caller]
Request Type:          [urgency category — see options below]
Details Provided:      [brief summary of what the caller described]
Preferred Appointment: [day/time stated by caller, or "Flexible"]
Follow-up Commitment:  [FOLLOW-UP TIMEFRAME]
──────────────────────────────────────────
Handled by AI assistant. No appointment has been booked.
```

---

## Request Type Options

The AI uses one of the following labels in the **Request Type** field based on what the caller described:

**Medical:**
- Routine appointment
- Urgent care (non-emergency)
- New patient inquiry
- Prescription refill
- General question

**Trades:**
- Emergency service
- Quote request
- Scheduled maintenance
- General inquiry

---

## Notes

- If the caller's preferred time is unknown or unspecified, the field reads **"Flexible"**
- The footer line ("Handled by AI assistant. No appointment has been booked.") is always included so the business knows the call was AI-handled and no slot has been reserved
- Medical emergency calls are redirected to 911 immediately and do not generate a summary email
