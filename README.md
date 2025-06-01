## 🛠️ Engineering Standards Dataset Generator

This project extracts and structures content from the [Whangarei District Council 2022 Engineering Standards PDF](https://www.wdc.govt.nz/files/assets/public/v/2/documents/council/standards-guidelines/ees-2022/2022-engineering-standards-with-title-pages.pdf) into a training and testing dataset suitable for fine-tuning large language models (LLMs) such as **Qwen3:0.6B**.

---

### 📚 Project Goals

* Parse the Table of Contents (ToC) into a **hierarchical tree structure** for context preservation.
* Extract **clean section text** from the PDF according to ToC sections.
* Create structured datasets with metadata for each section.
* Generate **instruction-following prompt-completion pairs** for LLM fine-tuning.
* Export a fine-tuning ready dataset in `JSONL` format.

---

### 📁 Folder Structure

```
.
├── data/                  # (gitignored) PDF and raw extracted text
├── output/                # Final dataset files (.jsonl)
├── notebooks/             # Jupyter notebooks for extraction & generation
├── scripts/               # Python scripts for parsing and formatting
├── .gitignore
├── README.md
├── requirements.txt
└── environment.yml        # Optional conda environment file
```

---

### ✅ Features

* 📖 PDF ToC parsing using `PyMuPDF`
* 🧠 Hierarchical context-aware data structure
* 🔍 Clean extraction of section text
* ✍️ Prompt-completion generation (with optional GPT API or LLM assistance)
* 📂 Dataset splitting into `train.jsonl` and `test.jsonl`

---

### 🧪 Example Output Format

```json
{
  "prompt": "Part A > A1 Introduction\n\nSummarize the key objectives of this section.",
  "completion": "The key objectives of A1 Introduction are to outline the scope, applicability, and background of the engineering standards."
}
```

---

### 🔧 Setup Instructions

#### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/engineering-standards-dataset.git
cd engineering-standards-dataset
```

#### 2. Set Up a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt
```

#### 3. Run Jupyter Lab/Notebook

```bash
jupyter lab
```

---

### 📦 Dependencies

Add these to `requirements.txt` as needed:

```txt
PyMuPDF
pdfplumber
jupyterlab
pandas
scikit-learn
openai  # optional, if using GPT-4 for generation
```

---

### 🧠 Fine-Tuning Qwen

Once the dataset is generated, it can be used to fine-tune Qwen3:0.6B or similar LLMs with instruction-tuning capabilities using frameworks like:

* [Transformers (Hugging Face)](https://huggingface.co/docs/transformers)
* [FlagAI (for Qwen)](https://github.com/FlagOpen/FlagAI)
* [LoRA adapters](https://github.com/microsoft/LoRA)

---

### 📌 License

This project is for educational and research purposes only. The original document is publicly available from the Whangarei District Council website.

---

### 🤝 Contributions

Pull requests and suggestions are welcome. Feel free to open an issue for bugs or feature requests!

---
