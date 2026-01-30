> **“Somewhere in the semantics of natural language and the ambiguity of our understanding in reality leaves truth as one of the great mysteries”**

# Introduction

**Hi, I’m [@lhallee](https://github.com/lhallee)!**  

My name is Logan Hallee, a scientist working on computational protein modeling through the lens of machine learning. Most notably, I am the the Chief Scientific Officer and Founder of Synthyra, a Public Benefit LLC which functions as a research org and CRO for protein science. I am also a PhD Candidate in Bioinformatics at the University of Delaware in the ([Gleghorn Lab](https://www.gleghornlab.com/)), where my research is focused on (you guessed it) protein modeling with transformer neural networks. On the side I run a fun blog called [Minds and Molecules](https://medium.com/minds-and-molecules) which touches on philosophical ideas I find facinating.

I'm deeply motivated to make progress towards safe computational systems that can help us study and grasp the intricases of the universe at every level of abstraction. However, I am mostly motivated towards the prospects of fidelity over the protein universe, projects that assist in turning biochemistry into a programming language, as true biochemical mastery will unlock organic carbon capture, better crops, efficient circular economies, and untold progress in the medical field.

### You can find my CV [here](https://docs.google.com/document/d/1q4mQotGm7MyU-TLmf_x17bRxalCy_Fcz/edit?usp=sharing&ouid=110410923518282620159&rtpof=true&sd=true)

# Research Highlights

## Protein-Protein Interaction Prediction (PPI)
### Synteract
- I've worked on a series of models named Synteract, which have made various contributions to the field of PPI.
- Synteract-1 was the first large language model approach for PPI prediction [**SYNTERACT**](https://huggingface.co/GleghornLab/SYNTERACT).
  - Its preprint still ranks in the [**top 3% of research outputs**](https://www.biorxiv.org/content/10.1101/2023.06.07.544109v1.article-metrics) by Altmetric.
  - We made progress showcasing how different negative sampling strategies can negatively effect performance (accidental localizers).
- Synteract-2 was a jointly optimized system that predicted PPI, protein-protein binding affinity, and binding site locaations and was Synthyra's first product. At the time of release it was the best binding affinity predictor via the Affinity v5.5 and Haddock benchmarks.
<img width="5400" height="3600" alt="pkd_correlation" src="https://github.com/user-attachments/assets/ab5dff22-835c-4cc1-be07-85135a71ef0d" />

- I addressed key confounders in PPI data compliation, most recently the [accidental taxonomist](https://www.biorxiv.org/content/10.1101/2025.10.07.681002v1) phenomena when training from pLM or adjacent embeddings.
  - In review at BMC Bioinformatics
- Synteract-3 was an internal model that had a similar workflow to Synteract-2 but with exceedingly high throughput, allowing for full interactome predictions.
- Synteract-4 is Synthyra's current premier product, offering a 10% increase in performance on standardized gold-standard benchmarks compared to the entire field. 
<img width="7200" height="4800" alt="bernett" src="https://github.com/user-attachments/assets/8946cfa9-faf3-43f3-ac0d-b77bed025e5b" />

### Protein binder design
We leveraged the signal of Synteract-2 binding affinity predictions with our generative model DSM
- DSM is the first protein language model (pLM) trained on the LLaDa masked diffusion process, enabling easy extension to pretrained pLMs to turn them into generative models.
<img width="856" height="1692" alt="dsm_architecture" src="https://github.com/user-attachments/assets/23b6611d-6288-4c9d-8c78-cb2686306ed2" />

- They maintained they representation quality while outputing high quality proteins
- DSM + Synteract2 was used to increase the binding affinity of the commercial cancer treatment Cetuximab, which has a projected [**$7 billion** market cap](https://www.reportsanddata.com/report-detail/cetuximab-market). At the time of release our [Cetuximab variants had 90% higher binding affinity to their target](https://github.com/Gleghorn-Lab/DSM) (EGFR) vs. the commercial option, and 30% over the nearest external designed variant. The data can be found on [Proteinbase](https://proteinbase.com/collections/dsm-round-1).
<table>
  <tr>
    <td>
      <img width="596" height="355" alt="image" src="https://github.com/user-attachments/assets/0c6f690d-3134-44d2-9540-12c277e187b3" />
    </td>
    <td>
      <img src="https://github.com/Gleghorn-Lab/DSM/blob/main/wetlab_result_analysis/egfr/kinetics/dsm_egfr_10_2.png" width="400">
    </td>
  </tr>
</table>

### Tetris For Proteins
- Collaborated with **Stephen Wolfram** & other mentors at the Wolfram Winter School.  
- Developed “[Tetris For Proteins](https://community.wolfram.com/groups/-/m/t/2777595)” – a shape-based metric emulating "lock-and-key" protein-protein interactions.  
- Generated hypotheses on protein aggregation likelihood.
<table>
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/61ebaf0e-3b3d-405f-93ad-0b628ba4945f" width="400" alt="image" />
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/977107b2-1ed6-457f-9dbf-f76a4db3d195" width="400" alt="image" />
    </td>
  </tr>
</table>

### Protify

### SpeedrunningPLMs

### FastPLMs

### Annotation Vocabulary
- Invented the [**Annotation Vocabulary**](https://www.biorxiv.org/content/10.1101/2024.07.30.605924v1.abstract), a unique set of integers mapped to popular protein and gene ontologies.  
- Enables state-of-the-art protein annotation and generation models when paired with its own token embedding.
<img width="1396" height="355" alt="image" src="https://github.com/user-attachments/assets/9dc3aafb-23ab-4796-baf7-349c976c62e4" />

### Codon Usage Bias
- Codon usage bias is highlighted as a key biological phenomenon and valuable feature for machine learning in [Nature Scientific Reports](https://www.nature.com/articles/s41598-023-28965-7).  
  - Our models show codon usage with a powerful phylogenetic association.
  - Introduced [**cdsBERT**](https://huggingface.co/GleghornLab/cdsBERT), showcasing cost-effective ways to enhance biological relevance in protein language models via a codon vocabulary.
<img width="14400" height="4800" alt="pca_combined_cds_simple" src="https://github.com/user-attachments/assets/14fb09ba-e63f-486e-b943-07d5f86b991e" />

### Mixture of Experts Extension
- Invented a [Mixture of Experts extension](https://arxiv.org/abs/2401.15713) for scalable transformer networks adept at sentence similarity tasks.  
  - Future networks with N experts could perform like N independently trained networks, offering significant time and computational savings in semantic retrieval systems.
  - Published in [Nature Scientific Reports](https://www.nature.com/articles/s41598-025-98185-8)
<img width="944" height="695" alt="image" src="https://github.com/user-attachments/assets/faeb88a4-441c-4db8-9cd5-53246b66b4d0" />


### Computer Vision in Biology
- Collaborates on lab projects involving deep learning for reconstructing 3D organs from 2D Z-stacks.  
- Informs morphometric and pharmacokinetic studies to further understanding of organ structure and function.

---

## Additional Projects & Publications

- [featureranker](https://github.com/lhallee/featureranker): A Python package for feature ranking.  
- Textbook Chapter on [Protein Language Models](https://www.researchgate.net/profile/Logan-Hallee/publication/378769504_413_Predicting_Structure_and_Function_of_Biomolecules_Through_Natural_Language_Processing_Tools/links/65e8d39dadc608480a056202/413-Predicting-Structure-and-Function-of-Biomolecules-Through-Natural-Language-Processing-Tools.pdf).
- Machine Learning for identifying [cardioprotective molecules](https://www.ahajournals.org/doi/abs/10.1161/circ.149.suppl_1.P109) in minority groups.
- Investigations of [Hsp90](https://www.mdpi.com/2075-4426/11/12/1373) and [Gamma secretase](https://www.mdpi.com/2075-4426/11/12/1294) in cardiac disease.

---

## Socials / Websites

- [Synthyra](https://synthyra.com/)
- [GitHub](https://github.com/lhallee)
- [LinkedIn](https://www.linkedin.com/in/logan-hallee/)
- [X](https://x.com/Logan_Hallee)
- [Gleghorn Lab](https://www.gleghornlab.com/)
- [Medium](https://medium.com/minds-and-molecules)
- [Substack](https://mindsandmolecules.substack.com/)
- [Facebook](https://www.facebook.com/mindsandmolecules)

### Contact

Research related queries - lhallee@udel.edu

Business related queries - logan@synthyra.com

---

> **Last Updated**: April 2025
