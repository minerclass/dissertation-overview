# Agent Log

Append-only. Newest entry first. No participant data, committee or faculty names,
credentials, or tokens.

---

## 2026-08-31 - Adopt the shared ecosystem design tokens

Links https://minerclass.github.io/tokens.css before the inline styles and points the
ground, panels, ink, muted, and rules at the shared tokens. The dark ground is unchanged
in character. The green `--accent` and blue `--link` stay local.

Every reference carries a fallback equal to the pre-adoption value, so a failed token
load leaves the page exactly as it was.

**Verified.** 102 text-bearing elements probed against their composited backdrops:
**zero** failures both with and without the token sheet. Tightest pair 5.18 against 4.5.

---

## 2026-08-31 — Friction matrix and convergent-design flowchart

**Context.** Worked from an agent handoff document titled "Dissertation Repositories
Visual Modernization & Streamlining," Tier 1 scope.

**Correction made before any edit.** The handoff's methodology section specified a
"Merriam-aligned single bounded case study" that "explicitly rejects Stake's collective
case design and Yin's postpositivist framing," and listed three participant groups. This
was checked against the controlling Chapters 1–3 and is wrong on both counts:

- The controlling proposal is titled *A Qualitative-Dominant Convergent Mixed Methods
  Study*. Full-text search returns **zero** occurrences of "case study," "Merriam,"
  "Stake" (as a citation), or "Yin."
- RQ1 names **four** participant perspectives, not three. Adult university students are
  participants contributing retrospective learner accounts.

The handoff's standardized "RQ Bridge Card" hardcodes the three-group framing and labels
RQ1 "Educator Sensemaking." It was **not** deployed. Rolling it out as written would have
propagated a methodology the proposal does not claim across the public ecosystem.
Confirmed with the author on 2026-08-31 that the controlling proposal governs.

**Changed.** `index.html` only. All pre-existing copy, including the canonical-entry note,
the study-status block, and the "explanatory only" notice, was left untouched.

- Added *The four dimensions of friction* — a four-cell matrix with a
  classroom/policy consequence toggle. Definitions are taken from the controlling
  proposal verbatim in substance. The infrastructural cell spans the grid and carries a
  distinct accent and a "system-level" role label, because the framework treats it as the
  institutional condition enabling or constraining the three learner-facing dimensions,
  not as a fourth peer. A flat 2×2 of equals would have misrepresented this.
- Added *How the strands fit together* — a convergent-design flowchart built from
  semantic HTML (not a fixed-viewBox SVG) so it reflows to one column and reads in source
  order. Shows concurrent QUAL-priority and complementary quan strands, separate analysis,
  integration at interpretation via joint displays organized by research question, and the
  nonparticipant AI-artifact comparison held deliberately apart.
- Added a page-wide `:focus-visible` ring (there was none), a
  `prefers-reduced-motion: reduce` block, and an `.sr-only` status region announcing
  toggle changes.

**Framing guard.** Consequence text under each dimension is labelled in-page as an
illustrative reading of the framework, explicitly not a finding, with a restatement that
no participant data has been collected. No numbers from the national survey datasets were
placed on this page, to avoid any reading that they are this study's results.

**Verified.** Served locally and checked in a real browser:

- Tag balance parsed clean; zero console errors.
- Toggle swaps all four cells and updates `aria-pressed` correctly (confirmed via
  computed styles, not just screenshot — an early screenshot was captured mid-repaint and
  looked wrong).
- 1440px: two-column matrix, side-by-side strands, infrastructural spans `1 / -1`,
  `scrollWidth === clientWidth`.
- 375px: single column, **zero** horizontally overflowing elements.
- Keyboard: real Tab press moves focus between toggles and the button matches
  `:focus-visible`.

**Fixed during verification.** The first mobile pass overflowed by 27px. Cause was a bare
`1fr` track (floors at min-content) combined with `white-space: nowrap` on the long
system-level role label. Changed to `minmax(0, 1fr)` and allowed the label to wrap once
the head stacks.

**Not done, deliberately.** No commit or push — this machine has no configured git
identity or credentials, so the change is left in the working tree for the author to
review and push. No RQ Bridge Card, pending the corrected wording described above.

**Open.** The handoff's §2.1 and its verification checklist item 1 still carry the
incorrect case-study framing and should be corrected at the source before any other agent
executes from that document.
