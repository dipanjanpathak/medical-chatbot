

# Medical Chatbot with LangChain and HuggingFace

A conversational AI assistant designed to answer medical questions using the GALE Encyclopedia of Medicine as a knowledge base. Built with LangChain, HuggingFace models, and FAISS for efficient document retrieval.

## Features

- **Document-based Q&A**: Answers questions using the GALE Encyclopedia of Medicine (2nd Edition)
- **Efficient Retrieval**: FAISS vectorstore for fast similarity search
- **Modern Stack**: Powered by LangChain and HuggingFace models
- **Web Interface**: Streamlit-based UI for easy interaction

## Prerequisites

- Python 3.8+
- Pipenv (for virtual environment management)
- HuggingFace account (for accessing models)
- [HuggingFace Access Token](https://huggingface.co/settings/tokens)

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/medical-chatbot.git
   cd medical-chatbot
   ```

2. **Set up environment with Pipenv**:
   ```bash
   pipenv install
   ```

3. **Set up HuggingFace token**:
   Create a `.env` file in the root directory with:
   ```env
   HUGGINGFACEHUB_API_TOKEN=your_token_here
   ```

## Usage

1. **Create vectorstore** (first-time setup):
   ```bash
   pipenv run python create_memory_for_llm.py
   ```

2. **Run the chatbot**:
   ```bash
   pipenv run python medibot.py
   ```

3. **Web Interface (Streamlit)**:
   ```bash
   pipenv run streamlit run app.py
   ```

## Project Structure

```
medical-chatbot/
├── data/                   # Medical documents
│   └── The_GALE_ENCYCLOPEDIA_of_MEDICINE_SECOND.pdf
├── vectorstore/            # FAISS vector database
├── create_memory_for_llm.py # Document processing script
├── connect_memory_with_llm.py # Retrieval setup
├── medibot.py              # Main chatbot script
├── app.py                  # Streamlit web interface
├── Pipfile                 # Dependencies
├── Pipfile.lock
└── .env.example            # Environment variables template
```

## Configuration

Modify these parameters in `connect_memory_with_llm.py`:
- `model_name`: Change HuggingFace model
- `k`: Number of document chunks to retrieve
- `chunk_size`: Document processing parameters

## Troubleshooting

- **Large file handling**: If you encounter Git LFS issues:
  ```bash
  git lfs install
  git lfs track "*.pdf" "vectorstore/**"
  ```

- **Memory errors**: Reduce chunk size in `create_memory_for_llm.py`

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- GALE Encyclopedia of Medicine for the knowledge base
- HuggingFace for language models
- LangChain framework



## Key improvements I've made:
1. Added clear sections with consistent formatting
2. Included visual hierarchy with headings
3. Added project structure visualization
4. Included troubleshooting section
5. Added license and acknowledgments
6. Made setup instructions more comprehensive
7. Added configuration notes
8. Included both CLI and Streamlit usage options
