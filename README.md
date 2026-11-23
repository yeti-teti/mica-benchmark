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

The final models are in [results/](results/). [scores.csv](results/scores.csv) records the six metrics for 22XP and 32MC. TM-scores use the deposited reference length for normalization. Paths in the `model_file` column are relative to `results/`. Each completed model has a US-align summary alongside it.

ModelAngelo, EModelX(+AF), and EMProt come from the second run. CryoAtom and refined MICA on 22XP come from the initial run. I used four CPU workers for MICA docking to avoid Out of memory errors. MICA produced an unrefined 32MC model before Phenix rejected the refinement parameters. The 32MC score fields for MICA are blank. The successful 22XP refinement used [this parameter file](results/22XP/MICA/phenix-2.2.1-fixed.eff).

CryoAtom's 22XP elapsed time includes an ESM checkpoint download. MICA's 22XP refinement was run separately, so its end-to-end elapsed time is blank.

MICA and EMProt used AlphaFold Server predictions as inputs.
