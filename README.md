# MIP/LP Instance Collection

This repository hosts a clean, versioned collection of Mixed-Integer and Linear Programming instances. It is primarily used as the remote instance bank for the [**mipviz**](https://mmghannam.github.io/mipviz/) web application, but can be used for any optimization tool.

The instances are stored in a flat directory under `/instances` in `.mps.gz` format and tracked with [Git LFS](https://git-lfs.github.com/).

## Collections

Collections are defined by `.txt` files in the `/collections` directory (one instance name per line), which allows for flexible, overlapping sets.

| Collection | # Instances | Description |
|---|---|---|
| `miplib2017_collection` | 1065 | Full [MIPLIB 2017](https://miplib.zib.de/) collection |
| `miplib2017_benchmark` | 240 | MIPLIB 2017 benchmark subset |
| `miplib2010` | 87 | [MIPLIB 2010](https://miplib.zib.de/tag_benchmark.html) instances |
| `miplib2003` | 38 | [MIPLIB 2003](https://miplib.zib.de/) instances |
| `mipdev-solvable` | 387 | Solvable instances from MIPDEV |
| `mipdev2-solvable` | 349 | Solvable instances from MIPDEV2 |
| `mipdev3-solvable` | 328 | Solvable instances from MIPDEV3 |
| `mipdev12merged-solvable` | 522 | Solvable instances from MIPDEV 1+2 merged |
| `coral` | 347 | Instances from the [CORAL](http://coral.ise.lehigh.edu/) collection |
| `mipcomp22` | 19 | Instances from the 2022 MIP computational competition |

## Metadata

- **`instance-stats.json`** — Per-instance statistics (number of variables, constraints, nonzeros, variable types).
- **`miplib-metadata.json`** — Extended metadata from MIPLIB (objective values, tags, etc.).

## Usage

You can access the raw instance files directly via `raw.githubusercontent.com`. For example:

```
https://raw.githubusercontent.com/mmghannam/mipviz-instances/main/instances/10teams.mps.gz
```

## License

The instances are provided under the terms specified by their original authors. When using instances from a specific library (like MIPLIB), please be sure to cite the original source. See the `LICENSE` file for more details.
