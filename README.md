# 🧬 Protein Residue-Residue Contact Prediction Model

## 📖 Overview
Proteins are chains of amino acids (residues), represented by single-letter codes (e.g., **M**, **K**, **T**). Understanding **residue-residue contacts** (spatially close residues within 3D structures) is essential for studying **protein folding** and **interactions**.

This project implements a **machine learning model** to predict residue-residue contacts:
- **Input**: Protein sequence.
- **Output**: A **binary contact map**:
  - **1**: Residues are in contact (Cα atoms < 8 Å apart).
  - **0**: Residues are not in contact.

The model leverages **ESM2 embeddings** and integrates **structural data** from similar protein sequences to enhance predictions.

---

## 🛠️ Approach

### 🎯 Goal
Develop a model to predict spatial residue contacts for a given sequence by combining:
1. **ESM2 embeddings** for sequence features.
2. **Structural information** from sequences with similar structures.

### 📂 Data Sources
- **Protein Data Bank (PDB)**: Provides sequence and 3D structural data.
- **ESM2 Architecture**: Supplies pre-trained embeddings for residue representation.

---

## 🔍 Methodology

### 🧑‍💻 Data Preparation
1. **Dataset Splitting**:
   - Data was split into **training**, **validation**, and **test** sets.
   - Similar sequences were handled to avoid train-test leakage.
2. **Input Features**:
   - Primary input: **ESM2 embeddings** of protein sequences.
   - Supplementary input: **Structural features** from related sequences.

### 🏗️ Model Architecture
- **Base Model**: Extended **ESM2** architecture with a **contact prediction head**.
- **Input**: Protein sequence.
- **Output**: Binary contact map.

### ⚙️ Training
- **Loss Function**: Cross-entropy loss on binary contact maps.
- **Validation**: Performance monitored to ensure generalization.

---

## 📊 Results
- **Performance Metrics**:
  - **Accuracy**: 87-90%
  - **Precision**: 85-89%
- **Improvements**: Incorporating structural data boosted predictive performance.

---

## 🚀 Usage

### 📝 Requirements
- **Python 3.x**
- Required libraries:
  - `torch`
  - `esm`
  - `biopython`
  - `numpy`

### ▶️ Running the Model
1. Clone the repository and install dependencies:
   ```bash
   git clone [repository link]
   cd [repository]
   pip install -r requirements.txt

