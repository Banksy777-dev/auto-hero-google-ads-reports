# Auto Hero Google Ads — Session Recap 08/07/2026

A plain-English recap of every setting changed in the Google Ads account on 08/07/2026 (Sydney), in the order it happened.

**Account:** Auto Hero — 947-503-9797
**Campaign in focus:** Jumpstart 14/04/2026 (23745071702)

---

## Table of Contents

1. [What changed today](#1-what-changed-today)
2. [Reading the Google Ads UI after the changes](#2-reading-the-google-ads-ui-after-the-changes)
3. [TL;DR](#3-tldr)

---

## 1. What changed today

### 1.1 New ad group launched

**Where:** Campaign "Jumpstart 14/04/2026"

**What:** Created a new ad group called **"20KAG - Jumpstart"**.

**Why:** Consolidate the jumpstart activity into a single fresh ad group with a tighter keyword set, rather than continuing on the older "Car Jump Starts" group.

**Details:**
- Status: Enabled
- Bid: $5.00 CPC (matched what the old ad group was using)

---

### 1.2 Old ad group paused

**What:** Paused the previous **"Car Jump Starts"** ad group.

**Why:** So the new ad group replaces it cleanly. Only one live ad group at a time, per our current focus rule.

---

### 1.3 Keywords added

**What:** Added **17 keywords**, each in two match types (Phrase + Exact), to the new ad group. That's **34 total keyword entries**.

**The 17 terms:**

jump start · jumpstart service · car jump start · flat battery jump start · battery jump start service · mobile jump start · car won't start · jump start near me · mobile battery service · emergency jump start · 24 hour jump start · come to me jump start · flat battery help · car battery dead · battery won't start car · jump start Sydney · mobile mechanic flat battery Sydney

**Note on the name:** The ad group is called "20KAG" but has 34 keywords — the name is a label, not a literal count.

---

### 1.4 Ads cloned across

**What:** Copied the 3 currently-live Responsive Search Ads from the old ad group into the new one.

**The three ad angles:**

1. **Urgency** — "Call Now" pinned, "Vehicle Technicians Sydney"
2. **No-membership** — "Pay Per Job", "No Joining Fee"
3. **Mobile / come-to-you** — "24/7 Sydney Metro", "We Come To You"

All three set to Enabled.

---

### 1.5 CallRail conversion action fixed

There were two issues with how CallRail conversions were being recorded in Google Ads:

**Issue A — Wrong category:** The "Call Rail" conversion action was miscategorised as "Default" instead of "Phone call lead".

- **Fix:** Changed category from Default → **Phone call lead**.

**Issue B — Hard to identify:** Multiple actions in the account had "CallRail" in the name but only one was the real one.

- **Fix:** Renamed it to **"Call Rail 8/7/26"** so the latest-touched version is easy to spot.

**Effect:** The action now shows up correctly in the "Phone call lead" goal group in the Google Ads UI, and becomes eligible for Enhanced Conversions for Leads in future.

---

### 1.6 Bidding goals cleaned up (both campaign and account level)

Google Ads was optimising toward multiple conversion goals (form leads, YouTube views, "clicks to call", etc.) — most of which aren't relevant to Auto Hero. This meant the bidder was chasing signal that didn't match real business outcomes, and also risked double-counting real calls.

**What we did:** Made **CallRail phone calls the ONLY goal** Google Ads optimises for.

**At the campaign level (Jumpstart 14/04/2026):**

| Goal | Change |
|---|---|
| Phone call lead (Website) — where CallRail lives | ✅ **ON** |
| Default (Website) | ❌ OFF |
| Contact (Call from ads) | ❌ OFF |

**At the account level (defaults for any new campaign):**

| Goal | Change |
|---|---|
| Phone call lead (Website) — where CallRail lives | ✅ **ON** |
| Default (Website) | ❌ OFF |
| Submit lead form (Website) | ❌ OFF |
| Phone call lead (Call from ads) | ❌ OFF |
| Contact (Call from ads) | ❌ OFF |
| Engagement (YouTube) | ❌ OFF |
| YouTube follow-on views | ❌ OFF |

**Result:** Now there is exactly **one biddable goal** at both layers — CallRail phone calls. Any new campaign will inherit this correctly by default.

---

### 1.7 What we did NOT change

- Bid strategy (kept as-is — currently shows Maximize Conversions in the API but that's disputed vs. Manual CPC; left for another session)
- Budget
- Ad schedule (still 17:00–22:00 Sydney)
- Location targeting
- Negative keyword lists (auto-inherited by new ad group from campaign-level shared lists)
- Any of the 14 brand ad groups (Toyota, Ford, BMW, etc.) — still paused as before

---

### 1.8 Important watch-out (found in end-of-session health check)

The campaign **Jumpstart 14/04/2026** appears to be currently **PAUSED** at the master switch level (though it was Enabled when we started the session). All the improvements above are correctly configured but won't actually run until the campaign itself is re-enabled. Someone with account access needs to flip it back on when ready to serve.

---

## 2. Reading the Google Ads UI after the changes

When you open **Goals > Summary** you'll see multiple goal cards still labelled "Active". **That's expected** — it doesn't mean the bidder is using them.

### The word "Active" in this UI is misleading

- **"Active"** = the goal card is properly configured (has at least one enabled primary conversion action inside).
- It does NOT mean "the bidder is optimising toward this."

### The "Campaigns" column is the real signal

| Goal | Campaigns | What it means |
|---|---|---|
| **Phone call lead** | **3 of 3** ✅ | On every campaign (this is CallRail — exactly right) |
| Contact | 0 of 3 | Not applied to any campaign anymore ✅ |
| Get directions | 0 of 3 | Not applied to any campaign ✅ |
| Engagement | 0 of 3 | Not applied to any campaign ✅ |
| Page view | 0 of 3 | Not applied to any campaign ✅ |
| YouTube follow-on views | 0 of 3 | Not applied to any campaign ✅ |
| Submit lead form | 0 of 3 | Not applied to any campaign ✅ |

**Only Phone call lead is being used by any campaign.** The other six goal cards can sit there as "Active" all they like — they're not driving anything because no campaign is subscribed to them. This is the CallRail-only setup working correctly.

### Note on "Misconfigured" — pre-existing

The **Submit lead form** goal card shows "Misconfigured". This is a pre-existing setup issue with the "Website lead" conversion action (probably a missing tag on the site). It was not caused by today's changes, and it's safe to ignore because Auto Hero doesn't track form conversions.

### What you'd see if we hadn't done today's changes

Every one of those cards would say `3 of 3` in the Campaigns column instead of `0 of 3`. That was the "leaky defaults" problem — every campaign inheriting a goal set that included YouTube, forms, engagement etc. Now the leak is closed.

---

## 3. TL;DR

- Rebuilt the jumpstart ad group with cleaner keywords + copied over the working ads
- Fixed how CallRail conversion data is categorised in Google Ads (Default → Phone call lead)
- Locked down Google Ads to optimise for **only** CallRail phone calls — no more distraction from YouTube goals, form goals, or Google's native call tracking
- **Campaign is currently paused** — needs to be re-enabled before any of this serves

**One-line for someone skimming:**

> The other goals showing "Active" is normal — that just means the cards are set up correctly. The important thing is the "Campaigns" number: Phone call lead is on 3 of 3 campaigns, everything else is on 0 of 3. So the bidder is only chasing CallRail phone calls — everything else is dormant.

---

*Prepared for Matt Banks, Auto Hero (Sydney) — 08/07/2026 by Claude Code.*
