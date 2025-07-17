# LA-NMDi-Immune
Single-cell transcriptome and T-cell-receptor analysis of a **mismatch-repair-deficient lung adenocarcinoma** model treated with **nonsense-mediated-decay inhibition (NMDi)** and/or **anti-PD-1** immunotherapy.  
This code reproduces the immune-profiling figures and statistics from:

> **Zadra I. *et al.* (2025)**  
> *Inhibition of nonsense-mediated decay elicits potent anti-tumour immune response in vivo*  

---

## Repository layout
| Notebook | Purpose |
| -------- | ------- |
| **0_Preprocessing.ipynb** | Read 10x **Cell Ranger 8.0.1** outputs, per-sample QC, filtering (<5 % MT, >10 k UMIs, >200 genes), doublet removal (DoubletDetection v4.2), save raw & filtered `h5ad`. |
| **1_Annotation.ipynb** | Batch integration with **scVI**, clustering (Leiden 0.15), marker-based cell-type labelling, differential expression. |
| **2_Preprocessing_TCR.ipynb** | Attach paired VDJ contigs (Cell Ranger `vdj`) with **Scirpy**; QC orphan chains; merge clonotypes. |
| **3_FIGURES.ipynb** | Generate manuscript figures (UMAPs, composition heat-maps, clonotype expansion, signature scores). |
