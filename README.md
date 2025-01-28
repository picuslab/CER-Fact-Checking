# 🩺 CER Demo: *Fact-Checking Biomedical Claims*

Welcome to the demo of the *CER (Combining Evidence and Reasoning)* system for fact-checking biomedical claims. This tool combines PubMed, one of the leading biomedical knowledge bases, with Large Language Models (LLMs) to verify the accuracy of claims, generate justifications, and provide reliable classifications.

## 🎥 Demo (or GIF)
[Watch our demo]() to see how CER supports biomedical fact-checking and enhances the transparency of scientific recommendations!

## 📊 Data Sources
We use the following data sources for training and evaluating the system:

- **[PubMed](https://pubmed.ncbi.nlm.nih.gov/)**: A biomedical database containing over 20 million abstracts.
- **HealthFC**: 750 biomedical claims curated by *Vladika et al. (2024)*.
- **BioASQ-7b**: 745 claims from the *BioASQ Challenge, Nentidis et al. (2020)*.
- **SciFact**: 1.4k expert-annotated scientific claims (*Wadden et al., 2020*).

## 🛠 Technologies Used
- **Python**: Core programming language.
- **BM25 Indexing**: For efficient retrieval of biomedical abstracts.
- [**Mixtral-8x22B-Instruct-v0.1**](https://huggingface.co/mistralai/Mixtral-8x22B-Instruct-v0.1): Language model for generating justifications.
- **PubMedBERT**: Classifier for claim evaluation.
- **Streamlit**: For building an interactive user interface.

The system is designed to work on both lightweight setups (Intel i7 CPU, 16GB RAM) and advanced environments with GPUs (e.g., NVIDIA Tesla T4), supporting complex tasks on large datasets.

## 🔬 Methodological Workflow
CER follows a structured workflow in three main phases:

1. **Evidence Retrieval**: Relevant abstracts are extracted from PubMed using a BM25 retrieval engine.
2. **Justification Generation**: The LLM generates explanations based on the retrieved abstracts.
3. **Claim Classification**: The classifier evaluates each claim as true, false, or "not enough evidence."

![Methodology](./Methodology.png)

## 🌟 Key Features
- **Zero-Shot and Fine-Tuned Classification**: Provides reliable fact-checking without the need for extensive task-specific labeled data.
- **Robustness Across Datasets**: Fine-tuning enhances model performance, even when the training and test sets differ.
- **Efficient Retrieval**: Leverages the Sparse Retriever for quick and accurate evidence extraction from PubMed.
- **Transparency**: Generates justifications to explain the classification of each claim, ensuring transparency and interpretability.

## 🚀 Getting Started
Follow these steps to use the CER system demo:

### Prerequisites
- **Python 3.9+**
- Required libraries: Install with the command:
  ```bash
  pip install -r requirements.txt
  ```

### Running the Application
1. **Clone the repository**:
    ```bash
    git clone https://github.com/picuslab/CER-Fact-Checking.git
    cd CER-Fact-Checking
    ```
2. **Create a virtual environment**:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```
3. **Run the Streamlit application**:
    ```bash
    streamlit run app.py
    ```
    Open your browser and go to `http://localhost:8501` to interact with the application.

### Submitting Claims
Enter a biomedical claim, for example:
```
"Vitamin D reduces the risk of osteoporosis."
```
Observe the process of evidence retrieval, justification generation, and classification.

## 📈 Conclusions
CER demonstrates how fact-checking using LLMs and evidence retrieval techniques can improve the reliability of medical information. Fine-tuning LLMs proves to be a powerful strategy for enhancing accuracy in fact-checking, even across different datasets. The ability to separate prediction from explanation ensures transparency and reduces bias.

## ⚖ Ethical Considerations
**CER** is a decision-support tool, not a substitute for professional medical advice. All recommendations must be validated by authorized healthcare providers. This demo uses anonymized data for illustrative purposes.

## 🙏 Acknowledgments
Special thanks to the dataset creators, library developers, and the research team for their contributions to this project.

👨‍💻 This project was developed by Antonio Romano, Giuseppe Riccio, Marco Postiglione, and Vincenzo Moscato.
