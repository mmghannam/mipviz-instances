# MIP/LP Instance Collection

This repository hosts a clean, versioned collection of Mixed-Integer and Linear Programming instances. It is primarily used as the remote instance bank for the [**mipviz**](https://mmghannam.github.io/mipviz/) web application, but can be used for any optimization tool.

The instances are stored in a flat directory under `/instances` in their original format (e.g., `.mps.gz`).

## Collections

Collections are defined by `.txt` files in the `/collections` directory, which allows for flexible, overlapping sets.

- **NEOS**: A broad collection of instances submitted to the [NEOS Server](https://www.neos-server.org/neos/).
- **Other**: Miscellaneous instances from various other sources.

## Usage

You can access the raw instance files directly via `raw.githubusercontent.com`. For example:

`https://raw.githubusercontent.com/mmghannam/mipviz-instances/main/instances/10teams.mps.gz`

## License

The instances are provided under the terms specified by their original authors. When using instances from a specific library (like MIPLIB), please be sure to cite the original source. See the `LICENSE` file for more details.
