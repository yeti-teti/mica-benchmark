# Benchmark

Repo to benchmark five methods for building protein structures from cryo-EM maps.

## Run the benchmarks

You can run each notebook individually. Open it from the repo folder and run the cells in order. Each notebook sets up its own environment.

- [MICA](MICA.ipynb)
- [ModelAngelo](ModelAngelo.ipynb)
- [EModelX](EModelX.ipynb)
- [CryoAtom](CryoAtom.ipynb)
- [EMProt](EMProt.ipynb)

Use x86-64 Linux with CUDA to run all five. Download the Phenix installer and put it in the same folder as `MICA.ipynb`. The scoring cells also use Phenix.

## Data

For this benchmark, I used 22XP and 32MC. The maps, FASTA files, reference structures, and AF2 and AF3 predictions are in [data/targets/](data/targets/).

I used the notebooks in [af/](af/) to get the AF2 predictions. I used [AlphaFold Server](https://alphafoldserver.com/) to get the AF3 predictions.

Download the dataset from [Zenodo](https://doi.org/10.5281/zenodo.24477761).

## Results

The final models and run notes are in [results/](results/). The scores for both targets are in [scores.csv](results/scores.csv).
