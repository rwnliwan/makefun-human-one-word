# Trial log — makefun-human-one-word

Program: Your Human in One Word — $5, slug `u-ronigrv-your-human-in-one-word-e4569a1c`,
deadline 27 Nov 2026 00:30 WITA (2026-11-26T16:30:00Z). Harness program/v1.
Repo: `makefun-human-one-word`. Wallet (agent): `FwUebjzYUBF6uybmEkUkiQf9z35bGGQuUE3GrToXFcUq`.

## Gate (from `rules` STRING in comp-humanword.json, read in full 25 Nov 22:12 WITA)

- `/output/entry.txt` must be UTF-8 text of **1 to 30 characters**, not only white space.
  Only a valid entry goes before the judge; invalid = listed with 0, no rate, no prize.
- Judge: pairwise, model z-ai/glm-5.3-flash via OpenRouter; superbot, reasoning high,
  max 12,100 output tokens per verdict. Brief weighs, most important first:
  1. one word describing the human the entrant works for (a phrase/sentence or a word
     about anything else loses to any one word that describes the human);
  2. funny (a joke or wry observation, not a plain label);
  3. fits the human (reads as true of a boss/client/manager, not a random insult
     or stock compliment);
  4. vivid and specific (memorable, repeatable; not flat like fine/busy/okay);
  5. lands on its own, no explanation needed.
- Length for its own sake does not count. Each game = two calls (both orders);
  margin 1–5; winner takes 0.5 + margin/10 per call.
- 3 fixed house texts (anchors) + 3 rungs play in development heats only; an entry
  byte-identical to one of them shares its rate and never enters the playoff; an
  entry reproducing one (same bytes, or same words after case/whitespace) takes no
  prize. Anchors/rungs revealed only in the final kit — avoid any stock one-word
  label that could be a house text.
- Final heat: top 500 on the dev board (+ unrated entries); 3 Swiss rounds + playoff
  of top 5. Prizes: 1st $2, 2nd $2, 3rd $1 (total $5).
- Blind rounds: nothing judged/shown at submit time; rounds at cutoffs; latest entry
  (or picked final) is the one that counts. Max 5 submissions per entrant per UTC day.
- Entry text shows on the public Feed from the moment its dev grade is recorded.
- Submission names a public GitHub repo + commit + AI session transcripts; repo must
  have been created after the competition opened.
- README must carry 3 LIVE make.fun badges (program badge, rank badge, reward badge);
  a README with only static badges is refused by the server (422 repo_readme).
  Rank/reward badge URLs use the REPO NAME after the owner segment, not the slug.
- Repo must contain `.makefun/owner.json` with the agent wallet (server 422 repo_owner
  without it).
- GitHub About (homepage + topics makefun, ai-agents, bounties) must be set before
  submit; topics via PUT names[], verified with `gh api`.

## Field research (live API, 25 Nov 22:13 WITA, via curl)

- Live `submissionCount`: 572 (comp JSON snapshot said 465 — field grew fast).
- Titles: 572 total. 146 are exactly the competition name ("Your Human in One Word"),
  29 are "Your Human in One Word: <word>", 2 are "One word for the human...: <word>",
  228 are a single word, 108 are two-word display names (e.g. "Lucid Helix" — not
  entry words), rest other. Titles yielding a real entry word: **263 (denominator)**;
  distinct entry words: 153.
- Saturated entry words (exact, out of 263): overlord 14, taskmaster 12,
  bottleneck 11, puppetmaster 8, rubberstamp 7, insomniac 5, ringmaster 4,
  relentless 4, degen 4, ghost 4, octopus 4, gaspol 4.
- Saturated families: boss-as-tyrant (overlord/taskmaster/puppetmaster/ringmaster),
  blocker (bottleneck), approval-stamp (rubberstamp), no-sleep (insomniac/nightowl),
  -holic/-zilla/-lord compounds (bountyhound, bountyholic, grindfather, bosszilla,
  tasknado, scopecreeper, meetingaholic, signoffzilla, ...).
- Proof/evidence family: only 1 hit — "Trustfall" (a trust-exercise pun, different
  mechanism: falling backwards into trust, not demanding evidence). No entry about
  receipts, proof, verification, checking, or fact-checking in the whole field.

## The human (Septian Panjaya, 32, Data Analyst — finance risk)

- Verifies EVERY claim against disk + live source before believing it; turns each
  correction into a permanent rule the same session; judges like a QA lead.
- Decides fast in one-line messages ("Gas", "Acc"); runs a multi-agent fleet;
  reads documentation for fun; income via make.fun + bug bounties.
- The single most checkable truth about him: he demands proof. Everything must
  come with receipts.

## Candidate shortlist (all 0-hit exact in the 263 entry words)

- Receipts (8 chars) — CHOSEN. Slang for proof/evidence: the boss who always asks
  "receipts?". Funny (current idiom, wry), fits the verification obsession exactly
  and the finance-risk/fraud background (evidence-driven), vivid concrete noun,
  lands alone with no explanation. Family check: no proof/evidence/verify word in
  the field except Trustfall (different mechanism). Not a stock flat label, not a
  plausible house anchor.
- Polygraph (9) — runner-up. Human lie-detector image; vivid and funny, but a
  machine metaphor rather than a human behaviour, and less precisely Septian
  (he checks records, he does not read minds). Family empty, 0-hit.
- Bloodhound (10) — fraud/AML sniffer, relentless tracker; vivid. Rejected: shares
  the "-hound" suffix with Bountyhound x3 in the field (near-duplicate risk), and
  the sniffing angle is less central than the demand-for-proof angle.
- Microscope (10) — examines every detail; vivid. Rejected: "micro" prefix collides
  with Micromanager x2 (different mechanism, but the prefix echo is needless risk).
- Inquisitor (10) — interrogates every claim; vivid, dark-funny. Rejected: the
  inquisition image is harsher than Septian (he verifies, he does not torture) and
  less funny than Receipts.
- Redpen (6) — red-pens everything; vivid. Rejected: editorial angle, adjacent to
  the Nitpicker/Nitpickasso family already in the field.
- Factchecker (11) / Crosschecker (12) / Verifier (8) — literal, flat labels;
  fail criterion 2 (funny) and 4 (vivid).
- Gatekeeper — 1 hit in the field. Rejected (not 0-hit).
- Gasman / Acc / Oneliner — Septian's signature words, but they do not land alone
  for a judge who does not know him (fail criterion 5). Rejected.
- Wrangler / Auditor / Skeptic / Watchdog / Underwriter — flat or generic; fail
  funny/vivid vs Receipts. Rejected.

## Entry

- Word: `Receipts` — 8 characters (Python len: 8), one word, no spaces.
- Program: `main.py` writes exactly `Receipts` (no trailing newline, 8 bytes)
  to `/output/entry.txt`.

## Trials

- T1 (local preflight, 25 Nov 22:15 WITA) — PASS. `MAKEFUN_OUTPUT_DIR=/tmp/humanword-out
  python3 main.py` exit 0; `/tmp/humanword-out/entry.txt` = 8 bytes `Receipts`,
  UTF-8, 8 chars (within 1–30), single word, no spaces. README: 3 live badge
  URLs (`make.fun/badge/` count 3), repo name present in rank + reward badge
  lines; banned static-badge-service word count 0 across the repo (grep -ri,
  excluding .git). `.makefun/owner.json` present with the agent wallet.
  Default branch is `master` (verified via `.git/HEAD`).
- T2 (kit check v1, 25 Nov 22:17 WITA) — 13 passed / 1 failed / 5 skipped.
  Commit `761d179144d5fdac8c32d3ea086c17b1f90a96ab`, bundle v1 206,316 B
  sha256 `41ddd96f6d21e217f6e95f9c350e2eb8e6ac90fce25e6c3ad028281d5f25cbb0`.
  Passes: competition_open, snapshot (5 files, 10,546 B), license_osi (MIT),
  entrypoint (main.py → python3.13), transcripts_present/recorded,
  thinking_wellformed, thinking_in_window, thinking_reproduces 98.5%
  (138/140 lines authored, 0 pasted; main.py 18 authored lines),
  thinking_turns (41), thinking_revised (trial-log from 2 write/edit
  messages), transcripts_run_record, thinking_own_work (138/140).
  FAIL only: thinking_priced — 0 usage rows attached. Cause (bundle tool
  itself): this is a subagent session; its usage row is written only once
  the run completes. muse.db at bundle time held 2 rows, both the
  koordinator's (agent 9c19e3e2…), 0 for this builder session — correctly
  left out by the bundle. FIX (koordinator, after this run ends): re-run
  the MUSE_APP_USAGE_SELECT for both agent ids, re-bundle from the FINAL
  session file with --muse-usage, re-check — expect 14/0. Nothing else
  needs rebuilding. At-submission checks (repo_public, repo_owner,
  repo_created_after_open, commit_in_repo, duplicate_snapshot) are
  server-side at submit; repo is public, owner.json committed, repo
  created 2026-11-25T14:15:41Z (after opening 13:29:43Z), commit pushed.
- T3 (final verification, after T2 trial-log commit): HEAD lokal = ls-remote,
  tree bersih, README 3 live badges, owner.json ada, banned word 0. (Pending.)
