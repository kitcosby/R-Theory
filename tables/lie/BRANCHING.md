# LiE library — banked facts (verified, do not re-derive)

Entry rule: both engines via `lie_dispatch.py` at proved grade + dim-sum
pass, with source named. Anything not listed here is NOT banked.

## Dimensions / tensors (Stage 2 rotation, 2026-10-31; battery-verified 2026-11-01)

- A4: dim([1,0,0,1]) = 24 (adjoint of SU(5)); dim([0,0,0,1]) = 5 (W′);
  dim([0,0,1,0]) = 10 (Λ²W′ piece); tensor([0,0,0,1],[1,0,0,0]) =
  1X[0,0,0,0] + 1X[1,0,0,1] — i.e. End(W′) = 1 ⊕ 24.
- A2: dim([1,1]) = 8; A1: dim([2]) = 3 — stabilizer type s(u(3)×u(2))
  dimension 8+3+1 = 12 (Stage 2 step 8).
- D5: spinors dim([0,0,0,0,1]) = dim([0,0,0,1,0]) = 16; vector 10;
  adjoint 45.

## Branching via res_mat (LiE maximal-subgroup database)

- E6 ⊃ A5 A1: 27 [1,0,0,0,0,0] → 1X[0,0,0,0,1,1] + 1X[0,1,0,0,0,0]
  (dims 12 + 15 = 27); 27̄ [0,0,0,0,0,1] → 1X[0,0,0,1,0,0] +
  1X[1,0,0,0,0,1] (dims 15 + 12 = 27). (Both engines AGREE,
  2026-11-01 post-repair, battery_branch. An earlier note attributing
  the 27 line to 27̄ was wrong and is corrected here; the battery
  caught it.)
- E6 ⊃ A2 A2 A2: 27̄ → 1X[0,0,1,0,1,0] + 1X[0,1,0,1,0,0] + 1X[1,0,0,0,0,1]
  (9 + 9 + 9). (Both engines AGREE, 2026-11-01 post-repair.)
- D5: 16 ⊗ 16̄ = 1X[0,0,0,0,0] + 1X[0,0,0,1,1] + 1X[0,1,0,0,0]
  (1 + 210 + 45 = 256). (Both engines AGREE, 2026-11-01, core battery.)
- E6: dim 27 = 27̄; adjoint dim([0,1,0,0,0,0]) = 78.
- E8: adjoint 248; dim([1,0,0,0,0,0,0,0]) = 3875. (Audit context only —
  geometry-first wall stands; scope labels unchanged.)

## E8 branching (audit context; geometry-first wall stands)

- E8 ⊃ D8 (so(16)): 30380 [0,0,0,0,0,0,1,0] → 13312 ⊕ 8008 ⊕ 7020 ⊕
  1920 ⊕ 120, the 1920 being [1,0,0,0,0,0,1,0]. (LiE both engines
  AGREE, hash e951da1299f3552b; Sage Weyl-character tie-break on toe
  agrees exactly, 2026-11-01.) **Corrects the 2026-10-05 banked
  15·128 term** — see io_word_sweep/CORRECTION_30380_D8_2026-11-01.md.
  Controls on this embedding: 248 → 120 ⊕ 128; 3875 → 135 ⊕ 1820 ⊕ 1920;
  m_1820(30380) = 0 in all methods.
- E8 30380 census (all both-engines AGREE + dim-sum = 30380, 2026-11-01;
  full polynomials in the workflow cache under the named hashes):
  A8 — 16 terms (ca74b07033c4cbed); E7 A1 — 10 terms (6402f3e9a7127552);
  E6 A2 — 23 terms (96049ea706f3bbaf); A4 A4 — 48 terms (6f91c57f05f26f36);
  G2 F4 — 17 terms (16c54f97afb6cdad). Scripts: lie-workflow jobs/scripts/30380_*.lie (hashes cited inline).
  Tensor control: ∧²(248) = 248 ⊕ 30380 (27ecacfbf6162b3f), and
  branch(∧²248→D8) − branch(248→D8) = branch(30380→D8) exactly
  (2db30bcadfd5db8c).

## Branching-claim audit — 2026-11-03

Every branching/tensor claim in the DB and text record verified
both-engines (report: `AUDIT_REPORT_2026-11-03.md` (this folder)). All
correct as stated except one notation inconsistency: the 248's
spinor sector under D5×A3 is (16,4) ⊕ (16̄,4̄) under the record's
node conventions (manuscript line 2241's form); three other
manuscript occurrences write the conjugate pairing. Newly banked
here: Sym²(248) = 1 ⊕ 3875 ⊕ 27000; the full 30380⊗30380
(18 terms, Sym² list matching §16.I.71.1 term for term);
27000 ↓ D8 = 1 ⊕ 128 ⊕ 1820 ⊕ 5304 ⊕ 6435 ⊕ 13312; D8 spinor
squares Sym²(128±) = 1 ⊕ 1820 ⊕ 6435, Λ²(128±) = 120 ⊕ 8008;
Sym²(120) = 1 ⊕ 135 ⊕ 1820 ⊕ 5304; 120⊗128 = 128 ⊕ 1920 ⊕ 13312;
135 and 1820 ↓ D5A3 (E1/E2 of the report); A2/A1 tensor facts
(3⊗3̄, 3⊗3, 3⊗3⊗3, 2⊗2); E6→D5T1 and A4→A2A1T1 matrices
(the `matrices/` folder here).

## E6 → SU(5)×U(1)×U(1) chain — BANKED 2026-11-03

Composed restriction matrix E6 → A4 T2 (full record:
`matrices/E6_A4T2_chain.md`), built from the E6→D5T1 and
D5→A4T1 matrices; cross-checked one-step vs two-step on the 27
(identical), both engines AGREE (aefe4e02c22a8c13), dim sums exact
for 27, 27̄, 78, 351, 351̄, 650. Charges (x, y) = (D5-leg X-charge,
E6-leg charge), conventions of the two matrix files:
- 27 → 1(0,−4) ⊕ 1(−5,−1) ⊕ 5̄(−2,2) ⊕ 5̄(3,−1) ⊕ 10(−1,−1) ⊕ 5(2,2)
- 78 → 1(−5,3) ⊕ 2·1(0,0) ⊕ 1(5,−3) ⊕ 5̄(3,3) ⊕ 5(−3,−3)
  ⊕ 10̄(−4,0) ⊕ 10̄(1,−3) ⊕ 10(−1,3) ⊕ 10(4,0) ⊕ 24(0,0)

## D5 → A4 T1 (SO(10) → SU(5)×U(1)) — BANKED 2026-11-01

Hand-built restriction matrix (full record:
`matrices/D5_A4_resmat.md`). `res_mat(A4, D5)` has no INFO
entry (max_sub(D5) = B4, B2, A1B3, B2B2, A3A1A1); the matrix was
built by `res_mat(R, D5)` from the subsystem roots α1..α4 and
carries the U(1) charge column (charge = 2a1+4a2+6a3+3a4+5a5).
Verified both-engines AGREE + dim sums (hashes a87fc10b57aa78c1,
de5df00185175fe7, 06a0bb2ca0d9a7c1); core four are in the branch
battery:
- 10 → 5̄(−2) ⊕ 5(2); 16 → 1(−5) ⊕ 5̄(3) ⊕ 10(−1);
  16̄ → 1(5) ⊕ 10̄(1) ⊕ 5(−3); 45 → 1(0) ⊕ 10̄(−4) ⊕ 10(4) ⊕ 24(0)
- 54 → 15̄(−4) ⊕ 24(0) ⊕ 15(4); 120, both 126s, 210 — in the
  matrices file. The former library debt is PAID.
