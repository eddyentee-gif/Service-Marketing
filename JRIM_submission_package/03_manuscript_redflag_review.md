# Red-Flag Review — JRIM_formatted_manuscript.docx + manuscript_IJEMR_tables.docx

Reviewed 2026-06-11 against Emerald/JRIM author guidelines and internal
consistency of the reported statistics. Verification method: full text
extracted from both .docx files; all reported correlations, R², f², path
coefficients and indirect effects were recomputed and cross-checked.

---

## A. Critical — fix before submission (reviewer-trust killers)

### A1. Hypothesis numbering is out of sync between the text and the tables
The manuscript text defines: H1 = PE→IJ, H2 = FE→CS, H3 = IJ→CS,
H4 = mediation, H5 = pathway comparison. The tables follow an older scheme:

- **Table 7** labels the PE→CS row "**Not supported (H1)**" — but in the text
  H1 is PE→IJ, which was *strongly supported* (β = 0.541). As written, the
  table tells reviewers your first hypothesis failed.
- **Table 7** gives no hypothesis labels to the IJ→CS (H3) and PE→IJ (H1) rows.
- **Table 8** says "Indirect-only mediation (**H3 supported**)" — mediation is
  **H4** in the text.
- **Section 2.5** (¶ beginning "This hypothesis is formulated at the level of
  comparative explanatory pathways…") says "**H4** compares the total
  evaluative pathways…" — it means **H5**.

This is classic version drift and is the single most damaging set of errors in
the package: it signals a hastily revised manuscript. Relabel everything to
the text's H1–H5 scheme.

### A2. The H5 variance-partition figures are not reproducible from your own tables
Reported: moral-relational pathway = **21.4** percentage points, instrumental
= **13.1** percentage points (sums exactly to R² = 34.5).

Recomputing the standard variance decomposition (Pratt measure, β × r) from
your own Tables 5, 7 and 9:

| Component | β | r with CS | Contribution |
|---|---|---|---|
| IJ → CS (moral-relational terminal path) | 0.420 | 0.515 | **21.6 pp** |
| FE → CS (instrumental path) | 0.280 | 0.386 | **10.8 pp** |
| PE → CS (residual direct, moral-relational side) | 0.061 | 0.346 | **2.1 pp** |
| Total | | | 34.5 pp = R² ✓ |

So the defensible figures are **21.6 vs 10.8** (with 2.1 pp residual direct
empathy contribution — which belongs conceptually to the moral-relational
side, not the instrumental side). 13.1 cannot be obtained unless the PE
residual is folded into the *instrumental* pathway, which would be
conceptually wrong — and even then it gives 12.9, not 13.1.

**Fix:** re-run the decomposition on the final PLS output, state the method in
§4.3.5 (e.g. "variance contributions computed as the product of each
standardized path coefficient and its zero-order correlation with CS (Pratt
measure)"), and report the reproducible numbers. H5's conclusion survives
either way — the moral-relational pathway still dominates (21.6 vs 10.8).

### A3. Anonymity leak in the Word file metadata
`docProps/core.xml` of the manuscript file contains:
`<dc:creator>Edward Entee</dc:creator>` and
`<cp:lastModifiedBy>Edward Entee</cp:lastModifiedBy>` — in a file whose own
subject line says "JRIM anonymized manuscript". ScholarOne does not strip
this. In Word: File → Info → Inspect Document → Document Properties &
Personal Information → Remove All, then save.

### A4. Tables file openly references another publisher
Line 2 of the tables document: "*supplied separately in line with
**Inderscience** preparation guidelines*" — and the filename contains
**IJEMR** (Inderscience's International Journal of Electronic Marketing and
Retailing). To a JRIM editor this reads as a recycled rejection. Delete the
sentence, rename the file (e.g. `JRIM_manuscript_tables.docx`), and sweep both
documents for any other journal's name.

### A5. Citation cited in text but missing from the reference list
"(Zhang et al., 2024; **Al-Shafei, 2025**)" in §2.3 — Al-Shafei (2025) does
not appear in the reference list. Emerald's production check and most
reviewers will catch this. Add the full reference or drop the citation.

### A6. Unfilled placeholders and author-notes left in the manuscript
- §3.3: "Ethical approval details **should be supplied in the final
  submission**… approval number [insert], approval date [insert]".
- "Declarations for submission" section: Funding, Conflict of interest, Data
  availability and AI-disclosure are all "[Insert …]" placeholders, with
  meta-instructions to yourself left in the running text.

Paste the finalized statements from `02_submission_statements.md` (blinded
ethics variant in the anonymized file) and delete every instruction-to-self.

---

## B. Major — likely reviewer objections

### B1. There are no figures at all
No conceptual-model figure and no structural-results figure. A JRIM PLS-SEM
paper is expected to include at minimum **Figure 1: research model** (and
ideally a results figure with path coefficients and significance). Their
absence weakens the H5 narrative in particular, which is inherently visual
(two competing pathways).

### B2. Power-analysis premise contradicts the tested model
§3.2: "Given the **maximum of two predictors** for customer satisfaction…" —
but the structural model regresses CS on **three** predictors (FE, IJ, and the
PE direct path, all reported in Table 7). Correct the G*Power input to three
predictors (conclusion will not change, but the inconsistency is conspicuous).
Relatedly, **Table 6 omits the PE→CS VIF row** even though PE→CS is in the
model — same version-drift fingerprint as A1.

### B3. Missing standard PLS-SEM reporting: Q²/PLSpredict and SRMR
§3.5/§4.3 report reliability, validity, paths, R², f² — but no predictive
relevance (Q² or PLSpredict) and no model fit (SRMR). Given the paper claims
PLS-SEM was chosen because "the model is prediction oriented", reviewers will
ask for PLSpredict specifically. Add both to §3.5 and a short results
paragraph (or table note).

### B4. H4 formally hypothesizes a null effect
H4 predicts "…the direct effect of perceived empathy on customer satisfaction
is **non-significant**." Predicting a null inside a hypothesis invites
methodological objections (NHST cannot confirm a null). Safer formulation:
H4 predicts the positive indirect effect through IJ; the attenuation of the
direct effect is then discussed as the indirect-only (full mediation) pattern
observed. Also unify terminology: §4.3.3 says "full mediation", Table 8 says
"indirect-only mediation (Zhao et al., 2010)" — Zhao et al. explicitly argue
*against* "full mediation" language, so standardize on **indirect-only**.

### B5. Reference-list inconsistencies vs the updated 2025 details you supplied
- **Wenger et al.**: text and Table 1 cite **(2026)** in *Communications
  Psychology* with no volume/pages/DOI; your updated list has the 2025
  PsyArXiv preprint. Pick one — if the Communications Psychology version is
  real, cite it with full details and change nothing in-text; otherwise revert
  to 2025 (which changes two in-text citations and Table 1).
- **Efthymiou et al. (2025)**: listed as "available at: SSRN 5367747" — your
  updated list says PsyArXiv with DOI. Also note it is cited only in Table 1,
  never in the running text; consider citing it in §2.2 where empathy-in-
  failure evidence is discussed.
- **Panarese et al. (2025)**: "AI and Society, pp.1-23" — replace with the
  updated Vol. 41 No. 4, pp. 2803-2825, doi: 10.1007/s00146-025-02451-2.
- **Han et al. (2025)**: initials "Kaas, M.H." vs "Kaas, M.H.L." in your
  updated list; DOI missing.
- **Zamora (2017)** appears in the reference list but is cited nowhere in the
  text or tables — delete or cite.

---

## C. Minor — desk-edit level

1. **Table numbering chaos**: placement markers use Roman numerals ("Insert
   Table I/II/…/IX"), the running text mixes both ("Table 2", "Table VII",
   "Table 9"), and the tables file uses Arabic. Standardize on Arabic
   throughout (current Emerald style).
2. **Abstract**: heading "Originality:" should be Emerald's
   "**Originality/value:**"; consider adding a one-sentence "Practical
   implications" sub-heading (~170 words used of the 250 cap, so there is
   room). "Perceived empathy does not directly **increase** satisfaction" →
   "is not directly **associated with**" for consistency with your own causal
   restraint.
3. **Title length**: 12 words vs Emerald's recommended ≤8. Acceptable but
   trimmable, e.g. "Beyond Efficiency: Interactional Justice in AI Service
   Encounters" (8 words).
4. **Table 9 vs text**: table interprets f² = 0.113 as "Small"; text (§4.3.4,
   §4.3.5) says "small-to-medium". Align (Cohen's benchmark: 0.113 is small,
   closer to medium than to 0.02 — "small" with the value reported is safest).
5. **Conclusion**: "justice perceptions, **which then drove** satisfaction" —
   causal verb; soften per statement 6.
6. **Reference formatting**: missing space after "pp." throughout
   (Emerald: "pp. 183-189"); Bies (2015) chapter lacks editor names; most
   references lack DOIs — Emerald requests DOIs where available.
7. **§2.1**: the coined definition of decoupled justice is wrapped in
   quotation marks twice in one sentence — restructure so the term is quoted
   once and the definition runs as plain text.

---

## What checks out (worth knowing)

- **The statistics are internally coherent.** Reported correlations
  (Fornell–Larcker matrix), path coefficients, R² (0.345; 0.292), all four f²
  values, and the indirect effect (0.541 × 0.420 = 0.227) all reproduce from
  each other almost exactly. Apart from the H5 partition figures (A2), the
  results read as genuine model output.
- Sample arithmetic is consistent (312 − 14 − 11 = 287; demographic
  percentages sum correctly).
- CMB handling (procedural remedies + Kock full-collinearity VIFs, all < 3.3)
  is the modern expected approach.
- HTMT (max 0.641) and Fornell–Larcker both clear thresholds comfortably.
- The cross-sectional causal-restraint language (statement 6) is present in
  §3.6 and §5.7 and the discussion mostly observes it.
- The body text is properly anonymized (no author names/affiliations) — only
  the file metadata leaks (A3).
- Word count ≈ 6,900 (manuscript) + tables ≈ 760 + 9 tables × 280 ≈ 10,200
  even after adding two figures — comfortably within a 12,000 cap.
- Interactivity framing is present ("AI service agents now sit at the front
  line of interactive marketing") — but could be reinforced with 2–3 more
  recent JRIM citations in §1 and §5.5.
