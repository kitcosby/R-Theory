# E6 → D5 T1 restriction matrix (E6 → SO(10)×U(1))

Banked 2026-11-03 (branching-claim audit). Hand-built — `res_mat`
has no D5T1 entry for E6 (max_sub(E6) = C4, F4, A2, G2, A2G2,
A5A1, A2A2A2), same gap class as D5→A4.

## Construction

The D5 subsystem of E6 (Bourbaki numbering: chain 1-3-4-5-6, node 2
on node 4) is the root set {α2, α3, α4, α5, α6} — deleting node 1
leaves a D5 diagram with branch point α4. Ordered as D5 simple
roots (β1..β5) = (α6, α5, α4, α3, α2) (α3 and α2 are the two fork
tips), in E6 simple-root coordinates:

    subr = [[0,0,0,0,0,1],
            [0,0,0,0,1,0],
            [0,0,0,1,0,0],
            [0,0,1,0,0,0],
            [0,1,0,0,0,0]]
    rmat = res_mat(subr, E6)

## Verified branchings (both engines AGREE, hash f0b4415d0a21ae59)

Charges in this matrix's normalization (overall sign is a
convention of the construction; ratios are the invariant content):

- 27  → 1(−4) ⊕ 16(−1) ⊕ 10(2)     [16 = D5 label [0,0,0,1,0]]
- 27̄  → 1(4) ⊕ 16̄(1) ⊕ 10(−2)
- 351 → 16̄(5) ⊕ 16(−1) ⊕ 120(2) ⊕ 45(−4) ⊕ 10(2) ⊕ 144(−1)
  (dim sum 16+16+120+45+10+144 = 351)

Usage: branch([1,0,0,0,0,0], D5 T1, rmat, E6) with setdefault E6.
