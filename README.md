# 👏 A Survey of Artificial Intelligence in Drug Discovery

💡 Artificial intelligence has been widely applied in drug discovery over the past decade and is still gaining popularity.
This repository compiles a collection works on related areas, based on the manuscript [Artificial Intelligence in Drug Discovery: Applications and Techniques](https://academic.oup.com/bib/advance-article-abstract/doi/10.1093/bib/bbab430/6420092?redirectedFrom=fulltext) by Jianyuan Deng et al. Hope you will find it useful for your research (citation is provided below). 

🔔 This repository is updated regularly. 

<p align="center">
  <img width="820" height="360" src="/images/github21.png">
</p>

```bibtex
@article{10.1093/bib/bbab430,
    title = "{Artificial intelligence in drug discovery: applications and techniques}",
    author = {Deng, Jianyuan and Yang, Zhibo and Ojima, Iwao and Samaras, Dimitris and Wang, Fusheng},
    journal = {Briefings in Bioinformatics},
    year = {2021},
    month = {11},
    issn = {1477-4054},
    doi = {10.1093/bib/bbab430},
    url = {https://doi.org/10.1093/bib/bbab430},
    note = {bbab430},
    eprint = {https://academic.oup.com/bib/advance-article-pdf/doi/10.1093/bib/bbab430/41068728/bbab430.pdf},
}
```

---
## Contents
- [Reviews and Perspectives](#review)
  - [General Drug Discovery](#general)
  - [Drug Discovery in the AI Era](#aidd)
  - [AI-Driven Drug Discovery: Hope or Hype](#caveats)

- [Data, Representation and Benchmarks](#data)
  - [Large-Scale Databases](#databases)
    - [PubChem](#pubchem)
    - [ChEMBL](#chembl)
    - [ZINC](#zinc)
    - [Others](#others)
  - [Molecular Representations](#molRep)
  - [Benchmark Platforms](#benchmark)
      - [MoleculeNet](#moleculenet)
      - [MolMapNet](#molmapnet)
      - [ChemProp](#chemprop) 
      - [REINVENT](#reinvent) 
      - [Guacamol](#guacamol)  
      - [MOSES](#moses) 
      - [GraphINVENT](#graphinvent)
      - [ATOM3D](#atom3d)

- [Model Architectures](#architec)
  - [Convolutional Neural Networks](#cnn)
  - [Recurrent Neural Networks](#rnn)
  - [Graph Neural Networks](#gnn)
  - [Variational Autoencoders](#vae)
  - [Generative Adversarial Networks](#gan)
  - [Normalizing Flow Models](#flow)
  - [Transformers](#transformer)

- [Learning Paradigms](#learning)
  - [Self-Supervised Learning](#selfsuper)
    - [Generative Learning](#gl)
    - [Contrastive Learning](#cl)
  - [Reinforcement Learning](#rl)
  - [Other Learning Paradigms](#otherlearning)
    - [Metric Learning](#mel)
    - [Few-Shot Learning](#fsl)
    - [Meta Learning](#metal)
    - [Active Learning](#al)

- [Addressing Existing Challenges](#challenges)

---
<a name="review" />

### 1. Reviews and Perspectives

<a name="general" />
<b>1.1 General Drug Discovery</b>

- Integration of virtual and high-throughput screening (Nat Rev Drug Discov 2002) [[Paper]](https://www.nature.com/articles/nrd941)
- Chemical space and biology (Nature 2004) [[Paper]](https://www.nature.com/articles/nature03192)
- Computer-based de novo design of drug-like molecules (Nat Rev Drug Discov 2005) [[Paper]](https://www.nature.com/articles/nrd1799)
- On Outliers and Activity Cliffs-Why QSAR Often Disappoints (J Chem Inf Model 2006) [[Paper]](https://pubs.acs.org/doi/10.1021/ci060117s)
- Virtual screening: an endless staircase? (Nat Rev Drug Discov 2010) [[Paper]](https://www.nature.com/articles/nrd3139)
- Privileged Scaffolds for Library Design and Drug Discovery (Curr Opin Chem Biol 2010) [[Paper]](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2908274/pdf/nihms218619.pdf)
- Principles of early drug discovery (Br J Pharmacol 2011) [[Paper]](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3058157/)
- Recognizing Pitfalls in Virtual Screening: A Critical Review (J Chem Inf Model 2012) [[Paper]](https://pubs.acs.org/doi/full/10.1021/ci200528d)
- Multi-objective optimization methods in drug design (Drug Discov Today 2013) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1740674913000085)
- Finding the rules for successful drug optimisation (Drug Discov Today 2014) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644614000075)
- Recent Progress in Understanding Activity Cliffs and Their Utility in Medicinal Chemistry (J Med Chem 2014) [[Paper]](https://pubs.acs.org/doi/10.1021/jm401120g)
- Automating Drug Discovery (Nat Rev Drug Discov 2017) [[Paper]](https://www.nature.com/articles/nrd.2017.232)
- Interpretation of Quantitative Structure−Activity Relationship Models: Past, Present, and Future (J Chem Inf Model 2017) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.jcim.7b00274)
- Advances and Challenges in Computational Target Prediction (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00832)
- Duality of activity cliffs in drug discovery (Expert Opin Drug Discov 2019) [[Paper]](https://www.tandfonline.com/doi/full/10.1080/17460441.2019.1593371)
- QSAR without borders (Chem Soc Rev 2020) [[Paper]](https://pubs.rsc.org/en/content/articlelanding/2020/cs/d0cs00098a#!divAbstract)
- Designing small molecules for therapeutic success: A contemporary perspective (Drug Discov Today 2021) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644621004244)

<a name="aidd" />
<b>1.2 Drug Discovery in the AI Era</b>

- Machine-learning approaches in drug discovery: methods and applications (Drug Discov Today 2015) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644614004176)
- The rise of deep learning in drug discovery (Drug Discov Today 2018) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644617303598)
- Applications of machine learning in drug discovery and development (Nat Rev Drug Discov 2019)[[Paper]](https://www.nature.com/articles/s41573-019-0024-5)
- Deep Learning in Chemistry (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.9b00266)
- Deep learning for molecular design—a review of the state of the art (Mol Syst Des Eng 2019) [[Paper]](https://pubs.rsc.org/en/content/articlehtml/2019/me/c9me00039a)
- Efficient molecular encoders for virtual screening (Drug Discov Today Technol 2019) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1740674920300123)
- Artificial intelligence in chemistry and drug design (J Comput Aid Mol Des 2020) [[Paper]](https://link.springer.com/article/10.1007/s10822-020-00317-x)
- Graph convolutional networks for computational drug development and discovery (Brief Bioinformatics 2020) [[Paper]](https://academic.oup.com/bib/article/21/3/919/5498046)
- Transfer Learning for Drug Discovery (J Med Chem 2020) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.jmedchem.9b02147)
- Learning Molecular Representations for Medicinal Chemistry (J Med Chem 2020) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.jmedchem.0c00385)
- Exploring chemical space using natural language processing methodologies for drug discovery (Drug Discov Today 2020) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644620300465)
- Practical Notes on Building Molecular Graph Generative Models (Applied AI Letters 2020) [[Paper]](https://onlinelibrary.wiley.com/doi/full/10.1002/ail2.18) 
- A compact review of molecular property prediction with graph neural networks (Drug Discov Today 2020) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1740674920300305)
- Artificial intelligence in drug discovery: Recent advances and future perspectives (Expert Opin Drug Discov 2021) [[Paper]](https://www.tandfonline.com/doi/abs/10.1080/17460441.2021.1909567)
- Artificial intelligence in drug discovery and development (Drug Discov Today 2021) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644620304256?via%3Dihub)
- Graph neural networks for automated de novo drug design (Drug Discov Today 2021) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644621000787)
- De novo molecular design and generative models (Drug Discov Today 2021) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644621002531)
- Artificial Intelligence for Drug Discovery (KDD 2021) [[Paper]](https://dl.acm.org/doi/pdf/10.1145/3447548.3470796) [[Website]](https://deepgraphlearning.github.io/DrugTutorial_KDD2021/) [[TorchDrug]](https://torchdrug.ai/)
- Generative Deep Learning for Targeted Compound Design (J Chem Inf Model 2021) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.0c01496)
- Explainable Machine Learning for Property Predictions in Compound Optimization (J Med Chem 2021) [[Paper]](https://pubs.acs.org/doi/pdf/10.1021/acs.jmedchem.1c01789)

<i>Side Notes: Successful Applications </i>

- Deep learning enables rapid identification of potent DDR1 kinase inhibitors (aka: GENTRL; Nat Biotechnol 2019) [[Paper]](https://www.nature.com/articles/s41587-019-0224-x) [[Code]](https://github.com/insilicomedicine/GENTRL) (Insilico Medicine)
- A Deep Learning Approach to Antibiotic Discovery (Cell 2020) [[Paper]](https://www.sciencedirect.com/science/article/pii/S0092867420301021?via%3Dihub) [[Code]](https://github.com/chemprop/chemprop/blob/master/README.md) (MIT CSAIL)
- "BenevolentAI Announces First Patient Dosed In Its Atopic Dermatitis Clinical Trial" [[Link]](https://www.benevolent.com/news/benevolentai-announces-first-patient-dosed-in-its-atopic-dermatitis-clinical-trial?utm_medium=social&utm_source=twitter&utm_campaign=ptrk) (BenevolentAI)
- "Exscientia Announces First AI-Designed Immuno-Oncology Drug to Enter Clinical Trials" [[Link]](https://www.exscientia.ai/news-insights/exscientia-first-ai-designed-immuno-oncology-drug-trial) (Exscientia)
- "Breaking Big Pharma's AI barrier: Insilico Medicine uncovers novel target, new drug for pulmonary fibrosis in 18 months" [[Link]](https://www.fiercebiotech.com/medtech/breaking-big-pharma-s-ai-barrier-insilico-medicine-uncovers-novel-target-new-drug-for) (Insilico Medicine)


<a name="caveats" />
<b>1.3 AI-Driven Drug Discovery: Hope or Hype</b>

- Rethinking drug design in the artificial intelligence era (Nat Rev Drug Discov 2020) [[Paper]](https://www.nature.com/articles/s41573-019-0050-3)
- Towards reproducible computational drug discovery (J Cheminf 2020) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-020-0408-x)
- Current Trends, Overlooked Issues, and Unmet Challenges in Virtual Screening (J Chem Inf Model 2020) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.9b01101)
- Drug discovery with explainable artificial intelligence (Nat Mach Intell 2020) [[Paper]](https://www.nature.com/articles/s42256-020-00236-4)
- Artificial intelligence in drug discovery: what is realistic, what are illusions? Part 1: Ways to make an impact, and why we are not there yet (Drug Discov Today 2021) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644620305274)
- Artificial intelligence in drug discovery: what is realistic, what are illusions? Part 2: a discussion of chemical and biological data used for AI in drug discovery (Drug Discov Today 2021) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644621000428)
- Critical assessment of AI in drug discovery (Expert Opin Drug Discov 2021) [[Paper]](https://www.tandfonline.com/doi/abs/10.1080/17460441.2021.1915982)
- An Insight into Artificial Intelligence in Drug Discovery: An Interview with Professor Gisbert Schneider (Expert Opin Drug Discov 2021) [[Paper]](https://www.tandfonline.com/doi/abs/10.1080/17460441.2021.1976007)

---
<a name="data" />

### 2. Data, Representation & Benchmarks

<a name="databases"/>

<b>2.1 Large-Scale Databases</b>

<a name="pubchem" />
<b>PubChem</b>

- PubChem in 2021: new data content and improved web interfaces (Nucleic Acids Res 2021) [[Paper]](https://academic.oup.com/nar/article/49/D1/D1388/5957164) [[Website]](https://pubchem.ncbi.nlm.nih.gov/) [[Download]](https://pubchemdocs.ncbi.nlm.nih.gov/downloads)

<a name="chembl" /> 
<b>ChEMBL</b>

- The ChEMBL database in 2017 (Nucleic Acids Res 2017) [[Paper]](https://academic.oup.com/nar/article/45/D1/D945/2605707) [[Website]](https://www.ebi.ac.uk/chembl/) [[Download]](https://chembl.gitbook.io/chembl-interface-documentation/downloads) [[WebAPI]](https://chembl.gitbook.io/chembl-interface-documentation/web-services/chembl-data-web-services)

<a name="zinc" />
<b>ZINC</b>

- ZINC 15 – Ligand Discovery for Everyone (J Chem Inf Model 2015) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.5b00559) [[Website]](https://zinc.docking.org/)

<a name="others" />
<b>Others</b>

- Recent applications of deep learning and machine intelligence on in silico drug discovery: methods, tools and databases (Brief Bioinformatics 2019) [[Paper]](https://academic.oup.com/bib/article/20/5/1878/5062947)
- <b>DrugBank</b> --- DrugBank 5.0: a major update to the DrugBank database for 2018 (Nucleic Acids Res 2018)  [[Paper]](https://academic.oup.com/nar/article/46/D1/D1074/4602867) [[Website]](https://go.drugbank.com/) [[Download]](https://go.drugbank.com/releases/latest)
- <b>KEGG</b> --- KEGG as a reference resource for gene and protein annotation (Nucleic Acids Res 2016)  [[Paper]](https://academic.oup.com/nar/article/44/D1/D457/2502600) [[Website]](https://www.kegg.jp/) [[Download]](https://www.kegg.jp/kegg/download/)
- <b>PDBbind</b> --- PDB-wide collection of binding data: current status of the PDBbind database (Bioinformatics 2015)  [[Paper]](https://academic.oup.com/bioinformatics/article/31/3/405/2365195) [[Website]](http://www.pdbbind-cn.org/) [[Download]](http://www.pdbbind-cn.org/download.php)
- <b>BindingDB</b> --- BindingDB in 2015: A public database for medicinal chemistry, computational chemistry and systems pharmacology (Nucleic Acids Res 2016)  [[Paper]](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4702793/) [[Website]](http://www.bindingdb.org/bind/index.jsp) [[Download]](https://www.bindingdb.org/bind/chemsearch/marvin/SDFdownload.jsp?all_download=yes)
- <b>DUD</b> --- Benchmarking Sets for Molecular Docking (J Med Chem 2006) [[Paper]](https://pubs.acs.org/doi/10.1021/jm0608356) [[Website]](http://dud.docking.org/)
- <b>DUD-E</b> --- Directory of Useful Decoys, Enhanced (DUD-E): Better Ligands and Decoys for Better Benchmarking (J Med Chem 2012) [[Paper]](https://pubs.acs.org/doi/full/10.1021/jm300687e) [[Website]](http://dude.docking.org/) 
- <b>MUV</b> --- Maximum Unbiased Validation (MUV) Data Sets for Virtual Screening Based on PubChem Bioactivity Data (J Chem Inf Model 2009) [[Paper]](https://pubs.acs.org/doi/10.1021/ci8002649) [[Website]](https://www.tu-braunschweig.de/en/pharmchem/forschung/baumann/translate-to-english-muv) 
- <b>STITCH</b> --- STITCH: interaction networks of chemicals and proteins (Nucleic Acids Res 2008) [[Paper]](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2238848/) [[Website]](http://stitch.embl.de/) 
- <b>GLL&GDD</b> --- Ligand and Decoy Sets for Docking to G Protein-Coupled Receptors (J Chem Inf Model 2012) [[Paper]](https://pubs.acs.org/doi/10.1021/ci200412p) [[Website]](http://cavasotto-lab.net/Databases/GDD/) 
- <b>NRLiSt BDB</b> --- NRLiSt BDB, the Manually Curated Nuclear Receptors Ligands and Structures Benchmarking Database (J Med Chem 2014) [[Paper]](https://pubs.acs.org/doi/10.1021/jm500132p) [[Website]](http://nrlist.drugdesign.fr/) 
- <b>SIDER</b> --- The SIDER database of drugs and side effects (Nucleic Acids Res 2016) [[Paper]](https://academic.oup.com/nar/article/44/D1/D1075/2502602) [[Website]](http://sideeffects.embl.de/) 
- <b>Offsides&Twosides</b> --- Data-driven prediction of drug effects and interactions (Sci Transl Med 2012) [[Paper]](https://stm.sciencemag.org/content/4/125/125ra31.long) [[Website]](http://tatonettilab.org/offsides/) 
- <b>DILIrank</b> --- DILIrank: the largest reference drug list ranked by the risk for developing drug-induced liver injury in humans (Drug Discov Today 2016) [[Paper]](https://www.sciencedirect.com/science/article/pii/S1359644616300411?via%3Dihub) [[Website]](https://www.fda.gov/science-research/liver-toxicity-knowledge-base-ltkb/drug-induced-liver-injury-rank-dilirank-dataset)  
- <b>UniProt</b> --- UniProt: the universal protein knowledgebase in 2021 (Nucleic Acids Res 2021) [[Paper]](https://academic.oup.com/nar/article/49/D1/D480/6006196) [[Website]](https://www.uniprot.org/)  
- <b>PDB</b> --- The Protein Data Bank (Nucleic Acids Res 2000) [[Paper]](https://academic.oup.com/nar/article/28/1/235/2384399) [[Website]](https://www.rcsb.org/) 


<a name="molRep" />

<b>2.2 Small Molecule Representations</b>

- Molecular representations in AI‑driven drug discovery: a review and practical guide (J Cheminf 2020) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-020-00460-5)

<a name="benchmark" />

<b>2.3 Benchmark Platforms</b>

<a name="moleculenet" />
<b>MoleculeNet</b>

- MoleculeNet: a benchmark for molecular machine learning (Chem Sci 2018) [[Paper]](https://pubs.rsc.org/en/content/articlehtml/2018/sc/c7sc02664a) [[Code]](https://github.com/deepchem/deepchem) [[Download]](http://moleculenet.ai/datasets-1)

<a name="molmapnet" />
<b>MolMapNet</b>

- Out-of-the-box deep learning prediction of pharmaceutical properties by broadly learned knowledge-based molecular representations (Nat Mach Intell 2021) [[Paper]](https://www.nature.com/articles/s42256-021-00301-6) [[Code]](https://github.com/shenwanxiang/ChemBench) 

<a name="chemprop" />
<b>ChemProp</b>

- Analyzing Learned Molecular Representations for Property Prediction (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.jcim.9b00237) [[Code]](https://github.com/chemprop/chemprop) [[Website]](http://chemprop.csail.mit.edu/)

<a name="reinvent" />
<b>REINVENT</b>

- Molecular De Novo design using Recurrent Neural Networks and Reinforcement Learning (J Cheminf 2017) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-017-0235-x) [[Code]](https://github.com/MarcusOlivecrona/REINVENT)
- REINVENT 2.0 – an AI Tool for De Novo Drug Design (J Chem Inf Model 2020) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.jcim.0c00915) [[Code]](https://github.com/MolecularAI/Reinvent)

<a name="graphinvent" />
<b>GraphINVENT</b>

- Graph Networks for Molecular Design (aka: GraphINVENT; Mach Learn: Sci Technol 2021) [[Paper]](https://iopscience.iop.org/article/10.1088/2632-2153/abcf91/pdf) [[Code]](https://github.com/MolecularAI/GraphINVENT)
- Practical Notes on Building Molecular Graph Generative Models (Applied AI Letters 2020) [[Paper]](https://onlinelibrary.wiley.com/doi/full/10.1002/ail2.18) [[Code]](https://github.com/MolecularAI/GraphINVENT)

<a name="guacamol" />
<b>Guacamol</b>

- GuacaMol: Benchmarking Models for de Novo Molecular Design (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00839) [[Code]](https://github.com/BenevolentAI/guacamol)

<a name="moses" />
<b>MOSES</b>

- Molecular Sets (MOSES): A Benchmarking Platform for Molecular Generation Models (Front Pharmacol 2020) [[Paper]](https://www.frontiersin.org/articles/10.3389/fphar.2020.565644/full) [[Code]](https://github.com/molecularsets/moses)

<a name="atom3d" />
<b>ATOM3D</b>

- ATOM3D: Tasks On Molecules in Three Dimensions (NeurIPS 2021) [[Paper]](https://arxiv.org/pdf/2012.04035.pdf) [[Code]](https://github.com/drorlab/atom3d) [[Website]](https://www.atom3d.ai/)

---
<a name="architec" />

### 3. Model Architectures

<a name="cnn" />

<b>3.1 Convolutional Neural Networks</b>

<i>Task*: Molecular Property Prediction; Representation*: Images</i>

- Convolutional Embedding of Attributed Molecular Graphs for Physical Property Prediction (J Chem Inf Model 2017) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.6b00601) (Techs - CNN + SVM)
- Chemception: a deep neural network with minimal chemistry knowledge matches the performance of expert-developed QSAR/QSPR models (aka: Chemception; arXiv 2017) [[Paper]](https://arxiv.org/pdf/1706.06689.pdf)
- Toxic Colors: The Use of Deep Learning for Predicting Toxicity of Compounds Merely from Their Graphic Images (aka: Toxic Colors; J Chem Inf Model 2018) [[Paper]](https://pubmed.ncbi.nlm.nih.gov/30063345/)
- KekuleScope: prediction of cancer cell line sensitivity and compound potency using convolutional neural networks trained on compound images (J Cheminf 2019) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-019-0364-5) [[Code]](https://github.com/isidroc/kekulescope) (Techs - CNN)
- Learning Drug Functions from Chemical Structures with Convolutional Neural Networks and Random Forests (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.9b00236) (Techs - CNN)
- DEEPScreen: high performance drug–target interaction prediction with convolutional neural networks using 2-D structural compound representation (Chem Sci 2020) [[Paper]](https://pubs.rsc.org/en/content/articlelanding/2020/sc/c9sc03414e#!divAbstract) [[Code]](https://github.com/cansyl/DEEPScreen)

<i>Task*: Molecular Property Prediction; Representation*: Fingerprints</i>

- Massively Multitask Networks for Drug Discovery (arXiv 2015) [[Paper]](https://arxiv.org/pdf/1502.02072.pdf) 
- Convolutional Networks on Graphs for Learning Molecular Fingerprints (NeurIPS 2015) [[Paper]](https://arxiv.org/pdf/1509.09292.pdf) [[Code]](https://github.com/HIPS/neural-fingerprint)

<i>Side Note: Molecular Structure Extraction and Recognition</i>

- Molecular Structure Extraction from Documents Using Deep Learning (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00669)
- DECIMER-Segmentation: Automated extraction of chemical structure depictions from scientific literature (J Cheminf 2021) [[Paper]](https://link.springer.com/article/10.1186/s13321-021-00496-1)
- DECIMER: towards deep learning for chemical image recognition (J Cheminf 2020) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-020-00469-w) [[Code]](https://github.com/Kohulan/DECIMER-Image-to-SMILES)
- DECIMER 1.0: Deep Learning for Chemical Image Recognition using Transformers (chemRxiv 2021) [[Paper]](https://chemrxiv.org/articles/preprint/DECIMER_1_0_Deep_Learning_for_Chemical_Image_Recognition_using_Transformers/14479287)
- Img2Mol - Accurate SMILES Recognition from Molecular Graphical Depictions (Chem Sci 2021) [[Paper]](https://pubs.rsc.org/en/content/articlepdf/2021/sc/d1sc01839f) [[Code]](https://github.com/bayer-science-for-a-better-life/Img2Mol)

<a name="rnn" />

<b>3.2 Recurrent Neural Networks</b>

<i>Task*: Molecular Property Prediction; Representation*: SMILES Strings</i>

- SMILES2Vec: An Interpretable General-Purpose Deep Neural Network for Predicting Chemical Properties (aka: SMILES2Vec; arXiv 2017) [[Paper]](https://arxiv.org/pdf/1712.02034.pdf)
- Large-scale comparison of machine learning methods for drug target prediction on ChEMBL (aka:SmilesLSTM; Chem Sci 2018) [[Paper]](https://pubs.rsc.org/en/content/articlelanding/2018/sc/c8sc00148k#!divAbstract) [[Code]](https://github.com/ml-jku/lsc) (Techs - RNN + GNN + Multi-Task Learning)

<i>Task*: Molecule Generation; Representation*: SMILES Strings</i>

- Molecular de‑novo design through deep reinforcement learning (aka: REINVENT; J Cheminf 2017) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-017-0235-x) (Techs - RNN: GRU + RL: Policy-gradient REINFORCE)
- Generating Focused Molecule Libraries for Drug Discovery with Recurrent Neural Networks (aka: CharRNN; ACS Cent Sci 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acscentsci.7b00512) (Techs - Transfer Learning)
- Exploring Deep Recurrent Models with Reinforcement Learning for Molecule Design (ICLR 2018 Workshop) [[Paper]](https://openreview.net/pdf?id=Bk0xiI1Dz) (Techs - RL: Hybrid A2C, Policy-gradient PPO) 
- Deep Reinforcement Learning for de novo Drug Design（aka: ReLeaSE; Sci Adv 2018）[[Paper]](https://advances.sciencemag.org/content/4/7/eaap7885) [[Code]](https://github.com/isayev/ReLeaSE) (Techs - RL: Policy-gradient REINFORCE)
- Deep Reinforcement Learning for Multiparameter Optimization in de novo Drug Design (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.9b00325) [[Code]](https://github.com/stan-his/DeepFMPO) (Techs - RNN: BiLSTM + RL: Hybrid Actor-Critic)
- Scaffold-Constrained Molecular Generation (J Chem Inf Model 2020) [[Paper]](https://pubs.acs.org/doi/pdf/10.1021/acs.jcim.0c01015) (Techs - RL: Policy-based Hill Climbing)

<i>Task*: Molecule Generation; Representation*: Molecular Graphs</i>

- GraphRNN: Generating Realistic Graphs with Deep Auto-regressive Models (aka: GraphRNN; ICML 2018) [[Paper]](https://arxiv.org/pdf/1802.08773.pdf) [[Code]](https://github.com/JiaxuanYou/graph-generation)
- Learning Deep Generative Models of Graphs (ICML 2018) [[Paper]](https://arxiv.org/abs/1803.03324) [[Code]](https://github.com/JiaxuanYou/graph-generation/blob/master/main_DeepGMG.py) (Techs - RNN: LSTM)
- MolecularRNN: Generating realistic molecular graphs with optimized properties (arXiv 2019) [[Paper]](https://arxiv.org/abs/1905.13372)
- A Deep-Learning View of Chemical Space Designed to Facilitate Drug Discovery (aka: DESMILES; J Chem Inf Model 2020) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.0c00321)

<a name="gnn" />

<b>3.3 Graph Neural Networks</b>

<i>Task*: Molecular Property Prediction; Representation*: Molecular Graphs</i>

- Molecular Graph Convolutions: Moving Beyond Fingerprints (aka: Weave; J Comput Aided Mol Des 2016) [[Paper]](https://arxiv.org/pdf/1603.00856.pdf)
- Convolutional Embedding of Attributed Molecular Graphs for Physical Property Prediction (J Chem Inf Model 2017) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.6b00601)
- Semi-supervised classification with graph convolutional networks (aka: GraphConv; ICLR 2017) [[Paper]](https://arxiv.org/pdf/1609.02907.pdf) [[Code]](https://github.com/tkipf/gcn)
- Neural Message Passing for Quantum Chemistry (aka: MPNN; ICML 2017) [[Paper]](https://arxiv.org/pdf/1704.01212.pdf) [[Code]](https://github.com/priba/nmp_qc)
- SchNet: A continuous-filter convolutional neural network for modeling quantum interactions (aka: SchNet; NeurIPS 2017)[[Paper]](https://dl.acm.org/doi/pdf/10.5555/3294771.3294866) [[Code]](https://github.com/atomistic-machine-learning/SchNet)
- Low Data Drug Discovery with One-Shot Learning (ACS Cent Sci 2017) [[Paper]](https://pubs.acs.org/doi/10.1021/acscentsci.6b00367) (Techs - LSTM: BiLSTM, attLSTM + GNN + Few-Shot Learning)
- Large-scale comparison of machine learning methods for drug target prediction on ChEMBL (aka:SmilesLSTM; Chem Sci 2018) [[Paper]](https://pubs.rsc.org/en/content/articlelanding/2018/sc/c8sc00148k#!divAbstract) [[Code]](https://github.com/ml-jku/lsc) (Techs - RNN + GNN + Multi-Task Learning)
- PotentialNet for Molecular Property Prediction (aka: PotentialNet; ACS Cent Sci 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acscentsci.8b00507) (Techs - GNN: GCNN + Multi-Task Learning)
- Molecular Property Prediction: A Multilevel Quantum Interactions Modeling Perspective (aka: MGCN; AAAI 2019) [[Paper]](https://arxiv.org/abs/1906.11081)
- Deep Learning-Based Prediction of Drug-Induced Cardiotoxicity (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00769) [[Code]](https://github.com/ChengF-Lab/deephERG) (Techs - GCN + Multi-task Learning)
- DeepChemStable: Chemical Stability Prediction with an Attention-Based Graph Convolution Network (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00672) (Techs - GCN + Attention)
- Analyzing Learned Molecular Representations for Property Prediction (aka: Chemrop, D-MPNN; J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.9b00237) [[Code]](https://github.com/chemprop/chemprop)
- Molecule Property Prediction Based on Spatial Graph Embedding (aka: C-SGEN; J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.9b00410) [[Code]](https://github.com/wxfsd/C-SGEN)
- Pushing the Boundaries of Molecular Representation for Drug Discovery with the Graph Attention Mechanism (aka: Attentive FP; J Med Chem 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jmedchem.9b00959) [[Code]](https://github.com/OpenDrugAI/AttentiveFP)
- Graph convolutional neural networks as” general-purpose” property predictors: the universality and limits of applicability (J Chem Inf Model 2020) [[Paper]](https://pubs.acs.org/doi/abs/10.1021/acs.jcim.9b00587)
- N-Gram Graph: Simple Unsupervised Representation for Graphs, with Applications to Molecules (aka: N-Gram Graph; NeurIPS 2019) [[Paper]](https://arxiv.org/pdf/1806.09206.pdf)
- Building attention and edge message passing neural networks for bioactivity and physical–chemical property prediction (J Cheminf 2020) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-019-0407-y) [[Code]](https://github.com/edvardlindelof/graph-neural-networks-for-drug-discovery) (Techs - MPNN + Multi-Task Learning)
- A self‑attention based message passing neural network for predicting molecular lipophilicity and aqueous solubility (J Cheminf 2020) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-020-0414-z) [[Code]](https://github.com/tbwxmu/SAMPN) (Techs - MPNN + Self-Attention: Interpretability)
- Chemically Interpretable Graph Interaction Network for Prediction of Pharmacokinetic Properties of Drug-Like Molecules (aka: CIGIN; AAAI 2020) [[Paper]](https://ojs.aaai.org/index.php/AAAI/article/view/5433) [[Code]](https://github.com/devalab/CIGIN)
- Strategies for Pre-training Graph Neural Networks (ICLR 2020) [[Paper]](https://arxiv.org/pdf/1905.12265.pdf) [[Code]](https://github.com/snap-stanford/pretrain-gnns) (Techs - Self-Supervised Learning)
- Directional Message Passing for Molecular Graphs (aka: DimeNet; ICLR 2020) [[Paper]](https://openreview.net/pdf?id=B1eWbxStPH) [[Code]](https://github.com/klicperajo/dimenet)
- Drug–target affinity prediction using graph neural network and contact maps (RSC Advances 2020) [[Paper]](https://pubs.rsc.org/en/content/articlelanding/2020/ra/d0ra02297g#!divAbstract) (Techs - GCN + GAT)
- ASGN: An Active Semi-supervised Graph Neural Network for Molecular Property Prediction (aka: ASGN; KDD 2020) [[Paper]](https://arxiv.org/pdf/2007.03196.pdf) [[Code]](https://github.com/HaoZhongkai/AS_Molecule) (Techs - Active Learning)
- Meta-Learning GNN Initializations for Low-Resource Molecular Property Prediction (ICML 2020 Workshop) [[Paper]](https://arxiv.org/pdf/2003.05996.pdf) [[Code]](https://github.com/GSK-AI/meta-learning-qsar) (Techs - GGNN + Meta Learning: MAML, FO-MAML, ANIL) 

<i>Task*: Molecule Generation; Representation*: Molecular Graphs</i>

- Multi‑objective de novo drug design with conditional graph generative model (J Cheminf 2018) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-018-0287-6) [[Code]](https://github.com/kevinid/molecule_generator) (Techs - Conditional Graph Generative Model: MolMP, MolRNN)
- Graph Convolutional Policy Network for Goal-Directed Molecular Graph Generation (aka: GCPN; NeurIPS 2018) [[Paper]](https://arxiv.org/pdf/1806.02473.pdf) [[Code]](https://github.com/bowenliu16/rl_graph_generation) (Techs - GCN + RL: PPO)
- Optimization of Molecules via Deep Reinforcement Learning (aka: MolDQN; Sci Rep 2019) [[Paper]](https://www.nature.com/articles/s41598-019-47148-x) (Techs - RL: Q-learning)
- Improving Molecular Design by Stochastic Iterative Target Augmentation (ICML 2020) [[Paper]](https://arxiv.org/pdf/2002.04720.pdf) [[Code]](https://github.com/yangkevin2/icml2020-stochastic-iterative-target-augmentation) (Techs - VSeq2Seq/HierGNN + Semi-Supervised Learnning) 
- DeepGraphMolGen, a multi‑objective, computational strategy for generating molecules with desirable properties: a graph convolution and reinforcement learning approach (J Cheminf 2020) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-020-00454-3) (Techs - GCN + RL: PPO)
- Reinforced Molecular Optimization with Neighborhood-Controlled Grammars (aka: MNCE-RL; NeurIPS 2020) [[Paper]](https://papers.nips.cc/paper/2020/file/5f268dfb0fbef44de0f668a022707b86-Paper.pdf) [[Code]](https://github.com/Zoesgithub/MNCE-RL) (Techs - RL: PPO)
- Graph Networks for Molecular Design (aka: GraphINVENT; Mach Learn: Sci Technol 2021) [[Paper]](https://iopscience.iop.org/article/10.1088/2632-2153/abcf91/pdf) [[Code]](https://github.com/MolecularAI/GraphINVENT)
- De novo drug design using reinforcement learning with graph-based deep generative models (aka: RL-GraphINVENT; ChemRxiv 2021) [[Paper]](https://chemrxiv.org/engage/api-gateway/chemrxiv/assets/orp/resource/item/60fc07bd171fc7a0adb87039/original/de-novo-drug-design-using-reinforcement-learning-with-graph-based-deep-generative-models.pdf) [[Code]](https://github.com/olsson-group/RL-GraphINVENT)

<i>Side Note: Common GNN Models</i>

- <b>Recurrent GNNs</b>   Gated graph sequence neural networks (aka: GGNN; ICLR 2016) [[Paper]](https://arxiv.org/pdf/1511.05493.pdf) [[Code]](https://github.com/yujiali/ggnn)
- <b>Convolutional GNNs (Spectral-based)</b>   Convolutional Neural Networks on Graphs with Fast Localized Spectral Filtering (aka: ChebNet; NeurIPS 2016) [[Paper]](https://arxiv.org/pdf/1606.09375.pdf) [[Code]](https://github.com/mdeff/cnn_graph)
- <b>Convolutional GNNs (Spectral-based)</b>   Semi-supervised classification with graph convolutional networks (aka: GraphConv; ICLR 2017) [[Paper]](https://arxiv.org/pdf/1609.02907.pdf) [[Code]](https://github.com/tkipf/gcn)
- <b>Convolutional GNNs (Spatial-based)</b>   Neural message passing for quantum chemistry (aka: MPNN; ICML 2017) [[Paper]](https://arxiv.org/pdf/1704.01212.pdf) [[Code]](https://github.com/priba/nmp_qc)
- <b>Convolutional GNNs (Spatial-based)</b>   Inductive Representation Learning on Large Graphs (aka: GraphSAGE; NeurIPS 2017) [[Paper]](https://arxiv.org/pdf/1706.02216.pdf) [[Code]](https://github.com/williamleif/GraphSAGE)
- <b>Convolutional GNNs (Spatial-based)</b>   Graph Attention Networks (aka: GAT; ICLR 2018) [[Paper]](https://arxiv.org/pdf/1710.10903.pdf) [[Code]](https://github.com/PetarV-/GAT)
- <b>Convolutional GNNs (Spatial-based)</b>   How powerful are graph neural networks? (aka: GIN; ICLR 2019) [[Paper]](https://arxiv.org/pdf/1810.00826.pdf) [[Code]](https://github.com/weihua916/powerful-gnns)

<a name="vae" />

<b>3.4 Variational Autoencoders</b>

<i>Task*: Molecule Generation; Representation*: SMILES Strings</i>

- Automatic chemical design using a data-driven continuous representation of molecules (arXiv 2016; ACS Cent Sci 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acscentsci.7b00572) [[Code]](https://github.com/HIPS/molecule-autoencoder) (Techs - VAE)
- Grammar Variational Autoencoder (aka: GrammarVAE; ICML 2017) [[Paper]](https://dl.acm.org/doi/pdf/10.5555/3305381.3305582) 
- Application of Generative Autoencoder in De Novo Molecular Design (Mol Inform 2017) [[Paper]](https://onlinelibrary.wiley.com/doi/full/10.1002/minf.201700123)
- Syntax-Directed Variational Autoencoder for Structured Data (aka: SD-VAE; ICLR 2018) [[Paper]](https://openreview.net/pdf?id=SyqShMZRb) [[Code]](https://github.com/Hanjun-Dai/sdvae) 
- Conditional Molecular Design with Deep Generative Models （aka: Continuous SSVAE; J Chem Inf Model 2018）[[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00263) [[Code]](https://github.com/nyu-dl/conditional-molecular-design-ssvae) 
- Molecular generative model based on conditional variational autoencoder for de novo molecular design (aka: CVAE; J Cheminf 2018) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-018-0286-7) [[Code]](https://github.com/jaechanglim/CVAE) (Techs - VAE)
- Constrained Graph Variational Autoencoders for Molecule Design (aka: CGVAE; NeurIPS 2018) [[Paper]](https://arxiv.org/pdf/1805.09076.pdf) [[Code]](https://github.com/microsoft/constrained-graph-variational-autoencoder)
- NEVAE: A Deep Generative Model for Molecular Graphs (aka: NeVAE; AAAI 2019) [[Paper]](https://arxiv.org/pdf/1802.05283.pdf) [[Code]](https://github.com/Networks-Learning/nevae)
- De Novo Molecular Design by Combining Deep Autoencoder Recurrent Neural Networks with Generative Topographic Mapping (aka: GTMVAE; J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00751) (Techs - Autoencoder + RNN)
- Re-balancing Variational Autoencoder Loss for Molecule Sequence Generation (aka: re-balanced VAE; ACM BCB 2020) [[Paper]](https://arxiv.org/pdf/1910.00698.pdf) [[Code]](https://github.com/chaoyan1037/Re-balanced-VAE.) (Techs - RNN: BiGRU + VAE) 
- CogMol: Target-Specific and Selective Drug Design for COVID-19 Using Deep Generative Models (aka: CogMol; NeurIPS 2020) [[Paper]](https://proceedings.neurips.cc/paper/2020/file/2d16ad1968844a4300e9a490588ff9f8-Paper.pdf) [[Code]](https://github.com/IBM/controlled-peptide-generation)

<i>VAE Variant: AAE</i>

- Application of Generative Autoencoder in De Novo Molecular Design (Mol Inform 2017) [[Paper]](https://onlinelibrary.wiley.com/doi/full/10.1002/minf.201700123)
- druGAN: An Advanced Generative Adversarial Autoencoder Model for de Novo Generation of New Molecules with Desired Molecular Properties in Silico (aka: druGAN; Mol Pharm 2017) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.molpharmaceut.7b00346?ref=recommended)
- Entangled Conditional Adversarial Autoencoder for de Novo Drug Discovery (aka: SAAE; Mol Pharm 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.molpharmaceut.8b00839)

<i>Task*: Molecule Generation; Representation*: Molecular Graphs</i>

- GraphVAE: Towards Generation of Small Graphs Using Variational Autoencoders (aka: GraphVAE; arXiv 2018) [[Paper]](https://arxiv.org/pdf/1802.03480.pdf)
- Junction Tree Variational Autoencoder for Molecular Graph Generation (aka: JT-VAE; ICML 2018) [[Paper]](https://arxiv.org/abs/1802.04364) [[Code]](https://github.com/wengong-jin/icml18-jtnn)
- Constrained Generation of Semantically Valid Graphs via Regularizing Variational Autoencoders (aka:Regularized VAE; NeurIPS 2018)[[Paper]](https://papers.nips.cc/paper/2018/file/1458e7509aa5f47ecfb92536e7dd1dc7-Paper.pdf) 
- Molecular Hypergraph Grammar with Its Application to Molecular Optimization (aka: MHG-VAE; ICML 2019) [[Paper]](https://arxiv.org/pdf/1809.02745.pdf) [[Code]](https://github.com/ibm-research-tokyo/graph_grammar) 
- Efficient learning of non‑autoregressive graph variational autoencoders for molecular graph generation (J Cheminf 2019) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-019-0396-x) [[Code]](https://github.com/seokhokang/graphvae_approx) (Techs - Non-autoregressive VAE + RL)
- Deep learning enables rapid identification of potent DDR1 kinase inhibitors (aka: GENTRL; Nat Biotechnol 2019) [[Paper]](https://www.nature.com/articles/s41587-019-0224-x) [[Code]](https://github.com/insilicomedicine/GENTRL) (Techs - VAE + RL: REINFORCE)
- Scaffold-based molecular design using graph generative model (aka: ScaffoldVAE; arXiv 2019) [[Paper]](https://arxiv.org/pdf/1905.13639.pdf)
- Learning Multimodal Graph-to-Graph Translation for Molecule Optimization (aka: VJTNN; ICLR 2019) [[Paper]](https://arxiv.org/pdf/1812.01070.pdf) [[Code]](https://github.com/wengong-jin/iclr19-graph2graph) 
- CORE: Automatic Molecule Optimization Using Copy & Refine Strategy (AAAI 2020) [[Paper]](https://arxiv.org/pdf/1912.05910.pdf) [[Code]](https://github.com/futianfan/CORE) 
- Hierarchical Generation of Molecular Graphs using Structural Motifs (aka: HierVAE; ICML 2020) [[Paper]](https://arxiv.org/pdf/2002.03230.pdf) [[Code]](https://github.com/wengong-jin/hgraph2graph) (Techs - Hierarchical VAE) 
- Compressed graph representation for scalable molecular graph generation (J Cheminf 2020) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-020-00463-2) [[Code]](https://github.com/seokhokang/graphvae_compress) (Techs - Non-autoregressive VAE)


<i>Side Note: Reaction & Retrosynthesis Prediction; Representation*: Molecular Graphs</i>

- Generating Molecules via Chemical Reactions (ICLR 2019 Workshop) [[Paper]](https://openreview.net/pdf?id=BJlQEILY_N) 
- Barking up the right tree: an approach to search over molecule synthesis DAG (NeurIPS 2020) [[Paper]](https://papers.nips.cc/paper/2020/file/4cc05b35c2f937c5bd9e7d41d3686fff-Paper.pdf) [[Code]](https://github.com/john-bradshaw/synthesis-dags)


<a name="gan" />

<b>3.5 Generative Adversarial Networks</b>

<i>Task*: Molecule Generation; Representation*: SMILES Strings</i>

- Objective-Reinforced Generative Adversarial Networks (ORGAN) for Sequence Generation Models (aka: ORGAN; ArXiv 2017) [[Paper]](https://arxiv.org/pdf/1705.10843.pdf) [[Code]](https://github.com/gablg1/ORGAN) (Techs - GAN: G-RNN, D-CNN  + RL: REINFORCE)
- Optimizing distributions over molecular space. An objective-reinforced generative adversarial network for inverse-design chemistry (aka: ORGANIC; ChemRxiv 2017) [[Paper]](https://chemrxiv.org/articles/preprint/ORGANIC_1_pdf/5309668) [[Code]](https://github.com/aspuru-guzik-group/ORGANIC) (Techs - GAN + RL: REINFORCE) 
- Reinforced Adversarial Neural Computer for de Novo Molecular Design (aka: RANC; J Chem Inf Model 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.7b00690) (Techs - GAN + RL) 

<i>Task*: Molecule Generation; Representation*: Molecular Graphs</i>

- MolGAN: An implicit generative model for small molecular graphs (aka: MolGAN; ICML 2018 Workshop) [[Paper]](https://arxiv.org/pdf/1805.11973.pdf) [[Code-Tensorflow]](https://github.com/nicola-decao/MolGAN) [[Code-PyTorch]](https://github.com/yongqyu/MolGAN-pytorch) (Techs - GAN + RL: DDPG)


<a name="flow" />

<b>3.6 Normalizing Flow Models</b>

<i>Task*: Molecule Generation; Representation*: Molecular Graphs</i>

- GraphNVP: An Invertible Flow Model for Generating Molecular Graphs (aka: GraphNVP; arXiv 2019) [[Paper]](https://arxiv.org/pdf/1905.11600.pdf) [[Code]](https://github.com/pfnet-research/graph-nvp) 
- Graph Residual Flow for Molecular Graph Generation (aka: GRF; arXiv 2019) [[Paper]](https://arxiv.org/pdf/1909.13521.pdf)
- GraphAF: a Flow-based Autoregressive Model for Molecular Graph Generation (aka: GraphAF; ICLR 2020) [[Paper]](https://openreview.net/pdf?id=S1esMkHYPr) [[Code]](https://github.com/DeepGraphLearning/GraphAF) (Techs - Flow + RL: PPO)
- MoFlow: An Invertible Flow Model for Generating Molecular Graphs (aka: MoFlow; KDD 2020) [[Paper]](https://arxiv.org/pdf/2006.10137.pdf) [[Code]](https://github.com/calvin-zcx/moflow)
- GraphDF: A Discrete Flow Model for Molecular Graph Generation (aka: GraphDF; ICML 2021) [[Paper]](https://arxiv.org/abs/2102.01189)
- Flow Network based Generative Models for Non-Iterative Diverse Candidate Generation (NeurIPS 2021) [[Paper]](https://arxiv.org/pdf/2106.04399.pdf)


<a name="transformer" />

<b>3.7 Transformers</b>

<i>Task*: Molecular Property Prediction; Representation*: SMILES Strings</i>

- SMILES-BERT: Large Scale Unsupervised Pre-Training for Molecular Property Prediction (aka: SMILES-BERT; ACM BCB 2019) [[Paper]](https://dl.acm.org/doi/pdf/10.1145/3307339.3342186) (Techs - BERT)
- SMILES Transformer: Pre-trained Molecular Fingerprint for Low Data Drug Discovery (aka: SMILES Transformer; arXiv 2019) [[Paper]](https://arxiv.org/pdf/1911.04738.pdf) [[Code]](https://github.com/DSPsleeporg/smiles-transformer)
- ChemBERTa: Large-Scale Self-Supervised Pretraining for Molecular Property Prediction (aka: ChemBERTa; arXiv 2020) [[Paper]](https://arxiv.org/pdf/2010.09885.pdf) [[Code]](https://github.com/seyonechithrananda/bert-loves-chemistry)
- Molecular representation learning with language models and domain-relevant auxiliary tasks (aka: MolBERT; NeurIPS 2020 Workshop) [[Paper]](https://arxiv.org/pdf/2011.13230.pdf) [[Code]](https://github.com/BenevolentAI/MolBERT) (Techs - BERT + Self-Supervised Learning)

<i>Task*: Molecular Property Prediction; Representation*: Molecular Graphs</i>

- Self-Supervised Graph Transformer on Large-Scale Molecular Data (aka: GROVER; NeurIPS 2020) [[Paper]](https://arxiv.org/pdf/2007.02835.pdf) [[Code]](https://github.com/tencent-ailab/grover) (Techs - Graph Transformer + Self-Supervised Learning)


<i>Task*: Molecule Generation; Representation*: Molecular Graphs</i>

- A Model to Search for Synthesizable Molecules (aka: Molecule Chef; NeurIPS 2019) [[Paper]](https://arxiv.org/pdf/1906.05221.pdf) [[Code]](https://github.com/john-bradshaw/molecule-chef)
- Transformer neural network for protein-specific de novo drug generation as a machine translation problem (Sci Rep 2021) [[Paper]](https://www.nature.com/articles/s41598-020-79682-4)


---
<a name="learning" />

### 4. Learning Paradigms


<a name="selfsuper" />

<b>4.1 Self-Supervised Learning in Molecular Property Prediction</b>

<a name="gl" />

<i>Generative Learning</i>

- Strategies for Pre-training Graph Neural Networks (ICLR 2020) [[Paper]](https://arxiv.org/pdf/1905.12265.pdf) [[Code]](https://github.com/snap-stanford/pretrain-gnns) (Techs - Self-Supervised Learning)
- Molecular representation learning with language models and domain-relevant auxiliary tasks (aka: MolBERT; NeurIPS 2020 Workshop) [[Paper]](https://arxiv.org/pdf/2011.13230.pdf) [[Code]](https://github.com/BenevolentAI/MolBERT) (Techs - BERT + Self-Supervised Learning)
- Self-Supervised Graph Transformer on Large-Scale Molecular Data (aka: GROVER; NeurIPS 2020) [[Paper]](https://arxiv.org/pdf/2007.02835.pdf) [[Code]](https://github.com/tencent-ailab/grover) (Techs - Graph Transformer + Self-Supervised Learning)


<a name="cl" />

<i>Contrastive Learning</i>

- MolCLR: Molecular Contrastive Learning of Representations via Graph Neural Networks (ArXiv 2021) [[Paper]](https://arxiv.org/pdf/2102.10056.pdf)


<a name="rl" />

<b>4.2 Reinforcement Learning in Molecule Generation</b>

- Objective-Reinforced Generative Adversarial Networks (ORGAN) for Sequence Generation Models (aka: ORGAN; ArXiv 2017) [[Paper]](https://arxiv.org/pdf/1705.10843.pdf) [[Code]](https://github.com/gablg1/ORGAN) (Techs - GAN: G-RNN, D-CNN  + RL: Policy-gradient REINFORCE)
- Molecular de‑novo design through deep reinforcement learning (aka: REINVENT; J Cheminf 2017) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-017-0235-x) (Techs - RNN: GRU + RL: Policy-gradient REINFORCE)
- Optimizing distributions over molecular space. An objective-reinforced generative adversarial network for inverse-design chemistry (aka: ORGANIC; ChemRxiv 2017) [[Paper]](https://chemrxiv.org/articles/preprint/ORGANIC_1_pdf/5309668) [[Code]](https://github.com/aspuru-guzik-group/ORGANIC) (Techs - GAN + RL: Policy-gradient REINFORCE) 
- Reinforced Adversarial Neural Computer for de Novo Molecular Design (aka: RANC; J Chem Inf Model 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.7b00690) (Techs - GAN + RL) 
- Exploring Deep Recurrent Models with Reinforcement Learning for Molecule Design (ICLR 2018 Workshop) [[Paper]](https://openreview.net/pdf?id=Bk0xiI1Dz) (Techs - RL: Hybrid A2C, Policy-gradient PPO)
- MolGAN: An implicit generative model for small molecular graphs (aka: MolGAN; ICML 2018 Workshop) [[Paper]](https://arxiv.org/pdf/1805.11973.pdf) [[Code-Tensorflow]](https://github.com/nicola-decao/MolGAN) [[Code-PyTorch]](https://github.com/yongqyu/MolGAN-pytorch) (Techs - GAN + RL: Hybrid Actor-Critic DDPG)
- Deep Reinforcement Learning for de novo Drug Design（aka: ReLeaSE; Sci Adv 2018）[[Paper]](https://advances.sciencemag.org/content/4/7/eaap7885) [[Code]](https://github.com/isayev/ReLeaSE) (Techs - RL: Policy-gradient REINFORCE)
- Graph Convolutional Policy Network for Goal-Directed Molecular Graph Generation (aka: GCPN; NeurIPS 2018)[[Paper]](https://proceedings.neurips.cc/paper/2018/file/d60678e8f2ba9c540798ebbde31177e8-Paper.pdf) [[Code]](https://github.com/bowenliu16/rl_graph_generation) (Techs - GCN + RL: Policy-gradient PPO)
- Deep learning enables rapid identification of potent DDR1 kinase inhibitors (aka: GENTRL; Nat Biotechnol 2019) [[Paper]](https://www.nature.com/articles/s41587-019-0224-x) [[Code]](https://github.com/insilicomedicine/GENTRL) (Techs - VAE + RL: Policy-gradient REINFORCE)
- Deep Reinforcement Learning for Multiparameter Optimization in de novo Drug Design (aka: DeepFMPO; J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.9b00325) [[Code]](https://github.com/stan-his/DeepFMPO) (Techs - RNN: BiLSTM + RL: Hybrid Actor-Critic)
- Optimization of Molecules via Deep Reinforcement Learning (aka: MolDQN; Sci Rep 2019) [[Paper]](https://www.nature.com/articles/s41598-019-47148-x) (Techs - RL: Value-based Double Q-learning)
- Efficient learning of non‑autoregressive graph variational autoencoders for molecular graph generation (J Cheminf 2019) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-019-0396-x) [[Code]](https://github.com/seokhokang/graphvae_approx) (Techs - Non-autoregressive VAE + RL: Policy-gradient)
- GraphAF: a Flow-based Autoregressive Model for Molecular Graph Generation (aka: GraphAF; ICLR 2020) [[Paper]](https://openreview.net/pdf?id=S1esMkHYPr) [[Code]](https://github.com/DeepGraphLearning/GraphAF) (Techs - Flow + RL: Policy-gradient PPO)
- Reinforcement Learning for Molecular Design Guided by Quantum Mechanics (cka: MolGym; ICML 2020) [[Paper]](https://arxiv.org/abs/2002.07717) (Techs - RL: Policy-gradient PPO)
- DeepGraphMolGen, a multi‑objective, computational strategy for generating molecules with desirable properties: a graph convolution and reinforcement learning approach (aka: DeepGraphMolGen; J Cheminf 2020) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-020-00454-3) (Techs - GCN + RL: Policy-gradient PPO)
- Reinforced Molecular Optimization with Neighborhood-Controlled Grammars (aka: MNCE-RL; NeurIPS 2020) [[Paper]](https://papers.nips.cc/paper/2020/file/5f268dfb0fbef44de0f668a022707b86-Paper.pdf) [[Code]](https://github.com/Zoesgithub/MNCE-RL) (Techs - RL: Policy-gradient PPO)
- Deep inverse reinforcement learning for structural evolution of small molecules (Brief Bioinform 2021) [[Paper]](https://academic.oup.com/bib/article-abstract/22/4/bbaa364/6043289?redirectedFrom=fulltext) [[Code]](https://github.com/bbrighttaer/irelease) (Techs - Inverse RL)

<i>Side Note: Common RL Algorithms</i>

- <b>Value-based</b>   Playing Atari with Deep Reinforcement Learning (aka: DQN; NeurIPS Workshop 2013) [[Paper]](https://arxiv.org/pdf/1312.5602.pdf)
- <b>Value-based</b>   Human-level control through deep reinforcement learning (aka: DQN; Nature 2015) [[Paper]](https://www.nature.com/articles/nature14236)
- <b>Value-based</b>   Deep Reinforcement Learning with Double Q-learning (aka: Double Q-learning; AAAI 2016) [[Paper]](https://arxiv.org/pdf/1509.06461.pdf)
- <b>Value-based</b>   Prioritized Experience Replay (aka: DQN with Experience Replay; ICLR 2016) [[Paper]](https://arxiv.org/pdf/1511.05952.pdf)
- <b>Value-based</b>   Dueling Network Architectures for Deep Reinforcement Learning (aka: Dueling Network; ICML 2016) [[Paper]](https://arxiv.org/pdf/1511.06581.pdf)
- <b>Policy-gradient</b>   Simple statistical gradient-following algorithms for connectionist reinforcement learning (aka: REINFORCE; Mach Learn 1992) [[Paper]](https://link.springer.com/article/10.1007/BF00992696)
- <b>Policy-gradient</b>   Policy Gradient Methods for Reinforcement Learning with Function Approximation (aka: Random Policy Gradient; NeurIPS 1999) [[Paper]](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.6.696&rep=rep1&type=pdf)
- <b>Policy-gradient</b>   Deterministic Policy Gradient Algorithms (aka: DPG; ICML 2014) [[Paper]](http://proceedings.mlr.press/v32/silver14.pdf)
- <b>Policy-gradient</b>   Trust Region Policy Optimization (aka: TRPO; ICML 2015) [[Paper]](https://arxiv.org/pdf/1502.05477.pdf)
- <b>Policy-gradient</b>   Proximal Policy Optimization Algorithms (aka: PPO; arXiv 2017 2015) [[Paper]](https://arxiv.org/pdf/1707.06347.pdf)
- <b>Hybrid</b>   Continuous control with deep reinforcement learning (aka: DDPG; ICLR 2016) [[Paper]](https://arxiv.org/pdf/1509.02971.pdf)
- <b>Hybrid</b>   Asynchronous Methods for Deep Reinforcement Learning (aka: A3C; ICML 2016) [[Paper]](https://arxiv.org/pdf/1602.01783.pdf)

<i>Side Note: Pareto Optimality</i>

- De Novo Drug Design of Targeted Chemical Libraries Based on Artificial Intelligence and Pair-Based Multiobjective Optimization (J Chem Inf Model 2020) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.jcim.0c00517) [[Code]](https://github.com/alberdom88/moo-denovo) (Techs - Pareto Optimality)
- Multiobjective de novo drug design with recurrent neural networks and nondominated sorting (J Cheminf 2020) [[Paper]](https://link.springer.com/article/10.1186/s13321-020-00419-6) (Techs - Pareto Optimality)
- DrugEx v2: De Novo Design of Drug Molecule by Pareto-based Multi-Objective Reinforcement Learning in Polypharmacology (ChemRxiv) [[Paper]](https://chemrxiv.org/articles/preprint/DrugEx_v2_De_Novo_Design_of_Drug_Molecule_by_Pareto-based_Multi-Objective_Reinforcement_Learning_in_Polypharmacology/14474127) (Techs - Pareto Optimality)

<i>Side Note: Reaction & Retrosynthesis Optimization</i>

- Optimizing chemical reactions with deep reinforcement learning (ACS Cent Sci 2017) [[Paper]](https://pubs.acs.org/doi/10.1021/acscentsci.7b00492)

<a name="otherlearning" />

<b>4.4 Other Learning Paradigms</b>

<a name="mel" />

<i>Metric Learning</i>

- Machine-guided representation for accurate graph-based molecular machine learning (Phys Chem Chem Phys 2020) [[Paper]](https://pubs.rsc.org/en/content/articlehtml/2020/cp/d0cp02709j)
- Embedding of Molecular Structure Using Molecular Hypergraph Variational Autoencoder with Metric Learning (Mol Inform 2020) [[Paper]](https://onlinelibrary.wiley.com/doi/full/10.1002/minf.202000203)

<a name="fsl" />

<i>Few-Shot Learning</i>

- Low Data Drug Discovery with One-Shot Learning (ACS Cent Sci 2017) [[Paper]](https://pubs.acs.org/doi/10.1021/acscentsci.6b00367) (Techs - LSTM: BiLSTM, attLSTM + GNN + Few-Shot Learning)
- Few-Shot Graph Learning for Molecular Property Prediction (WWW 2021) [[Paper]](https://arxiv.org/abs/2102.07916) [[Code]](https://github.com/zhichunguo/Meta-MGNN)

<a name="metal" />

<i>Meta Learning</i>

- Meta-Learning GNN Initializations for Low-Resource Molecular Property Prediction (ICML 2020 Workshop) [[Paper]](https://arxiv.org/pdf/2003.05996.pdf) [[Code]](https://github.com/GSK-AI/meta-learning-qsar) (Techs - Gated GNN + Meta Learning: MAML, FO-MAML, ANIL)

<a name="al" />

<i>Active Learning</i>

- ASGN: An Active Semi-supervised Graph Neural Network for Molecular Property Prediction (aka: ASGN; KDD 2020) [[Paper]](https://arxiv.org/pdf/2007.03196.pdf) [[Code]](https://github.com/HaoZhongkai/AS_Molecule) (Techs - Active Learning)
- Evidential Deep Learning for Guided Molecular Property Prediction and Discovery (NeurIPS 2020 Workshop) [[Talk]](https://slideslive.at/38942396/evidential-deep-learning-for-guided-molecular-property-prediction-and-discovery?ref=speaker-17456-latest)



---
<a name="challenges" />

### 5. Addressing Existing Challenges

<i>*Model Interpretation*</i>

- Drug Discovery Maps, a Machine Learning Model That Visualizes and Predicts Kinome−Inhibitor Interaction Landscapes (J Chem Inf Model 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00640)
- Using attribution to decode binding mechanism in neural network models for chemistry (PNAS 2019) [[Paper]](https://www.pnas.org/content/pnas/116/24/11624.full.pdf)
- Interpretation of QSAR Models by Coloring Atoms According to Changes in Predicted Activity: How Robust Is It? (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00825)
- Building of Robust and Interpretable QSAR Classification Models by Means of the Rivality Index (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/abs/10.1021/acs.jcim.9b00264)

<i>*Dataset Concerns*</i>

- In Need of Bias Control: Evaluating Chemical Data for Machine Learning in Structure-Based Virtual Screening (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00712)
- Deep Learning-Based Imbalanced Data Classification for Drug Discovery (J Chem Inf Model 2020) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.9b01162) [[Code]](https://github.com/selcukorkmaz/DeepDrug)

<i>*Uncertainty Estimation*</i>

- General Approach to Estimate Error Bars for Quantitative Structure−Activity Relationship Predictions of Molecular Activity (J Chem Inf Model 2018) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.jcim.8b00114)
- Assessment and Reproducibility of Quantitative Structure−Activity Relationship Models by the Nonexpert (J Chem Inf Model 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.7b00523)
- Deep Confidence: A Computationally Efficient Framework for Calculating Reliable Prediction Errors for Deep Neural Networks (J Chem Inf Model 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00542)
- Reliable Prediction Errors for Deep Neural Networks Using Test-Time Dropout (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.jcim.9b00297)
- Minimal-uncertainty prediction of general drug-likeness based on Bayesian neural networks (Nat Mach Intell 2020) [[Paper]](https://www.nature.com/articles/s42256-020-0209-y)
- Assigning Confidence to Molecular Property Prediction (arXiv 2021) [[Paper]](https://arxiv.org/abs/2102.11439)
- Gi and Pal Scores: Deep Neural Network Generalization Statistics (ICLR 2021 Workshop) [[Paper]](https://arxiv.org/pdf/2104.03469.pdf)
- Probabilistic Random Forest improves bioactivity predictions close to the classification threshold by taking into account experimental uncertainty (J Cheminf 2021) [[Paper]](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-021-00539-7)

<i>*Representation Capacity*</i>

- Ligand-Based Virtual Screening Using Graph Edit Distance as Molecular Similarity Measure (J Chem Inf Model 2019) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00820)
- Optimal Transport Graph Neural Networks (arXiv 2020) [[Paper]](https://arxiv.org/abs/2006.04804)

<i>*Out-of-Distribution Generalization*</i>

- Dissecting Machine-Learning Prediction of Molecular Activity: Is an Applicability Domain Needed for Quantitative Structure−Activity Relationship Models Based on Deep Neural Networks? (J Chem Inf Model 2018) [[Paper]](https://pubs.acs.org/doi/full/10.1021/acs.jcim.8b00348)
- Most Ligand-Based Classification Benchmarks Reward Memorization Rather than Generalization (J Chem Inf Model 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.7b00403)
- Molecular Similarity-Based Domain Applicability Metric Efficiently Identifies Out-of-Domain Compounds (J Chem Inf Model 2018) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00597)

<i>*Model Adoption*</i>

- A Turing Test for Molecular Generators (J Med Chem 2020) [[Paper]](https://pubs.acs.org/doi/10.1021/acs.jmedchem.0c01148)

<i>*Molecular Docking*</i>

- Docking and scoring in virtual screening for drug discovery: methods and applications (Nat Rev Drug Discov 2004) [[Paper]](https://www.nature.com/articles/nrd1549.pdf)
- Benchmarking sets for molecular docking (J Med Chem 2006) [[Paper]](https://pubs.acs.org/doi/pdf/10.1021/jm0608356)
- Molecular Docking: A powerful approach for structure-based drug discovery (Curr Comput Aided Drug Des 2011) [[Paper]](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3151162/pdf/nihms-308746.pdf)
- Software for Molecular Docking: a review (Biophys Rev 2017) [[Paper]](https://link.springer.com/content/pdf/10.1007/s12551-016-0247-1.pdf)
- Deep Docking: A Deep Learning Platform for Augmentation of Structure Based Drug Discovery (ACS Cent Sci 2020) [[Paper]](https://pubs.acs.org/doi/pdf/10.1021/acscentsci.0c00229)
- A Deep-Learning Approach toward Rational Molecular Docking Protocol Selection (Molecules 2020) [[Paper]](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7321124/pdf/molecules-25-02487.pdf)
- GNINA 1.0: molecular docking with deep learning (J Cheminf 2021) [[Paper]](https://jcheminf.biomedcentral.com/track/pdf/10.1186/s13321-021-00522-2.pdf)
