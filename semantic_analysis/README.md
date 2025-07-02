# Semantic Analysis for Vietnamese Texts

## Project Overview
This project focuses on semantic analysis of Vietnamese text data, specifically hate speech and offensive content detection. It uses state-of-the-art Vietnamese language models (PhoBERT and VisoBERT) to classify text into three categories: CLEAN, OFFENSIVE, and HATE.

## Dataset
The project utilizes the [Vietnamese Hate Speech Detection dataset](https://huggingface.co/datasets/sonlam1102/vihsd) (ViHSD) which contains text comments labeled as:
- CLEAN (0): Normal content
- OFFENSIVE (1): Offensive content
- HATE (2): Hate speech content

## Project Structure
- `data/`: Contains augmented datasets
  - `aug_eda_offensive.csv`, `aug_eda_hate.csv`: Data augmented using Easy Data Augmentation techniques
  - `aug_llm_offensive.csv`, `aug_llm_hate.csv`: Data augmented using LLM-based techniques
  - `convert/`: Contains mapping files for text normalization (emoticons, teencode)
- `notebooks/`:
  - `data_exploration.ipynb`: Exploratory data analysis of the dataset
  - `augment_eda.ipynb`: Data augmentation using Easy Data Augmentation
  - `augment_llm.ipynb`: Data augmentation using LLM-based techniques
  - `train_phobert.ipynb`: Training and evaluation using PhoBERT model
  - `train_visobert.ipynb`: Training and evaluation using VisoBERT model

## Features
- **Data Preprocessing**: Text normalization techniques including:
  - Character standardization
  - Emoticon to emoji conversion
  - Teencode to standard Vietnamese conversion
- **Data Augmentation**:
  - EDA (Easy Data Augmentation): Synonym replacement, random insertion, random swap, random deletion
  - LLM-based augmentation: Generation of new examples using language models
- **Model Training**:
  - Fine-tuning of PhoBERT and VisoBERT for text classification
  - Implementation of Focal Loss to handle class imbalance
- **Evaluation**: Comprehensive evaluation metrics including accuracy, precision, recall, F1-score

## Setup and Installation
```bash
# Clone the repository
git clone https://github.com/dangvonguyen/semantic-analysis.git
cd semantic-analysis

# Activate virtual environment and install dependencies
uv sync
source .venv/bin/activate
```
