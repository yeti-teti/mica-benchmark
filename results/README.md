# Benchmark results

[scores.csv](scores.csv) records the six metrics for 22XP and 32MC. TM-scores use the deposited reference length for normalization. Paths in the `model_file` column are relative to this directory. Each completed model has a US-align summary alongside it.

ModelAngelo, EModelX(+AF), and EMProt come from the second run. CryoAtom and refined MICA on 22XP come from the initial run. MICA produced an unrefined 32MC model before Phenix rejected the refinement parameters. The 32MC score fields for MICA are blank. The successful 22XP refinement used [this parameter file](22XP/MICA/phenix-2.2.1-fixed.eff).

CryoAtom's 22XP elapsed time includes an ESM checkpoint download. MICA's 22XP refinement was run separately, so its end-to-end elapsed time is blank.

MICA and EMProt used AlphaFold Server predictions as inputs. The inputs and applicable derivatives are subject to the [AlphaFold Server Output Terms of Use](alphafold-server-terms.md).
