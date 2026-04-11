# chromaticindex

The `chromaticindex*` MIPLIB instances encode **edge-colouring** problems
— MIPs for computing the **chromatic index** of a graph — and were
introduced by Le Bodic and Nemhauser (2015) in *How important are
branching decisions: Fooling MIP solvers*[^1]. The paper's title is
literal: the instances are constructed so that the optimal solution is
trivially available at the root, yet every MIP solver tested in 2015
needs an arbitrarily growing tree to prove optimality.

The paper appeared in Operations Research Letters[^1] and is also
available as an author preprint on optimization-online[^2].

## The `I_k` construction

Starting from the **Petersen graph** (10 vertices, max degree Δ=3,
chromatic index χ′=4), Le Bodic and Nemhauser define two modified
variants:

- **P1** — obtained by subdividing one edge of the Petersen graph with
  a new vertex; still has χ′=4.
- **P2** — obtained by subdividing two non-adjacent edges; χ′=3.

Define `G_k` as the disjoint union of **one P1 and k−1 P2 copies**,
plus k−1 bridging edges (each added between degree-2 vertices so the
whole graph becomes connected). Because `G_k` contains P1 as a
subgraph and Δ=3, its chromatic index stays pinned at 4. Each
`G_k` has **12k vertices and 18k−1 edges** — which is why every
chromaticindex instance in MIPLIB has a vertex count that is exactly
12 × (first number in its name), e.g. `chromaticindex32-8` has
32 × 12 = 384 vertices.

The MIP model is a simple edge-colouring formulation (Section 2.3 of
the paper): binary variables `xᵉⁱ` ("edge e has colour i") and `cⁱ`
("colour i is used"), minimise Σ cⁱ subject to edge-assignment and
vertex-adjacency constraints. Instance `Iₖ` has approximately **72k
variables, 64k constraints, and 264k nonzeros**[^1].

The trailing number in the instance name (the **8** in
`chromaticindex32-8`) is the **row-permutation index**: the authors
generate ten equivalent copies per size `k` via random row
permutations to smooth out performance variability[^1]. So the five
instances in this MIPLIB group are each a single permutation drawn
from a larger 10-per-size cohort.

## Why MIP solvers struggle

The striking feature of these instances is that *finding* the optimum
is trivial (a 4-edge-colouring of a max-degree-3 graph can be produced
in linear time), while *proving* the optimum is the hard part. The
paper pins down why:

- **Root LP = 3 everywhere.** The continuous relaxation has objective
  value 3 at the root and — crucially — at every node the solver
  descends into. Since the objective is integral and the optimum is
  4, the absolute gap is 1 at the root and must be closed purely
  through dual bound improvement[^1].
- **Theorem 1**: For every `k ≥ 1`, there exists a **fixed-size**
  branch-and-bound tree that proves optimality. The proof lifts a
  tree for `I_1` to `I_k` and relies on the LP bound at each leaf
  of `I_k` being at least as strong as the bound at the corresponding
  leaf of `I_1`[^1]. So the tree need not grow with `k` — but no
  solver tested finds it.
- **Pseudocost branching is blind.** SCIP's reliability pseudocost
  rule relies on pseudocosts computed from LP bound changes under
  branching. On `I_k`, any branch that fails to find a feasible
  improvement still leaves the child LP at value 3, so no LP bound
  change is observed, so pseudocosts are *uniformly zero* across
  all variables. The ranking information pseudocosts are supposed
  to provide is therefore absent[^1].
- **Conflict analysis bootstraps slowly.** The tie-breaking fallback
  is SCIP's conflict analysis, which is un-initialised at the root.
  Early branching decisions are effectively random, which occasionally
  generates useful conflicts and "snowballs" into concentrated
  branching on good variables — or the solver runs out of time first.
  This explains the huge variance across row permutations observed
  in Table 1 of the paper[^1].

## What the paper measured in 2015

Section 3.2 benchmarks CPLEX 12.6.0.0, GUROBI 5.6.0, and SCIP 3.1.0
(10 permutations per size, 5-hour time limit). All three solvers
hit an exponential wall as `k` grows:

| `k`   | CPLEX solved | GUROBI solved | SCIP solved |
|-------|-------------:|--------------:|------------:|
| 16    | 9/10         | 10/10         | 10/10       |
| 128   | 8/10         | 7/10          | 10/10       |
| 512   | 2/10         | 7/10          | 6/10        |
| 1024  | 2/10         | 3/10          | 0/10        |

Section 3.4 tries parameter tuning and finds that **probing**
(`mip strategy probe = 3`) and **dual-bound emphasis** (`emphasis mip
= 3`) help CPLEX, but none of the tuning knobs produce tree sizes
that stay bounded as `k` grows — the exponential blow-up just gets
a better prefactor.

The paper is explicit that its deeper branching-rule analysis applies
to **SCIP only** — the authors cannot read CPLEX or GUROBI internals,
so the black-box empirical numbers are all they can say there[^1].

## The paper's call, and what has happened since

The conclusion of Le Bodic & Nemhauser (2015) flags the likely fix:

> *"New techniques (e.g., exploiting structure or symmetry, for
> instance during preprocessing, branching or cut generation) may be
> needed for MIP solvers to efficiently solve these instances."*[^1]

Anecdotally, modern solvers with aggressive presolve (e.g. COPT)
appear to handle the `chromaticindex` family in roughly constant time
— essentially at the root, before real branch-and-bound begins. We
don't have a citable write-up for the specific technique being used
in any particular solver, but the observed behaviour lines up exactly
with what the 2015 paper calls for. Treat that paragraph as an open
observation, not a result.

Two more recent papers continue the line of investigation into the
connection between branching, tree size, and performance:

- **Estimating the Size of Branch-and-Bound Trees** — Hendel, Anderson,
  Le Bodic et al. (2022)[^3]. From the same first author; proves that
  B&B tree size cannot even be approximated within a factor of 2 for
  general binary programs.
- **Decomposition Branching for Mixed Integer Programming** — Yıldız,
  Boland, Savelsbergh (2022)[^4]. A branching-strategy paper that
  cites the origin.

## References

[^1]: Le Bodic, P., & Nemhauser, G. L. (2015). *How important are
      branching decisions: Fooling MIP solvers.* Operations Research
      Letters 43(3), 273–278.
      [DOI](https://doi.org/10.1016/j.orl.2015.03.003)
[^2]: Le Bodic, P., & Nemhauser, G. L. (2014). Author preprint of the
      above, freely available on optimization-online:
      <https://optimization-online.org/2014/04/4324/>
      ([PDF](https://optimization-online.org/wp-content/uploads/2014/04/4324.pdf))
[^3]: Hendel, G., Anderson, D., Le Bodic, P., et al. (2022).
      *Estimating the Size of Branch-and-Bound Trees.* INFORMS
      Journal on Computing.
      [DOI](https://doi.org/10.1287/ijoc.2021.1103)
[^4]: Yıldız, B., Boland, N., & Savelsbergh, M. (2022).
      *Decomposition Branching for Mixed Integer Programming.*
      Operations Research.
      [DOI](https://doi.org/10.1287/opre.2021.2210)
