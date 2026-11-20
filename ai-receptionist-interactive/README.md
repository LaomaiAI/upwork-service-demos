# AI Receptionist - Interactive Demo

Interactive portfolio demo for the $199 Upwork Catalog product
"AI Receptionist Setup: Answers Calls, Books Appointments, Follows Up".

## What it is

A single self-contained page (`index.html`, no external dependencies, no
network calls). A visitor picks one of three scripted sample scenarios,
answers a simulated phone call from "Sarah", the AI receptionist of the
fictional Bright Smile Dental clinic (Austin, TX), chooses the caller's
replies, and then sees the outcome: the booking on a week calendar, the
SMS confirmation, and a behind-the-scenes log of everything the service
did during the call.

## Scenarios (all scripted, all sample data)

- A - New patient books a cleaning (Emma Johnson, Delta Dental PPO).
  Branches: asks about insurance first, declines to share a number,
  no insurance, picks Tue 10:00 AM / Wed 2:30 PM / Thu 9:15 AM,
  or asks for details by text instead of booking.
- B - Existing patient reschedules (Michael Chen, Fri 3:00 PM filling).
  Branches: reschedule to Mon 11:00 AM / Tue 4:00 PM, cancel outright,
  or fails phone verification and gets flagged for a front-desk callback.
- C - Opening hours and prices (Alex Morgan).
  Branches: info only (no booking), or books Saturday 9:30 AM.
- D - Law firm intake (Priya Sharma, Hartwell and Associates).
  Branches: contract dispute, employment case, or fees question;
  intake record with matter, deadline and conflict check, books a
  30-minute consultation (Thu 2:00 PM / Fri 10:00 AM) or ends
  info-only.
- E - E-commerce pre-sales (Jordan Lee, Northwind Outdoor).
  Branches: shipping, returns or stock questions; reserves stock and
  creates order #NW-2481, or ends info-only.

End states: booked, moved, cancelled, flagged for front desk,
info only, intake complete, order placed. Ending a call early shows
"No booking was made" with a replay button. Mute / keypad / speaker
buttons toggle; the call timer runs live. The phone header and the
message tags follow the scenario's business and agent (Sarah / Alex /
Mia).

## Content sections (below the call)

- One receptionist, four kinds of business: clinic, law firm,
  e-commerce, manufacturing - each with the problem and what the
  receptionist does, linked to the playable scenario.
- More than answering the phone: records every caller, calls back and
  follows up, after-sales care, pre-sales answers - each with a
  concrete sample (record, callback log, check-in text, order).
- Your model, your choice: runs on mainstream large models (OpenAI,
  Anthropic Claude, Google Gemini, DeepSeek, open-source). The client
  picks; we build the integration; model usage is billed by the
  provider and paid by the client directly. No model is hard-coded,
  no prices invented.
- Lives on your website: the receptionist answers the phone and can
  sit on the company website as a chat / click-to-call widget; we can
  build or rebuild the company website too.
- How we work together: billed by the hour at $40/hr, no fixed
  package price, continuous adjustment during delivery as the client
  asks. No fixed-price promise appears anywhere on the page.

## Safety rules baked in

- Every name, phone number, date and price is invented and the page
  says so in the header, the intro, the SMS previews and the footer.
- No free-form input, no live AI, no real calls, no real bookings,
  no API keys. A visitor cannot use this page as a receptionist.
- Nothing on this page touches the existing dental / law-firm demo
  sites, Upwork, or any account.

## Testing (2026-11-20, Playwright + headless Chromium)

- 14 scripted paths covering every branch and every end state of
  scenarios A-C: all pass. Expansion re-test: 9 new paths for
  scenarios D and E plus 3 regression paths for A/B/C: all pass.
- End-call-early and mute-toggle behaviour verified.
- Agent tags and phone header verified per scenario (Sarah / Alex /
  Mia); footer verified free of any fixed-price promise.
- Zero console errors, zero page errors.
- Overflow audit at 1280px desktop and 390px mobile: no page-level
  overflow; the week calendar fits exactly on desktop and scrolls
  horizontally inside its own container on mobile.
- Screenshots checked by eye (desktop final A/B/D/E, mobile final
  A/E, mid-call, new sections): no overlapping text, no
  placeholder-grey blocks.

## Files

- `index.html` - the whole demo (HTML + CSS + JS, one file).
- This README.

## Hosted copy

Built as a web artifact (slug `ai-receptionist-interactive-demo`) so the
Upwork portfolio item can link to it. The local `index.html` in this
folder is the tested source of truth; verify the hosted copy renders
and plays the same before putting the link in the portfolio.

## Upwork portfolio copy

Title (60 chars):
`Demo: AI Receptionist for Clinics, Law Firms & Online Stores`

Description:
`Play a sample call with the AI receptionist across three businesses - a dental clinic, a law firm and an online store - and watch the booking, intake record or order appear with the confirmation message. Scripted demo with sample data only; the live service answers real calls, records every caller, follows up after the visit or sale, and is billed by the hour with the model of your choice.`
