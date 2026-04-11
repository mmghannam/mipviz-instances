# rmatr

The `rmatr*` MIPLIB instances come from Goldengorin and Krushinsky
(2011)[^1], whose paper evaluates the complexity of benchmark
instances for the **p-median problem**. The p-median problem is a
classic facility-location model that chooses `p` facilities from a
set of candidate locations so as to minimize the total assignment
cost from demand points to their closest chosen facility.

The same authors and their collaborators later explored a
**pseudo-Boolean formulation** of p-median and applied it to
manufacturing **cell formation**[^2][^3]; this connection is visible
directly from the abstracts of the follow-up papers, which describe
the p-median approach as the basis for large-size cell formation
algorithms.

## Further reading

Papers from the OpenAlex citation graph that cite the origin and stay
within p-median or closely related facility-location / cell-formation
territory:

- **Flexible PMP approach for large-size cell formation** —
  Goldengorin, Krushinsky, Slomp (2012)[^2]. The authors frame cell
  formation as a p-median instance.
- **A computational study of the pseudo-Boolean approach to the
  p-median problem applied to cell formation** — Goldengorin &
  Krushinsky (2011)[^3].
- **Hybrid metaheuristics for the Reliability p-Median Problem** —
  Alcaraz, Landete, Monge (2012)[^4]. Robust-flavour variant of
  p-median.
- **Discrete particle swarm optimization for p-median** — Şevkli,
  Mamedsaidov, Camci (2012)[^5].
- **A branch-and-price approach for the continuous multifacility
  monotone ordered median problem** — Blanco, Gázquez, Ponce et al.
  (2022)[^6]. Related ordered-median generalisation.

## References

[^1]: Goldengorin, B., & Krushinsky, D. (2011). *Complexity
      evaluation of benchmark instances for the p-median problem.*
      Mathematical and Computer Modelling 53(9–10), 1719–1736.
      [DOI](https://doi.org/10.1016/j.mcm.2010.12.047)
[^2]: Goldengorin, B., Krushinsky, D., & Slomp, J. (2012).
      *Flexible PMP Approach for Large-Size Cell Formation.*
      Operations Research.
      [DOI](https://doi.org/10.1287/opre.1120.1108)
[^3]: Goldengorin, B., & Krushinsky, D. (2011). *A Computational
      Study of the Pseudo-Boolean Approach to the p-Median Problem
      Applied to Cell Formation.* LNCS.
      [DOI](https://doi.org/10.1007/978-3-642-21527-8_55)
[^4]: Alcaraz, J., Landete, M., & Monge, J. F. (2012). *Design and
      analysis of hybrid metaheuristics for the Reliability p-Median
      Problem.* European Journal of Operational Research.
      [DOI](https://doi.org/10.1016/j.ejor.2012.04.016)
[^5]: Şevkli, M., Mamedsaidov, R., & Camci, F. (2012). *A novel
      discrete particle swarm optimization for p-median problem.*
      Journal of King Saud University — Engineering Sciences.
      [DOI](https://doi.org/10.1016/j.jksues.2012.09.002)
[^6]: Blanco, V., Gázquez, R., Ponce, D., et al. (2022).
      *A branch-and-price approach for the continuous multifacility
      monotone ordered median problem.* European Journal of
      Operational Research.
      [DOI](https://doi.org/10.1016/j.ejor.2022.07.020)
