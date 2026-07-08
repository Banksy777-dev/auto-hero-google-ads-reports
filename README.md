# Auto Hero Google Ads — Change Log

Session recaps for the Auto Hero Google Ads account (947-503-9797), Sydney roadside battery + jumpstart service.

Each session's changes are written in plain English, in the order they happened, so anyone with account access can follow what changed and why.

---

## Sessions

| Date | Summary |
|---|---|
| [09/07/2026](reports/2026-07-09.md) | Campaign re-enabled + bid strategy and budget verified against API (records updated) |
| [08/07/2026](reports/2026-07-08.md) | New 20KAG ad group + keywords + RSAs, CallRail conversion action fix, CallRail-only bidding goals |

Latest session is always at the top.

---

## Latest session — 09/07/2026

Short session — getting the campaign back to serving after yesterday's build, and correcting two facts in our records that turned out to be wrong.

### Key changes

- **Campaign enabled.** `Jumpstart 14/04/2026` flipped from PAUSED to ENABLED. Status verified: SERVING + ELIGIBLE.
- **Bid strategy verified.** The API shows the campaign is on **Maximize Conversions** (smart bidding, no target CPA). Prior records said Manual CPC — that was outdated. No change to strategy made this session.
- **Budget verified.** The API shows **$100/day**, not $50/day as prior records indicated. Someone raised the budget at some point without it being logged. Left at $100/day.
- **No target CPA added.** Given only 7 conversions in the last 30 days (below the ~30 conv/30d floor smart bidding needs to hit a target reliably), adding a $40 tCPA now could throttle serving. Deferred until conversion volume is higher.

### Serving expectations

Campaign is ENABLED but the ad schedule is **17:00–22:00 Sydney**, so first impressions will land at 17:00 today.

### Watch-outs

- Soft `HAS_ADS_LIMITED_BY_POLICY` warning still on the campaign — legacy flag from paused ads elsewhere in the campaign. All live ads are APPROVED.
- Call-asset render rate was 15.5% in the 7d pre-pause — worth checking Friday.
- Top-of-page impression share on mobile 25.6%, rank-lost impression share 54.5% — Ad Rank / Quality Score is the ceiling, not budget.

Full detail: [reports/2026-07-09.md](reports/2026-07-09.md).

---

## Previous sessions

### 08/07/2026 — Ad group rebuild + CallRail-only conversion setup

The big structural session. Highlights:

- Built new ad group **"20KAG - Jumpstart"** inside the Jumpstart campaign, with 17 keywords (Phrase + Exact = 34 entries) and the 3 top-performing RSAs cloned from the old ad group.
- Paused the older "Car Jump Starts" ad group.
- Fixed the CallRail conversion action — corrected category from Default → Phone call lead, renamed to `Call Rail 8/7/26` for easy identification.
- Locked down bidding goals at both campaign and account level so Google Ads optimises only for CallRail phone calls — no more distraction from YouTube, form leads, or Google's native call tracking.
- Reconciled CallRail export vs Google Ads: 35 of 38 qualifying calls captured (92%) — the missing 3 all lacked a `gclid` (iOS-only `gbraid` or direct-dial ad-extension), which is a known Google/CallRail attribution limit.

Full detail: [reports/2026-07-08.md](reports/2026-07-08.md).

---

## Account context

- **Business:** Auto Hero — mobile onsite battery replacement + emergency jumpstarts across Sydney metro (25km radius from Wentworth Point 2127).
- **Google Ads ID:** 947-503-9797
- **Live campaign:** `Jumpstart 14/04/2026` (`23745071702`)
- **Ad schedule:** 17:00–22:00 Sydney
- **Bidding:** Maximize Conversions (no target CPA), $100/day
- **Conversion source of truth:** CallRail webhook upload → conversion action `Call Rail 8/7/26` (ID 7587485451)

---

*Maintained by Matt Banks + Claude Code. Sessions logged as they happen.*
