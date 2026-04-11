# maritime

The `maritime` MIPLIB instances come from **MIRPLib**, the maritime
inventory routing problem library assembled by Papageorgiou,
Nemhauser, Sokol, Cheon, and Keha (2014)[^1]. MIRPLib was introduced
together with a core MIP model and benchmark results for maritime
inventory routing. A companion paper from a subset of the same authors
studies approximate dynamic programming for long-horizon variants of
the problem[^2]; that paper describes the setting directly:

> We study a deterministic maritime inventory routing problem with a
> long planning horizon. For instances with many ports and many
> vessels, mixed-integer linear programming (MIP) solvers often
> require hours to produce good solutions even when the planning
> horizon is 90 or 120 periods.[^2]

## Further reading

Papers from the OpenAlex citation graph that cite MIRPLib and stay
within the maritime/inventory-routing area:

- **Robust optimization** applied to a single-product maritime
  inventory routing problem by Agra, Christiansen, Hvattum et al.
  (2018)[^3]. The abstract describes a heterogeneous fleet and
  multiple production/consumption ports with limited storage
  capacity.
- **Modelling uncertainty** in maritime inventory routing — a
  comparison by Rodrigues, Agra, Christiansen et al. (2019)[^4].
- A **decomposition algorithm for LNG inventory routing** by
  Andersson, Christiansen, Desaulniers (2015)[^5]; the abstract
  describes the LNG-IRP setting with liquefaction plants, a
  heterogeneous fleet of LNG ships, and regasification inventories.
- **Approximate dynamic programming** for long-horizon MIRPs —
  Papageorgiou, Cheon, Nemhauser, Sokol (2014)[^2] (the companion
  paper to MIRPLib).

## References

[^1]: Papageorgiou, D. J., Nemhauser, G. L., Sokol, J., Cheon, M.-S.,
      & Keha, A. B. (2014). *MIRPLib – A library of maritime inventory
      routing problem instances: Survey, core model, and benchmark
      results.* European Journal of Operational Research 235(2),
      350–366.
      [DOI](https://doi.org/10.1016/j.ejor.2013.12.013)
[^2]: Papageorgiou, D. J., Cheon, M.-S., Nemhauser, G. L., & Sokol, J.
      (2014). *Approximate dynamic programming for a class of
      long-horizon maritime inventory routing problems.*
      Transportation Science 49(4), 870–885.
      [DOI](https://doi.org/10.1287/trsc.2014.0542)
[^3]: Agra, A., Christiansen, M., Hvattum, L. M., & Rodrigues, F.
      (2018). *Robust Optimization for a Maritime Inventory Routing
      Problem.* Transportation Science.
      [DOI](https://doi.org/10.1287/trsc.2017.0814)
[^4]: Rodrigues, F., Agra, A., Christiansen, M., et al. (2019).
      *Comparing techniques for modelling uncertainty in a maritime
      inventory routing problem.* European Journal of Operational
      Research.
      [DOI](https://doi.org/10.1016/j.ejor.2019.03.015)
[^5]: Andersson, H., Christiansen, M., & Desaulniers, G. (2015).
      *A new decomposition algorithm for a liquefied natural gas
      inventory routing problem.* International Journal of Production
      Research.
      [DOI](https://doi.org/10.1080/00207543.2015.1037024)
