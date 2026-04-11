# chromaticindex

The `chromaticindex*` MIPLIB instances encode **edge-coloring**
problems — specifically, MIPs for computing the **chromatic index**
of a graph — and were introduced by Le Bodic and Nemhauser (2015)
in *How important are branching decisions: Fooling MIP solvers*[^1].
The paper's title is literal: the instances are constructed to
illustrate that seemingly small changes in branching decisions can
cause a MIP solver's branch-and-bound tree to explode.

The MIPLIB bibtex for these instances lists the paper's keywords
directly as *Mixed integer programming solvers*, *Branch and bound*,
*Tree size*, *Edge coloring*, and *Chromatic index*, which is the
full story of what the instances are about and why they exist.

## Further reading

The OpenAlex citation graph for the origin paper is small (6 citers
as of this writing) but includes two direct follow-ups on branching
and tree-size behaviour in MIP:

- **Estimating the Size of Branch-and-Bound Trees** — Hendel,
  Anderson, Le Bodic et al. (2022)[^2]. From the abstract: "We first
  prove that the size of the B&B tree cannot be approximated within
  a factor of 2 for general binary programs…". A direct thematic
  follow-up from one of the original authors.
- **Decomposition Branching for Mixed Integer Programming** —
  Yıldız, Boland, Savelsbergh (2022)[^3]. A branching-strategy paper
  that cites the origin.

## References

[^1]: Le Bodic, P., & Nemhauser, G. L. (2015). *How important are
      branching decisions: Fooling MIP solvers.* Operations Research
      Letters 43(3), 273–278.
      [DOI](https://doi.org/10.1016/j.orl.2015.03.003)
[^2]: Hendel, G., Anderson, D., Le Bodic, P., et al. (2022).
      *Estimating the Size of Branch-and-Bound Trees.* INFORMS
      Journal on Computing.
      [DOI](https://doi.org/10.1287/ijoc.2021.1103)
[^3]: Yıldız, B., Boland, N., & Savelsbergh, M. (2022).
      *Decomposition Branching for Mixed Integer Programming.*
      Operations Research.
      [DOI](https://doi.org/10.1287/opre.2021.2210)
