# chromaticindex32-8

The instance encodes an edge-colouring problem on a graph with **384
vertices and 575 edges** (maximum degree 3). The optimal value is
χ′ = 4 — i.e. four colour classes are enough to edge-colour this
graph — recovered from MIPLIB's best-known solution file.

## Graph structure

![Graph structure](images/graph.png)

The graph is built from 32 small motifs (each ≈ 12 vertices, visible
as the dense clusters in the layout) connected by a sparse backbone.
The `32` in the instance name corresponds to this replication count.

## Optimal 4-colouring

![Optimal edge 4-colouring (χ′ = 4)](images/solution.png)

The four colour classes come from the solution file hosted on MIPLIB
([`chromaticindex32-8.sol.gz`](https://miplib.zib.de/downloads/solutions/chromaticindex32-8/1/chromaticindex32-8.sol.gz)).
No adjacent edges share a colour.

## Source and reproducibility

Both images were produced by
[`scripts/render_chromaticindex.py`](https://github.com/mmghannam/mipviz/blob/main/scripts/render_chromaticindex.py)
in the mipviz repo, which parses the MIPLIB solution file (variable
names follow the pattern `x<i>_<j>_<c> 1` for "edge (i,j) has colour
c") and draws the graph with NetworkX + matplotlib. See the group note
on `chromaticindex` for the origin paper and further reading.
