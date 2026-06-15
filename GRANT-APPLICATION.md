# Solana Foundation Nigeria Grant — Application

**Grant:** Solana Foundation Nigeria Grants (regional, administered by Superteam Nigeria)
**Submit at:** https://superteam.fun/earn/grants/solana-foundation-nigeria-grants/
**Status:** Open (rolling) · Funding range $1–$10,000 USDC · ~30-day response · Contact: nzubej@gmail.com
**Prepared:** 2026-06-15

---

## Step 1 — Basics

**Project Title**
> fair-tickets

**One-Line Description**
> On-chain event ticketing where a program-enforced resale price cap makes scalping impossible — not just against platform policy.

**Funding Requested**
> $3,000 USDC

**Telegram**
> t.me/G_Ojies

**X / Twitter**
> x.com/Great_ojies

**GitHub Profile**
> github.com/G-ojies

**Wallet Address**
> Use the Solana wallet already connected to the Superteam Earn profile (fill at submission time).

---

## Step 2 — Details

**Project Details / Problem & Solution**

> **Problem.** Event ticketing is a daily system distorted by middlemen. Resale price caps — where they exist — are *platform policy*, enforced by a marketplace that also profits from every resale (a direct conflict of interest) and trivially bypassed by selling off-platform. The ticket itself is just a row in a private database the platform controls; the holder has a claim, not custody.
>
> **Solution.** fair-tickets rebuilds primary and secondary ticket sales as a Solana program (Anchor 1.0 / Rust) where the resale ceiling is a property of the ticket, enforced by code. The organizer sets a `max_resale_price` at event creation, and the program rejects any listing above it — there is no resale path that bypasses the cap, because the program *is* the marketplace. The ticket is custody: `Ticket.owner` is the source of truth, and changing it *is* the transfer, settled atomically with payment in a single instruction (no double-sell, no "paid but didn't receive"). Resale is permissionless and peer-to-peer — no escrow, no gatekeeper. Check-in (`redeem`) disables further resale, closing the loop.
>
> **Public value.** It's fully open-source, does one thing well (fair primary + secondary sales with check-in, no feature creep), and serves as a clean reference implementation other Solana builders — especially in the Nigerian events space — can learn from and fork.

**Proof of Work**

> - **Public repo (code, tests, README with full Web2→Solana analysis):** https://github.com/G-ojies/fair-tickets
> - **Live on devnet — full lifecycle proven on-chain:** program `Ggb46RAz1cWos2fQp4eWorFPpjPWouTBzccyCDVMGcgU` (verified deployed). One ticket: primary sale → listed under the cap → resold to a second wallet at the capped price → checked in. Explorer tx links for all five instructions are in the repo's `SUBMISSION.md`.
> - **litesvm integration suite, all passing** — face price to organizer; listing above cap rejected / at cap succeeds; resale moves exactly the resale price to the seller; redeemed ticket can't be resold; only the owner can list.
> - **TypeScript CLI** drives every instruction and prints an Explorer link per transaction.

---

## Step 3 — Milestones

**Goals & Milestones**

> 1. **M1 — Mainnet-beta deployment** (by **Jul 7, 2026**): deploy with finalized upgrade-authority strategy and a security self-review.
> 2. **M2 — Minimal web client** (by **Jul 31, 2026**): organizer event creation + buyer purchase/resale UI, wallet-adapter connected.
> 3. **M3 — USDC payments** (by **Aug 20, 2026**): stablecoin payment alongside native SOL, so ticket pricing isn't exposed to SOL volatility.
> 4. **M4 — QR check-in flow** (by **Sep 5, 2026**): door-scan redemption at the venue.
> 5. **M5 — Live pilot** (by **Sep 30, 2026**): run one real Nigerian event end-to-end and gather feedback.

**Overall Deadline**
> September 30, 2026

**Primary KPI**
> Tickets sold + resold through the program on mainnet during the first pilot — target **100 on-chain ticket transactions in the first month**.

---

## Pre-submission checklist

- [x] Repo public & reachable (`github.com/G-ojies/fair-tickets`, HTTP 200, main in sync)
- [x] Program live on devnet (`Ggb46RAz1cWos2fQp4eWorFPpjPWouTBzccyCDVMGcgU`, verified via `solana program show`)
- [ ] Skim the live form for region-specific fields (e.g. "how does this benefit Nigeria" — M5 pilot answer covers this)
- [ ] Select payout wallet from Superteam Earn profile at submission
- [ ] Paste each block into the matching form field and submit
