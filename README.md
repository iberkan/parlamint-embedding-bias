[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/iberkan/parlamint-embedding-bias/blob/main/thesis_findings.ipynb)
[![Code DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21001580.svg)](https://doi.org/10.5281/zenodo.21001580)
[![Data DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21000496.svg)](https://doi.org/10.5281/zenodo.21000496)

# Political orientation in multilingual embedding spaces

Analysis code for the master's thesis *Political Orientation in Multilingual Embedding
Spaces: A Multi-Country Audit of Parliamentary Speech* (KU Leuven, Digital Humanities).
The study audits five multilingual sentence-embedding models for left–right political
asymmetries across twelve European parliaments drawn from ParlaMint 5.0.

## What is here

- `thesis_findings.ipynb` — the full analysis pipeline (retrieval asymmetry,
  ideology/role classification, gender confound, WEAT and its confound battery,
  regression, and the paper-version figures).
- `scripts/` — corpus sampling and embedding-generation scripts *(add your own)*.
- `requirements.txt` — Python dependencies.

## Data

Two tiers, kept separate on purpose:

1. **Source corpus — ParlaMint 5.0.** Not redistributed here. It is openly available
   from CLARIN.SI; see Erjavec et al. (2024) and the ParlaMint repository.
2. **Derived data — pre-computed embeddings + labels.** Archived on Zenodo:
   **DOI: 10.5281/zenodo.21000496**. It is published as a single archive, `embeddings_metadata.zip`, holding the five
   `embeddings_<model>.npy` arrays (72,720 speeches each) and `metadata.csv`
   (per-speech country, ideology, role, gender, topic labels; no raw text). The
   notebook downloads and unpacks it automatically; every result is reproduced
   from these files alone.

## Reproduce

1. Open the notebook in Colab with the badge above.
2. In the **Reproduction setup** cell, set `ZENODO_RECORD` to your Zenodo record id
   (the number in the DOI / URL). Leave `DATA_SOURCE = 'zenodo'`.
3. Run all cells. A GPU is not required for the analysis; the embeddings are already
   computed. Results and figures are written to a local `results/` folder.

To re-compute the embeddings from scratch you also need the raw ParlaMint text
(reconstructable from the IDs in `metadata.csv`) and the scripts in `scripts/`.

## Citation

If you use this work, please cite the thesis, the code archive
(DOI 10.5281/zenodo.21001580) and the dataset (DOI 10.5281/zenodo.21000496), and
cite ParlaMint 5.0 (Erjavec et al., 2024) as the source corpus.

## License

Code: MIT. Derived data on Zenodo: CC BY 4.0 (matching ParlaMint's licence).
