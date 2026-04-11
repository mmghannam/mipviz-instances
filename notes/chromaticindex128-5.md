# chromaticindex128-5

The instance encodes an edge-colouring problem on a graph with
**1,536 vertices and 2,303 edges** (maximum degree 3). The optimal
value is χ′ = 4 — i.e. 4 colour classes are enough to edge-colour
this graph — recovered from MIPLIB's best-known solution file.

Drag the graph to pan and scroll to zoom.

```mipviz-graph
graph.json
```

## Source and reproducibility

The graph and its colouring come from MIPLIB's best-known solution
file
([`chromaticindex128-5.sol.gz`](https://miplib.zib.de/downloads/solutions/chromaticindex128-5/1/chromaticindex128-5.sol.gz)).
Variable names in that file follow `x<i>_<j>_<c> 1` ("edge (i,j) has
colour c"), so the graph and its colouring are reconstructible without
touching the MPS file. The conversion to `graph.json` is done by
[`scripts/render_chromaticindex.py`](https://github.com/mmghannam/mipviz/blob/main/scripts/render_chromaticindex.py)
in the mipviz repo; the interactive view is powered by Sigma.js.

See the group note on `chromaticindex` for the origin paper and
further reading.
