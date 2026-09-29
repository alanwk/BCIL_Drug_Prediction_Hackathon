# BCIL Hackathon: Drug Property Prediction and Drug Generation

2026 Hosted by the Biomedical and Clinical Informatics Laboratory (BCIL; <https://najarianlab.ccmb.med.umich.edu/home>). 

This repository contains two educational notebooks developed for the **BCIL lab hackathon**. Together, they introduce complementary applications of machine learning in computational drug discovery:

1. **Drug Property Prediction** — predicting blood–brain barrier permeability using logistic regression and a graph neural network.
2. **Drug Generation** — training a variational autoencoder on the ZINC dataset to generate new molecular structures.

## Repository Contents

| Notebook | Description |
|---|---|
| [`TDC_BBB_prediction_demo.ipynb`](./TDC_BBB_prediction_demo.ipynb) | Explores the Therapeutics Data Commons blood–brain barrier dataset and compares logistic regression with a graph neural network for binary permeability prediction. |
| [`ZINC_VAE_generation_demo.ipynb`](./ZINC_VAE_generation_demo.ipynb) | Trains a variational autoencoder on molecules from the ZINC dataset and samples from the learned latent space to generate new molecular structures. |



## Learning Objectives

By working through these notebooks, participants will gain experience with:

- Loading and exploring molecular datasets
- Representing molecules using SMILES, SELFIES, fingerprints, and molecular graphs
- Cleaning and preprocessing chemical structures
- Developing baseline and deep-learning models
- Inspecting learned molecular embeddings
- Training a generative latent-variable model
- Generating and assessing candidate molecular structures
- Identifying limitations and proposing meaningful extensions


## Notebook 1: Blood–Brain Barrier Permeability Prediction

The first notebook uses the **BBB_Martins** dataset from the [Therapeutics Data Commons](https://tdcommons.ai/) ADME collection. The objective is to predict whether a molecule can permeate the blood–brain barrier.

This is formulated as a binary classification task:

- `1`: the molecule is labeled as blood–brain barrier permeable
- `0`: the molecule is labeled as non-permeable

*Noteable caveat: labels derived from in-vitro but not verified in-vivo*

### Workflow

The notebook covers:

1. Loading the dataset through PyTDC
2. Inspecting the provided training, validation, and test splits
3. Examining class prevalence and imbalance
4. Cleaning and standardizing molecular structures
5. Visualizing representative molecules
6. Converting SMILES into model-specific representations
7. Training and evaluating two classification models
8. Comparing model performance and error patterns
9. Visualizing learned graph embeddings
10. Exploring interpretable molecular descriptors and possible next steps


## Notebook 2: Molecular Generation with a Variational Autoencoder

The second notebook introduces generative molecular modeling using a **variational autoencoder (VAE)** trained on molecules from the [ZINC database](https://zinc.docking.org/).

A VAE learns a continuous latent representation of molecular structures. Once trained, points can be sampled from the latent space and decoded into candidate molecules.

### Workflow

The notebook demonstrates:

1. Loading and preprocessing ZINC molecules
2. Encoding molecular strings into model-ready sequences
3. Training an encoder–decoder architecture
4. Optimizing reconstruction and latent regularization objectives
5. Exploring the learned latent space
6. Sampling latent vectors
7. Decoding samples into candidate molecules
8. Inspecting the validity and properties of generated structures


## Hackathon Guidance

Participants are encouraged to use the notebooks as starting points. A strong hackathon project should clearly communicate:

- The scientific or modeling question being addressed 
- The source of the dataset trained and evaluated on (Many available at <https://tdcommons.ai/single_pred_tasks/adme/>)
- The rationale for the chosen model
- The evaluation methodology
- The observed strengths and limitations
- The chemical or biological interpretation of results


## Data Sources

### Therapeutics Data Commons

The blood–brain barrier notebook accesses the **BBB_Martins** dataset through the Therapeutics Data Commons Python package.

- Website: <https://tdcommons.ai/>
- Documentation: <https://tdcommons.ai/single_pred_tasks/adme/>
- Source code: <https://github.com/mims-harvard/TDC>

### ZINC

The generative-modeling notebook uses molecular data from ZINC, a public database of commercially available compounds.

- Website: <https://zinc.docking.org/>

Users are responsible for reviewing and complying with the terms, licenses, and citation requirements associated with each dataset.


## Software Resources

The notebooks use tools from the following open-source projects:

- [PyTDC](https://github.com/mims-harvard/TDC)
- [RDKit](https://www.rdkit.org/)
- [PyTorch](https://pytorch.org/)
- [PyTorch Geometric](https://pyg.org/)
- [SELFIES](https://github.com/aspuru-guzik-group/selfies)
- [scikit-learn](https://scikit-learn.org/)
- [ZINC](https://zinc.docking.org/)

Please cite the original datasets, software packages, and relevant publications when extending or presenting this work.


## Scope and Disclaimer

This repository is intended for **education, experimentation, and hackathon use**.

The models and generated molecules are not validated for clinical, diagnostic, therapeutic, or commercial use. Predictions of blood–brain barrier permeability are computational estimates and do not replace experimental measurements. Generated molecules have not necessarily been evaluated for synthesizability, toxicity, pharmacokinetics, efficacy, or biological activity.


## Contributing

Hackathon participants may contribute by:

1. Creating a new branch
2. Making a focused change
3. Documenting the motivation and methodology
4. Including reproducible evaluation results
5. Opening a pull request with a concise summary

Please avoid committing large raw datasets, model checkpoints, or generated artifacts unless they are necessary and explicitly approved for the repository.


## Acknowledgments

These materials were prepared for the **BCIL lab hackathon** to support hands-on exploration of predictive and generative machine learning for molecular data.

The project builds upon the work of the Therapeutics Data Commons, ZINC, RDKit, PyTorch, PyTorch Geometric, SELFIES, scikit-learn, and the broader open-source computational chemistry community.