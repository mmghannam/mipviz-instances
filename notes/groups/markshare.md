# markshare

The **market share** problem, introduced by Cornuéjols and Dawande
(1998) as a family of deliberately hard equality-constrained 0/1 integer
programs. Each row is a near-balanced linear combination of binary
variables, with an RHS chosen so that every feasible point is extremely
rare. The instances are small — a few hundred variables — but the LP
relaxation is very weak and branch-and-bound explodes combinatorially,
which made them a popular stress test for MIP solvers and cut
generators.

## Why they are hard

- **Tight equality rows** leave almost no slack, so the LP relaxation
  produces fractional solutions that are nowhere near any feasible
  integer point.
- **No structure for conventional cutting planes** — there are no
  natural knapsack, clique, or flow substructures to exploit.
- **Highly symmetric** coefficient patterns amplify the search tree.

## Techniques that help

- **Basis reduction reformulation.** Aardal, Hurkens, and Lenstra
  (2000) showed that applying the LLL algorithm to the constraint
  matrix yields an equivalent but much better-conditioned formulation
  in which standard branch-and-bound solves the instances orders of
  magnitude faster. This is the landmark result people cite when they
  say "markshare is hard in the original formulation but easy after
  LLL".
- **Problem-structure–aware basis reduction.** Louveaux and Wolsey
  (2002) extended the Aardal et al. approach to a broader class of
  market-share–like equality-constrained IPs and solved larger
  instances that resisted pure LLL.

## References

- Cornuéjols, G., & Dawande, M. (1998). *A class of hard small
  0–1 programs.* In: Integer Programming and Combinatorial
  Optimization (IPCO), LNCS 1412, pp. 284–293. Springer.
- Aardal, K., Hurkens, C. A. J., & Lenstra, A. K. (2000). *Solving
  a system of linear Diophantine equations with lower and upper
  bounds on the variables.* Mathematics of Operations Research
  25(3), 427–442.
- Louveaux, Q., & Wolsey, L. A. (2002). *Combining problem structure
  with basis reduction to solve a class of hard integer programs.*
  Mathematics of Operations Research 27(3), 470–484.
  [DOI](https://doi.org/10.1287/moor.27.3.470.315)
