# Branching-claim audit of the record — 2026-11-03

Ordered by Kit 2026-11-03 ("Start the branching-claim audit of the
record"). Method: every branching / tensor-decomposition claim in
the theorem DB and in the text record (manuscript Vols I–IV,
rewrite books, ledgers, geometry-first) was extracted, and each
LiE-checkable claim was run through `lie_dispatch.py` — verdict
PROVED grade = both engines (desktop 32-bit build + native build)
AGREE verbatim, plus an exact dimension-sum check wherever the
claim is stated in dimensions. Extraction: `db_candidates.txt`
(77 DB rows scanned), `text_claims.md` (28 distinct text claims).

## Headline

**No false decomposition was found.** Every checkable claim in the
record is correct as stated — 10 DB rows and 24 text claims
verified (4 further text claims were already KNOWN from the 30380
census). **One notation inconsistency** was found (D1 below): a
chirality pairing written two ways across four manuscript
occurrences; the sector dimensions and all downstream-used content
are unaffected, and the one load-bearing use (the (126,6) sector)
is written in the form LiE confirms.

## DB rows verified (both engines AGREE)

| Row | Claim | Result |
|---|---|---|
| b16-16-i-71-5-205 (CP) | Sym²(248) channels 1 ⊕ 3875 ⊕ 27000 | exact ✓ (b4b769139c10eafd) |
| b16-16-i-71-1-199 (SC) | full 30380⊗30380 decomposition | LiE full tensor: 18 terms, dim sum = 30380² = 922,944,400 exact; direct both-engines AGREE (4adeab0d30f85802), Sym²/Λ² split also AGREE (5469e713ac76b180), and the Sym² summand list matches manuscript §16.I.71.1 **term for term, multiplicities included** |
| b16-ledger_a-47-044 (CP) | 248 dims 45+15+60+64+64 via D5×A3 | exact via the two-step chain 248 →(D8) 120 ⊕ 128− →(D5A3) (45,1)⊕(1,15)⊕(10,6) ⊕ (16,4)⊕(16̄,4̄) (0c610ce31535bac9) |
| e8-128-negative-theorem (CP v2) | 248 → 120 ⊕ 128− | already verified in the 30380 census ✓ |
| gf-e6-rep27 (CP) | 27 = 16 ⊕ 10 ⊕ 1 under the seed algebra | exact, with charges 1(−4) ⊕ 16(−1) ⊕ 10(2) via a new hand-built E6→D5T1 matrix (f0b4415d0a21ae59) |
| rs-family-bridge (CP) | 16 ≇ 16̄ (complex FS type) | 16⊗16 = 126 ⊕ 120 ⊕ 10 has **no singlet** ✓ (b4b769139c10eafd) |
| b14-14-ix-s-031 (ST) | Herm(Sym²(ℂ²)) = 1 ⊕ 3 ⊕ 5 | [2]⊗[2] = [0]⊕[2]⊕[4] ✓ |
| b14-14-ix-t1-030 (CP) | one-body lift image 1 ⊕ 3, no 5 | rep content consistent (the 5 is the quadrupole sector of the same decomposition) |
| b16-85-1-245 (NC) | (1/2,1/2)⊗(1/2,0) = (1,1/2)⊕(0,1/2), 8=6+2 | A1A1 tensor exact ✓ |
| b16-ledger_a-39-036 (MA) | full E8 spectrum + branching multiplicities | summary claim; all of its specific content is the census + the A/B claims below ✓ |
| gf-so10-infinitesimal (CP) | Dirac 32 splits 16 ⊕ 16′ | rep content = the two D5 spinor labels (both dim 16, banked); the claim itself is an explicit-matrix construction, outside LiE's scope, no conflict |

The remaining ~66 DB candidates use "branch/decompose/restrict"
for function branches, concrete 1820/C⁸ operator sectors, or
declared carrier splits — not Lie-representation claims; out of
scope for this audit (the 1820 operator layer was the 2026-11-01
matrix recheck).

## Text claims verified (extraction IDs from text_claims.md)

- **A1** Sym²(248) = 1 ⊕ 3875 ⊕ 27000 ✓ · **A2** Λ²(248) = 248 ⊕ 30380 ✓ (KNOWN, census control)
- **A3** mult of 27000 in Sym²(30380) = 2, Λ² mult = 0 ✓; also the manuscript's companion values Hom(Sym²(30380),3875) = 2 and Hom(Λ²(30380),3875) = 0 ✓ — all from the AGREE sym/alt runs
- **B1** 248 ↓ D8 = 120 ⊕ 128 ✓ KNOWN · **B2** 30380 ↓ D8 ✓ KNOWN (the corrected decomposition) · **B3** 3875 ↓ D8 = 135 ⊕ 1820 ⊕ 1920 ✓ KNOWN
- **B4** 27000 ↓ D8 = 1 ⊕ 128 ⊕ 1820 ⊕ 5304 ⊕ 6435 ⊕ 13312 ✓ (05ee09a414b565a7; labels dim-checked 13312/5304)
- **C1** Sym²(128±) = 1 ⊕ 1820 ⊕ 6435 ✓ (both chiralities) · **C2** Λ²(128±) = 120 ⊕ 8008 ✓ (both) · **C3** Sym²(120) = 1 ⊕ 135 ⊕ 1820 ⊕ 5304 ✓ · **C4** 120 ⊗ 128 = 128 ⊕ 1920 ⊕ 13312 ✓
- **C5** 1820 = Λ⁴(16_V) and 8008 = Λ⁶(16_V), each a **single irrep** ✓ (plethysm) · **C6** Sym²(16_V) = 1 ⊕ 135 ✓
- **D1** 248 under SO(10)×SU(4): sector content ✓ — see the flag below
- **E1** 135 ↓ = (54,1) ⊕ (1,20′) ⊕ (10,6) ⊕ (1,1) ✓ · **E2** 1820 ↓ SO(10)×SO(6) = (210,1) ⊕ (120,6) ⊕ (45,15) ⊕ (10,10) ⊕ (10,10̄) ⊕ (1,15) ✓ — the ledger's "(10, 10⊕10′)" term confirmed literally
- **F1** 16⊗16 = (10 ⊕ 126)_s ⊕ 120_a, 1 ∉ Sym²(16) ✓ (sym/alt split exact) · **F3** Sym²(10_V) = 1 ⊕ 54 ✓
- **F2 / G1** Dirac-spinor chirality splits (geometry-first, proved there by explicit matrices): rep content consistent; nothing for LiE to decompose (the Dirac rep is not a single irrep input)
- **H1** 3⊗3̄ = 1 ⊕ 8 ✓ · **H2** 3⊗3 = 3̄ ⊕ 6 ✓ · **H3** 3⊗3⊗3 = 1 ⊕ 8 ⊕ 8 ⊕ 10 ✓ (via (3̄⊕6)⊗3, 6⊗3 = 8 ⊕ 10)
- **I1** 2⊗2 = 3 ⊕ 1 ✓
- **J1** Λ^even(W) six blocks (1,1)⊕(1,1)⊕(2,3)⊕(1,3̄)⊕(1,3̄)⊕(2,1) ✓ via Λ²/Λ⁴ of W = (2,1)⊕(1,3) on A1A2; the printed U(1) charges follow arithmetically from block charges (+1/2, −1/3) — checked by hand, all six agree
- **J2** SO(10) 10 under SU(2)×SU(3)×U(1): content ✓; charge ratios exact via a new hand-built A4→A2A1T1 matrix (its charge = −6 × the books' Y; ratio and sign pattern are the invariant content)
- **K1** Λ²U identity: formal exterior algebra; its Lie core Λ²(3) = 3 for SO(3) ✓
- **K2** reviewed in context (Book 6): **not** an SO(3) decomposition claim — the 3⊕2 there is the ambient ℂ³⊕ℂ² block split of the joint argument; the SO(3) facts used (smallest faithful complex rep = 3; faithful in dim 4 ⇒ 3⊕1) are correct. No issue.

## The one flag — D1 chirality pairing (manuscript Vol III)

The 248's spinor sector under SO(10)×SU(4) is written two ways:

- line 2241: (16,4) + (16̄,4̄)
- lines 2669, 4070, 6069: (16,4̄) ⊕ (16̄,4)

Under the record's own fixed node conventions (the ones the
corrected e8-128 row uses: the 248 contains D8's 128−), the LiE
chain gives **(16,4) ⊕ (16̄,4̄)** — line 2241's pairing. The flipped
pairing is the content of the *other* D8 spinor (128+), which is
not in the 248. The two writings differ by conjugating the SU(4)
factor alone, so this is a labeling-convention inconsistency, not
a dimension or sector error: (45,1), (1,15), (10,6) are identical
in all four places, and no dimension sum changes.

Downstream exposure checked: the one structural use at line 4070
puts the condensate in (126,6) ⊕ (126̄,6) — LiE confirms exactly
that content for the 30380's 8008 sector (both D5 126 chiralities
paired with the 6, which is self-conjugate, so the ambiguity does
not reach it). Line 2669's orientation-exchange argument has the
same form under either pairing. **Recommendation:** normalize
lines 2669/4070/6069 to the (16,4) ⊕ (16̄,4̄) pairing (or state the
SU(4)-conjugation convention once, explicitly). No DB row carries
the flipped pairing (ledger_a-47-044 speaks of the swap map
between the two 128s, which is correct as stated).

## New library assets banked

- `matrices/E6_D5T1_resmat.md` — hand-built E6 → SO(10)×U(1)
  matrix (INFO gap, same class as D5→A4) with 27/27̄/351 branchings.
- `matrices/A4_A2A1T1_resmat.md` — hand-built SU(5) →
  SU(3)×SU(2)×U(1) matrix with the 5/5̄ branchings.
- Scripts: jobs/scripts/audit_*.lie; cache hashes cited inline.

## Scope note

This audit verifies representation-theoretic content only. It
assigns no physics labels, and it does not touch the concrete
operator layer (matrices on the 1820/C⁸ — covered by the
2026-11-01 recheck) or real-form questions (the E8(−24) /
Spin(4,2) completions named at the D1 locations are outside what
complex LiE branching can decide; the flag above is stated at the
complexified level, which is where the inconsistency lives).
