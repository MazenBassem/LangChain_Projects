# LangChain Projects

A collection of practical **LangChain** projects built in Jupyter notebooks, focused on LLM workflows such as prompting, document ingestion, retrieval, and question answering.

> Repository: [MazenBassem/LangChain_Projects](https://github.com/MazenBassem/LangChain_Projects)

---

## 📌 Overview

This repository contains notebook-based experiments and mini-projects using LangChain.  
It is designed for learning and rapid prototyping.

Current repo language composition:
- **Jupyter Notebook (100%)**

---

## 🗂️ Project Structure

- `*.ipynb` notebooks: main project implementations and experiments
- (Optional) `data/`: local input files for testing retrieval / QA pipelines
- (Optional) `.env`: API keys and environment variables (never commit secrets)

---

## ⚙️ Requirements

Install dependencies before running notebooks:

```bash
pip install -U langchain langchain-community langchain-openai openai pypdf faiss-cpu chromadb tiktoken python-dotenv
```

> You may not need all packages for every notebook. Install only what your notebook imports.

---

## 🔑 Environment Variables

Set API keys as environment variables (recommended), for example in a `.env` file:

```env
OPENAI_API_KEY=your_key_here
```

Then in notebook:

```python
from dotenv import load_dotenv
load_dotenv()
```

---

## ▶️ Running Locally (Jupyter)

1. Clone the repository
2. Create/activate virtual environment
3. Install requirements
4. Open notebooks with Jupyter
5. Run cells top-to-bottom

---

## 🧪 Running on Kaggle (Important)

If you run notebooks on **Kaggle**, local file paths like `./data/file.pdf` may fail unless files are uploaded correctly.

### Option A — Upload files as a Kaggle Dataset (recommended)
1. Create a dataset in Kaggle and upload your files.
2. Attach that dataset to your notebook (**Add data**).
3. Files become available under:
   `/kaggle/input/<dataset-name>/`

Example:
```python
file_path = "/kaggle/input/my-dataset-name/my_file.pdf"
```

### Option B — Manually upload files in notebook session
1. In Kaggle notebook, use the right sidebar **Data** panel.
2. Upload files directly.
3. Read files from working directory if needed:
   `/kaggle/working/` (or uploaded path shown by Kaggle UI)

---

## 🔁 What to Replace in Notebook Code

When moving between local and Kaggle, replace these parts:

1. **File paths**
   - Replace local paths:
     - `./data/...`
     - `C:/...`
   - With Kaggle paths:
     - `/kaggle/input/<dataset-name>/...`

2. **Environment / keys loading**
   - If `.env` is not available in Kaggle, use:
     - Kaggle **Secrets** (preferred), or
     - `os.environ["OPENAI_API_KEY"] = "..."` (not recommended for shared notebooks)

3. **Output directories**
   - Use `/kaggle/working/` for generated files in Kaggle:
   ```python
   output_path = "/kaggle/working/results.json"
   ```

4. **Model/provider-specific setup**
   - Replace model names or providers if your environment differs:
   ```python
   model_name = "gpt-4o-mini"  # example, change as needed
   ```

---

## 📝 Suggested Notebook Markdown Sections

For consistency, add these Markdown sections to each notebook:

1. `# Project Title`
2. `## Objective`
3. `## Setup & Dependencies`
4. `## Data Source / Input Files`
5. `## Configuration (API Keys, Paths)`
6. `## Implementation`
7. `## Results`
8. `## Limitations`
9. `## Next Improvements`

---

## ✅ Best Practices

- Keep secrets out of notebooks and Git history.
- Use relative paths locally and clearly separated Kaggle paths.
- Add short explanations before each major code block.
- Keep outputs reproducible (fixed chunk size, deterministic settings where possible).

---

## 🤝 Contributing

Contributions and improvements are welcome:
1. Fork the repo
2. Create a feature branch
3. Commit changes
4. Open a pull request

---

## 📄 License

Add your preferred license (e.g., MIT) in a `LICENSE` file.
