# bppc

The `bppc*` instances in MIPLIB encode **two-dimensional strip packing**
problems from Côté, Dell'Amico, and Iori (2014)[^1]. The instances
were introduced by the same paper that proposes a combinatorial-Benders
cut-generation algorithm for strip packing.

From the origin paper abstract:

> We study the strip packing problem, in which a set of two-dimensional
> rectangular items has to be packed in a rectangular strip of fixed
> width and infinite height, with the aim of minimizing the height
> used.

## Further reading

Papers from the OpenAlex citation graph that cite the origin and work
in closely related areas (cutting & packing, Benders-style
decomposition):

- A survey of **exact solution techniques for 2D cutting and packing**
  by Iori, Lima, Martello, Miyazawa & Monaci (2020)[^2].
- **Logic-based Benders' decomposition** applied to orthogonal stock
  cutting, by Delorme, Iori & Martello (2016)[^3].
- The **meet-in-the-middle principle** for cutting and packing —
  a later exact framework from Côté & Iori (2018)[^4].
- **Pseudo-polynomial formulations** for bin packing and cutting stock,
  by Delorme & Iori (2019)[^5].
- A general **Benders decomposition literature review** by Rahmaniani,
  Crainic, Gendreau & Rei (2017)[^6].

## References

[^1]: Côté, J.-F., Dell'Amico, M., & Iori, M. (2014).
      *Combinatorial Benders' Cuts for the Strip Packing Problem.*
      Operations Research 62(3), 643–661.
      [DOI](https://doi.org/10.1287/opre.2013.1248)
[^2]: Iori, M., de Lima, V. L., Martello, S., Miyazawa, F. K., &
      Monaci, M. (2020). *Exact solution techniques for two-dimensional
      cutting and packing.* European Journal of Operational Research.
      [DOI](https://doi.org/10.1016/j.ejor.2020.06.050)
[^3]: Delorme, M., Iori, M., & Martello, S. (2016).
      *Logic based Benders' decomposition for orthogonal stock cutting
      problems.* Computers & Operations Research.
      [DOI](https://doi.org/10.1016/j.cor.2016.09.009)
[^4]: Côté, J.-F., & Iori, M. (2018). *The Meet-in-the-Middle
      Principle for Cutting and Packing Problems.* INFORMS Journal
      on Computing.
      [DOI](https://doi.org/10.1287/ijoc.2018.0806)
[^5]: Delorme, M., & Iori, M. (2019). *Enhanced Pseudo-polynomial
      Formulations for Bin Packing and Cutting Stock Problems.*
      INFORMS Journal on Computing.
      [DOI](https://doi.org/10.1287/ijoc.2018.0880)
[^6]: Rahmaniani, R., Crainic, T. G., Gendreau, M., & Rei, W. (2017).
      *The Benders decomposition algorithm: A literature review.*
      European Journal of Operational Research.
      [DOI](https://doi.org/10.1016/j.ejor.2016.12.005)
