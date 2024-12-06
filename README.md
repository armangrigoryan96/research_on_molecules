Protein Residue-Residue Contact Prediction Model
🧬 Overview
Proteins are complex molecules made up of chains of amino acids (residues), each represented by a single-letter code (e.g., M, K, T). Understanding which residues are spatially close within a protein's 3D structure (residue-residue contacts) is critical for studying protein folding and interactions.

This project implements a machine learning model to predict residue-residue contacts within protein sequences, leveraging ESM2 embeddings and incorporating structural data from sequences similar to the input sequence.

🛠️ Approach
🎯 Objective
The model predicts a binary contact map for a given protein sequence:

1: Residue pairs are in contact (Cα atoms < 8 Å apart).
0: Residue pairs are not in contact.
📂 Data Sources
Protein Data Bank (PDB): Open-source protein sequences and 3D structural data were used for training and evaluation.
ESM2 Architecture: Embeddings from ESM2, a state-of-the-art protein language model, were utilized to represent sequence residues.
🔍 Methodology
🧑‍💻 Data Preparation
Dataset Splitting:
Protein data were divided into training, validation, and test sets.
Sequence similarity was carefully handled to prevent train-test data leakage.
Input Features:
Primary input: Protein sequence embeddings from ESM2.
Additional features: Structural data from sequences similar to the input sequence.
🏗️ Model Architecture
Built upon the ESM2 model, extending its contact prediction head to integrate additional structural information.
Input: Single protein sequence.
Output: Binary contact map predicting spatial residue-residue contacts.
⚙️ Training
Trained the model on annotated protein datasets from PDB.
Optimized using cross-entropy loss on binary contact maps.
Validation ensured generalization across diverse protein sequences.
📊 Results
Accuracy: Achieved [insert accuracy metric] on the test set.
Precision: Achieved [insert precision metric].
The model successfully improved performance by incorporating structural data alongside ESM2 embeddings.
🚀 Usage
📝 Requirements
Python 3.x
Required libraries:
torch
esm
biopython
numpy
