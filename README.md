# Ultimate Agentic AI for Enterprise Agentic Solutions

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)

## Overview

This project utilizes various Python libraries for natural language processing, machine learning, and vector search capabilities. It combines transformer-based models with efficient similarity search algorithms to process and analyze text data.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
- [Project Structure](#project-structure)
- [Running the Code](#running-the-code)
- [Dependencies](#dependencies)
- [Testing](#testing)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [Contact](#contact)

## Prerequisites

- Python 3.9 or higher
- pip (Python package installer)
- Git
- Virtual environment tool (recommended)
- 8GB+ RAM recommended for running larger models

## Setup Instructions

### Manual Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/<your_username>/enterprise-agentic-ai.git
   cd enterprise-agentic-ai
   ```

2. **Create and activate a virtual environment**:

   For macOS/Linux:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

   For Windows:
   ```bash
   python3 -m venv .venv
   .venv\Scripts\activate
   ```

   > Note: If you need to recreate your virtual environment, remove the existing one first with `rm -rf .venv` (macOS/Linux) or `rmdir /s /q .venv` (Windows).

3. **Update pip and install dependencies**:
   ```bash
   pip install --upgrade pip setuptools wheel
   ```

4. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Project Structure

- `src/chapters/` - Contains individual chapter code implementations

## Running the Code

### Running Individual Chapters

Navigate to a chapter folder and execute:

```bash
cd src/chapters/ch01
python ch1_first_agent.py
```

**NOTE:** Three chapters (ch02, ch09 and ch10) are theoretical and don't have any code.

## Package Information

This project relies on the following packages:

| Package               | Description                                                      | Usage                                          |
|-----------------------|------------------------------------------------------------------|------------------------------------------------|
| tiktoken              | OpenAI's tokenizer for text tokenization                         | Text encoding for LLM input                    |
| ag2             | Framework for building autonomous AI agents                      | Creating agent-based systems                   |
| transformers          | Hugging Face's NLP library                                         | Working with state-of-the-art language models  |
| sentence-transformers | Specialized transformers for sentence embeddings                 | Creating semantic text embeddings              |
| scikit-learn          | Machine learning library                                           | Classical ML algorithms and utilities          |
| rank-bm25             | BM25 ranking algorithm implementation                              | Information retrieval and document ranking     |
| together              | Client for Together AI's language model API                        | Accessing Together AI's LLM services             |
| faiss-cpu             | Facebook AI Similarity Search (CPU version)                        | Efficient vector similarity search             |
| networkx              | Network and graph analysis library                                 | Creating and analyzing complex networks        |
| numpy                 | Numerical computing foundation                                      | Array operations and numerical computations      |
| pandas                | Data analysis and manipulation                                      | Dataframe operations and data processing         |

## Troubleshooting

### Common Issues

1. **PyTorch Dependency Errors**
   - If you see an error like:
     ```
     ERROR: Cannot install -r requirements.txt (line X) because these package versions have conflicting dependencies.
     The conflict is caused by: sentence-transformers X.X.X depends on torch>=1.11.0
     ```
   - **Solution:**
     - Ensure you have Python 3.9+ and PyTorch separately before other dependencies:
       ```bash
       # For CPU only
       pip install torch>=1.11.0
       
       # For CUDA support (replace XX with your CUDA version, e.g. 11.8)
       pip install torch>=1.11.0 --index-url https://download.pytorch.org/whl/cuXX
       
       # Then install the rest
       pip install -r requirements.txt
       ```
     - Alternatively, update your requirements.txt to include torch explicitly before sentence-transformers.

2. **CUDA/GPU Issues**:
   - If experiencing CUDA errors, ensure you have compatible drivers installed.
   - Try setting: `export CUDA_VISIBLE_DEVICES=""` to force CPU mode.

3. **Import Errors**:
   - Verify that your virtual environment is activated.
   - Check that all dependencies are installed using `pip list`.

4. **Memory Issues**:
   - For "out of memory" errors, try reducing batch sizes in configuration.
   - Close other memory-intensive applications.
   - Use smaller model variants, implement gradient checkpointing, or reduce batch sizes.

5. **FAISS Installation Problems**:
   - On some systems, you may need to install additional dependencies:
     ```bash
     sudo apt-get install libomp-dev
     ```

6. **Version Conflicts**:
   - If you encounter compatibility issues, try creating a fresh environment.

## Best Practices

1. **Security**
   - Never commit API keys to version control
   - Use environment variables or secure vaults

2. **Performance**
   - Batch process data when possible
   - Cache embeddings for frequently used data
   - Use quantized models for deployment

3. **Updates**
   - Regularly check for security updates:
     ```bash
     pip list --outdated
     ```
## Contributing

We welcome contributions to improve the project!

1. Fork the repository.
2. Create a feature branch (e.g., `git checkout -b feature/amazing-feature`).
3. Make your changes, ensuring you include tests with your changes.
4. Commit your changes (e.g., `git commit -m 'Add amazing feature'`).
5. Push to your branch (`git push origin feature/amazing-feature`).
6. Open a Pull Request.

Please ensure your code adheres to our style guidelines and includes appropriate tests.

## Contact

- Project Maintainer: [<your_name>](mailto:your.email@example.com)
- Project Homepage: [GitHub Repository](https://github.com/<your_username>/enterprise-agentic-ai)

## Acknowledgments

- Thanks to all contributors and the open-source community.
- Special thanks to the authors of libraries and tools used in this project.
