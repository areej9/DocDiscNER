# DocDiscNER: Enhanced Document-Level Discontinuous NER via Coordination Ellipses Resolution and Self-Consistency Decoding

**Authors:**  
Areej Alhassan, Viktor Schlegel, Rina Carines Cabral, Riza Batista-Navarro, Caren Han, Josiah Poon, Goran Nenadic  

Published at **ECAI 2025**

---

##  Overview

This repository contains the implementation of **DocDiscNER**, a document-level discontinuous Named Entity Recognition (DiscNER) framework that enhances model performance via:

- **Coordination Ellipses Resolution (CER)**
- **Document Chunking**
- **Self-Consistency Decoding (SC)**

It includes code notebooks, the CER dataset, and links to the released CER checkpoint.  
Please cite our ECAI 2025 paper if you use this work in your research.

---

## Resources

- **CER Checkpoint (Hugging Face):**  
   [https://huggingface.co/areej9/CER_Mistral7B](https://huggingface.co/areej9/CER_Mistral7B)

- **CER Dataset:**  
   [View CER Dataset](https://github.com/areej9/DocDiscNER/blob/main/CER%20Dataset/CERDataset.csv)

---

## Notebooks & Contents

| Notebook / Folder | Description |
|------------------|-------------|
| `1. DocDiscNER_Preprocessing.ipynb` | Preprocesses raw datasets (ShARe-13, ShARe-14, and CADEC). CADEC is converted into a document-level format with prefixed spans. |
| `2. DocDiscNER_Chunker.ipynb` | Implements recursive and semantic chunking for ShARe datasets. Adds "disorder" prefixes and optionally removes date/time info. |
| `3. DocDiscNER_CER.ipynb` | Fine-tunes **BioMistral-7B** on the CER dataset. The trained model is used for resolving coordination ellipses in text during preprocessing. |
| `4. DocDiscNER_NER.ipynb` | Main model training and inference code for Discontinuous NER. Use this after preprocessing. |
| `5. DocDiscNER_SC.ipynb` | Performs **Self-Consistency Decoding** by filtering span predictions via majority agreement across beam search outputs. |
| `6. DocDiscNER_Eval.ipynb` | Document-level evaluation. For sentence-level benchmarking, refer to Dai et al.'s evaluation (see next notebook). |
| `7. ConvertOurs2Dai's.ipynb` | Converts document-level predictions into sentence-level inline format compatible with [Dai et al., 2020] evaluation scripts. Separate versions for ShARe and CADEC. |
| `8. DocDiscNER_Analysis.ipynb` | Analyses F1 scores across span/interval lengths and discontinuous structures. Based on Wang et al., 2021. |
| `9. TOE_replication_setup/` | Reproduction setup for TOE (Liu et al., 2023). Includes model configurations and hyperparameters. |

---

## Citation

If you use DocDiscNER in your research, please cite our paper:

```bibtex
@inproceedings{alhassan2025docdiscner,
  title     = {DocDiscNER: Enhanced Document-Level Discontinuous NER via Coordination Ellipses Resolution and Self-Consistency Decoding},
  author    = {Areej Alhassan and Viktor Schlegel and Rina Carines Cabral and Riza Batista-Navarro and Caren Han and Josiah Poon and Goran Nenadic},
  booktitle = {Proceedings of the European Conference on Artificial Intelligence (ECAI)},
  year      = {2025}
}
