# D5 → A4 T1 restriction matrix (SO(10) → SU(5)×U(1))

Banked 2026-11-01. Hand-built — this pays the library's first debt.
`res_mat(A4, D5)` has no INFO entry (max_sub(D5) = B4, B2, A1B3,
B2B2, A3A1A1; the lookup errors "Group D5 has no maximal subgroup
of type A4"), so the matrix was constructed from the root subsystem.

## Construction

The SU(5) subsystem's simple roots are D5's α1..α4 (the e_i − e_{i+1}
chain). Feeding those roots (in D5 simple-root coordinates) to
`res_mat(R, D5)`:

    subr = [[1,0,0,0,0],[0,1,0,0,0],[0,0,1,0,0],[0,0,0,1,0]]

returns the A4-only matrix (first four columns below). The full
A4×U(1) restriction matrix, as returned by Resmat and used with the
target group `A4T1`:

    fullm = [[1,0,0,0,2],
             [0,1,0,0,4],
             [0,0,1,0,6],
             [0,0,0,1,3],
             [0,0,0,0,5]]

The last column is the U(1) charge functional: a D5 weight with
Dynkin labels (a1..a5) gets charge 2a1+4a2+6a3+3a4+5a5 = 2·(sum of
its epsilon coordinates) — the standard SO(10) X-charge
normalization (vector weights ±e_i carry ∓2 per side; the spinor
singlet carries ±5).

## Usage

    setdefault D5
    fullm = [[1,0,0,0,2],[0,1,0,0,4],[0,0,1,0,6],[0,0,0,1,3],[0,0,0,0,5]]
    branch([0,0,0,1,0],A4T1,fullm,D5)

For A4 content without charges, branch to `A4` with the first four
columns of fullm.

## Verification (both engines AGREE via lie_dispatch; dim sums exact)

Core set (script jobs/scripts/d5_a4t1_core.lie, hash a87fc10b57aa78c1;
adjoint also standalone, hash de5df00185175fe7):
- 10  → 5̄(−2) ⊕ 5(2)
- 16  [0,0,0,1,0] → 1(−5) ⊕ 5̄(3) ⊕ 10(−1)
- 16̄  [0,0,0,0,1] → 1(5) ⊕ 10̄(1) ⊕ 5(−3)
- 45  → 1(0) ⊕ 10̄(−4) ⊕ 10(4) ⊕ 24(0)

Extra set (script jobs/scripts/d5_a4t1_extra.lie, hash 06a0bb2ca0d9a7c1;
dim sums 54/120/126/126/210 verified per rep):
- 54  → 15̄(−4) ⊕ 24(0) ⊕ 15(4)
- 120 → 5̄(−2) ⊕ 10̄(6) ⊕ 10(−6) ⊕ 45(2) ⊕ 5(2) ⊕ 45̄(−2)
- 126 [0,0,0,2,0] → 1(−10) ⊕ 5̄(−2) ⊕ 15̄(6) ⊕ 10(−6) ⊕ 45(2) ⊕ 50(−2)
- 126̄ [0,0,0,0,2] → 1(10) ⊕ 10̄(6) ⊕ 50̄(2) ⊕ 5(2) ⊕ 45̄(−2) ⊕ 15(−6)
- 210 → 1(0) ⊕ 5̄(8) ⊕ 10̄(−4) ⊕ 40(4) ⊕ 10(4) ⊕ 75(0) ⊕ 5(−8)
        ⊕ 24(0) ⊕ 40̄(−4)

(A4 labels for the named pieces: 5=[1,0,0,0], 5̄=[0,0,0,1],
10=[0,1,0,0], 10̄=[0,0,1,0], 15=[2,0,0,0], 15̄=[0,0,0,2],
24=[1,0,0,1], 40=[0,0,1,1], 40̄=[1,1,0,0], 45=[0,1,0,1],
45̄=[1,0,1,0], 50=[0,2,0,0], 50̄=[0,0,2,0], 75=[0,1,1,0].)

All contents match the standard SO(10) → SU(5)×U(1) branching
tables, including the canonical 16 → 1(−5) ⊕ 5̄(3) ⊕ 10(−1).
The four core branchings are also in the branch battery
(battery/battery_branch.lie) so any future build/machine change
re-verifies them.
