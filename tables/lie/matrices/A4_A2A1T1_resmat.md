# A4 → A2 A1 T1 restriction matrix (SU(5) → SU(3)×SU(2)×U(1))

Banked 2026-11-03 (branching-claim audit, for the Book 11 J-claims).

## Construction

Subsystem roots of A4: A2 on nodes {1,2} (the ℂ³ block), A1 on
node {4} (the ℂ² block):

    subr = [[1,0,0,0],[0,1,0,0],[0,0,0,1]]
    rmat = res_mat(subr, A4)

## Verified branchings (both engines, script audit_j.lie)

Charge scale of this matrix: charge = −6 × (the books' Y), i.e.
the doublet/triplet block charges come out in ratio −3 : +2 where
the books use +1/2 : −1/3 — same ratios, opposite overall sign
(convention of the construction).

- 5  → (3,1)(+2) ⊕ (1,2)(−3)     [labels (A2 | A1 | charge)]
- 5̄  → (3̄,1)(−2) ⊕ (1,2)(+3)

These are exactly the Book 11 contents: with Y-normalization,
5 → (1,3)_{−1/3} ⊕ (2,1)_{+1/2} in (SU(2), SU(3)) order, and the
Λ^even(W) charge table of 11.IV.T2 follows arithmetically from
block charges (c₂, c₃) = (+1/2, −1/3) (verified by hand in the
audit report).
