# chromaticindex32-8

The instance encodes an edge-colouring problem on a graph with **384
vertices and 575 edges** (maximum degree 3). The optimal value is
χ′ = 4 — i.e. four colour classes are enough to edge-colour this
graph — recovered from MIPLIB's best-known solution file.

Drag the graph to pan, scroll to zoom, and hover an edge to see which
colour class it belongs to.

```mipviz-graph
graph.json
```

## Notes on the layout

The graph is built from 32 small motifs (each ≈ 12 vertices, visible
as the dense clusters above) connected by a sparse backbone. The `32`
in the instance name corresponds to this replication count.

## Source and reproducibility

The graph and its colouring come from MIPLIB's best-known solution
file
([`chromaticindex32-8.sol.gz`](https://miplib.zib.de/downloads/solutions/chromaticindex32-8/1/chromaticindex32-8.sol.gz)).
Variable names in that file follow `x<i>_<j>_<c> 1` ("edge (i,j) has
colour c"), so the graph and its colouring are reconstructible without
touching the MPS file. The conversion to `graph.json` is done by
[`scripts/render_chromaticindex.py`](https://github.com/mmghannam/mipviz/blob/main/scripts/render_chromaticindex.py)
in the mipviz repo; the interactive view is powered by Sigma.js.

See the group note on `chromaticindex` for the origin paper and
further reading.
