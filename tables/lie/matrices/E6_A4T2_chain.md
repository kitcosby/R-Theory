# E6 → SU(5)×U(1)×U(1) chain — composed restriction matrix

Banked 2026-11-03. The chain E6 → SO(10)×U(1) → SU(5)×U(1)×U(1)
as a single restriction matrix, composed from the two banked
hand-built matrices (E6_D5T1_resmat.md, D5_A4_resmat.md).

## The composed matrix

Target `A4 T2`; a branched weight prints as
`[a1,a2,a3,a4, x, y]` — A4 Dynkin labels, then x = the charge from
the D5→A4 leg (the SO(10) X-charge normalization of
D5_A4_resmat.md), then y = the charge from the E6→D5 leg (the
normalization of E6_D5T1_resmat.md). Overall signs/scales of x and
y are the conventions of those two constructions; ratios and
relative signs are the invariant content.

    comp = [[0,0,0,0,0,-4],
            [0,0,0,0,5,-3],
            [0,0,0,1,3,-5],
            [0,0,1,0,6,-6],
            [0,1,0,0,4,-4],
            [1,0,0,0,2,-2]]

(rows = E6 simple roots in Bourbaki order; composed as
comp[:, 0:5] = M1[:, 0:5] · M2, comp[:, 5] = M1[:, 5], with M1 the
E6→D5T1 matrix and M2 the D5→A4T1 matrix.)

Usage: `branch(w, A4 T2, comp, E6)` with `setdefault E6`.

## Verification (both engines AGREE, hash aefe4e02c22a8c13)

- Cross-check: branching the 27 through the composed matrix gives
  a polynomial **identical** to branching in two steps (E6 → D5T1,
  then the result → A4T2 by the step-2 matrix). The composition is
  exact.
- Dim sums (A4 parts) exact for every rep branched: 27, 27̄, 78,
  351, 351̄, 650.
- Conjugation closes: the 27̄/351̄ tables are the charge-negated
  conjugates of the 27/351 tables; the 78 and 650 are
  self-conjugate as required.

## Tables (named SU(5) pieces; charges as (x, y))

27 → 1(0,−4) ⊕ 1(−5,−1) ⊕ 5̄(−2,2) ⊕ 5̄(3,−1) ⊕ 10(−1,−1) ⊕ 5(2,2)

27̄ → 1(0,4) ⊕ 1(5,1) ⊕ 5̄(−2,−2) ⊕ 10̄(1,1) ⊕ 5(−3,1) ⊕ 5(2,−2)

78 → 1(−5,3) ⊕ 2·1(0,0) ⊕ 1(5,−3) ⊕ 5̄(3,3) ⊕ 5(−3,−3)
     ⊕ 10̄(−4,0) ⊕ 10̄(1,−3) ⊕ 10(−1,3) ⊕ 10(4,0) ⊕ 24(0,0)
     (grouped by the D5 leg: the y=0 sector is 45 ⊕ 1 of SO(10);
     the y=±3 sectors are the two spinors)

The 351, 351̄, and 650 branchings (21–31 terms each) are in the
dispatch cache record aefe4e02c22a8c13 verbatim; their D5-leg
intermediates for the 351 are banked in E6_D5T1_resmat.md.
Script: jobs/scripts/e6_su5_chain.lie.
