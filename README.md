# Retrieval-Augmented Generation (RAG) Model

## Overview

This repository contains a **Retrieval-Augmented Generation (RAG) model** implementation that combines a retrieval system with a generative language model to answer questions based on a specific corpus. The model retrieves relevant documents from a knowledge base and uses them to generate accurate, context-aware answers.

This implementation is suitable for tasks such as:

* Question answering over custom datasets
* Biomedical or domain-specific QA (e.g., PubMedQA)
* Knowledge-based dialogue systems
* Any scenario requiring document retrieval before generation

---

## Features

* **Vector Store Retrieval** using embeddings (FAISS-based)
* **Custom Document Chunking** for better context handling
* **Integration with Generative Models** for high-quality answer generation
* **CPU/GPU Support** for scalable inference
* **Easy Evaluation** with metrics like Accuracy, Precision, Recall, and F1-score

---



## Installation

1. Clone the repository:

```bash
git clone https://github.com/rohanreddy-marri/RAG-Model.git
cd RAG-Model
```

2. Create a virtual environment:

```bash
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Usage

### 1. Prepare your dataset

* Place your dataset in `data/` folder.
* Ensure it contains a `context` column (documents) and an `answer` column (labels for QA tasks).

### 2. Build the vector store

```bash
python src/build_vectorstore.py --data_path data/your_dataset.csv --embed_model all-MiniLM-L6-v2
```

### 3. Run retrieval + generation

```python
from src.rag_inference import RAGPipeline

rag = RAGPipeline(vectorstore_path='embeddings/vectorstore.faiss')
question = "What is the function of the hippocampus?"
answer = rag.answer(question)
print(answer)
```

### 4. Evaluate model

* Evaluation scripts are provided in `evaluation` to compute metrics like Accuracy, Precision, Recall, and F1-score.


---

## Example Output

| Question     | Retrieved Context                        | Model Answer                                     |
| ------------ | ---------------------------------------- | ------------------------------------------------ |
| What is RAG? | RAG combines retrieval and generation... | RAG stands for Retrieval-Augmented Generation... |

---

## References

* Chung et al., 2022 – Scaling Laws for LLMs
* Jin et al., 2019 – Biomedical QA datasets
* Karpukhin et al., 2020 – Dense Passage Retrieval
* Khattab & Zaharia, 2020 – ColBERT: Efficient Retrieval
* Lewis et al., 2020 – RAG: Retrieval-Augmented Generation
* Muennighoff et al., 2022 – Sentence Transformers
* Reimers & Gurevych, 2019 – Sentence-BERT

---

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contact

Created by **Rohan Reddy Marri & Devakinandan pentyala** – [rohanreddy1408@gmail.com](mailto:your.email@example.com)

GitHub: [https://github.com/rohanreddy-marri](https://github.com/yourusername)
