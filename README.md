# 📚 PDF Question Answering System using RAG

A Retrieval-Augmented Generation (RAG) based Question Answering System that allows users to ask questions about a PDF document and receive context-based answers using Large Language Models (LLMs).

The project uses **LangChain, NVIDIA AI, FastEmbed, and Qdrant** to retrieve relevant information from PDF documents and generate answers using an NVIDIA language model.

## 🚀 Features

- 📄 **PDF Loading:** Extracts text from PDF documents.
- ✂️ **Text Chunking:** Splits documents into smaller chunks for efficient retrieval.
- 🔢 **Text Embeddings:** Uses FastEmbed to convert text into vector representations.
- 🗄️ **Vector Database:** Stores and searches document embeddings using Qdrant.
- 🔍 **Semantic Search:** Retrieves relevant text chunks based on the user's question.
- 🤖 **AI-Powered Answers:** Generates answers using NVIDIA's LLM API.
- 💬 **Context-Based Responses:** Answers questions using the retrieved PDF content.
- 🐍 **Python-Based:** Built with Python and LangChain.

## 🛠️ Technologies Used

- Python
- LangChain
- NVIDIA AI Endpoints
- FastEmbed
- Qdrant Vector Database
- PyPDF
- python-dotenv

## ⚙️ How It Works

1. **Load PDF:** The system reads the PDF document using `PyPDFLoader`.
2. **Split Text:** The extracted text is divided into chunks using `RecursiveCharacterTextSplitter`.
3. **Generate Embeddings:** FastEmbed converts each chunk into a numerical vector.
4. **Store Vectors:** Qdrant stores the embeddings in an in-memory vector database.
5. **Retrieve Context:** The retriever finds the three most relevant chunks for a question.
6. **Generate Answer:** The NVIDIA language model generates an answer based on the retrieved context.
7. **Display Output:** The system displays the retrieved text and generated answer.

## 📂 Project Structure

```text
RAG-PDF-Question-Answering/
│
├── main1.py
├── requirements.txt
├── .env
├── .gitignore
│
└── document_loader/
    └── FILE.pdf
```

## 📋 Requirements

- Python 3.12 recommended
- NVIDIA API key
- pip package manager

## 🔧 Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Replace `YOUR_USERNAME` and `YOUR_REPOSITORY` with your GitHub username and repository name.

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the API key

Create a `.env` file in the project root directory:

```env
NVIDIA_API_KEY=your_nvidia_api_key
```

Replace the placeholder with your own valid NVIDIA API key.

**Security:** Never upload your `.env` file or expose your API key on GitHub.

### 5. Add your PDF document

Place your PDF file inside the `document_loader` directory and name it `FILE.pdf`, or update the PDF path in the Python script.

### 6. Run the application

```bash
python main1.py
```

## 💻 Example Usage

Example question:

```text
What is machine learning?
```

The system retrieves relevant content from the PDF and sends it to the NVIDIA language model to generate an answer.

**Note:** The quality of the answer depends on the content of the uploaded PDF. If the required information is not present in the retrieved context, the system may respond that it does not know.

## 🧠 RAG Architecture

```text
PDF Document
     |
     v
PDF Text Extraction
     |
     v
Text Chunking
     |
     v
FastEmbed Embeddings
     |
     v
Qdrant Vector Database
     |
     v
User Question
     |
     v
Semantic Retrieval
     |
     v
Relevant Context + Question
     |
     v
NVIDIA Language Model
     |
     v
Generated Answer
```

## 🔐 Environment Variables

| Variable | Description |
|---|---|
| `NVIDIA_API_KEY` | API key used to access the NVIDIA language model |

## ⚠️ Important Notes

- The current implementation uses an in-memory Qdrant database. Document embeddings are recreated when the script runs again.
- The PDF must contain readable text for effective retrieval.
- The NVIDIA API requires a valid API key and access to the configured model.
- The current implementation is a command-line application, not a web interface.
- Do not commit API keys, virtual environments, or private documents to a public repository.

## 🔮 Future Improvements

- Support uploading multiple PDF files.
- Build a web interface using Streamlit or Flask.
- Add persistent vector storage.
- Display PDF page references with answers.
- Improve retrieval quality using reranking.
- Add conversation history and chat memory.

## 👨‍💻 Author

"Hemant Kumar"

LinkedIn: [https://www.linkedin.com/in/hemant-kumar-050a25359]

 
