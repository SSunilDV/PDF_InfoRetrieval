# PDF Retrieval and Question Answering with LangChain

This project utilizes LangChain, a library for natural language processing tasks, to facilitate PDF document retrieval and question answering. The pipeline involves extracting text from PDF documents, embedding them into a vector database, and using an AI language model for answering user queries based on the retrieved documents.

## Features

- **PDF Loading and Text Extraction**: Utilizes `PyPDFLoader` to load and split text from PDF documents.
- **Text Splitting and Embedding**: Segments the extracted text into manageable chunks and embeds them using `OllamaEmbeddings` model.
- **Vector Database Management**: Uses `Chroma` to create and manage a vector database (`vector_db`) for efficient document retrieval.
- **Question Generation and Answering**: Generates alternative versions of user questions to enhance document retrieval using `MultiQueryRetriever` and an AI language model (`ChatOllama`).
- **Pipeline for Question Answering**: Sets up a processing pipeline (`chain`) that integrates document retrieval, question prompts, and answer extraction.
- **Clean-up**: Includes functionality to delete collections (`local-rag`) from the vector database after use.

## Project :

PDF Loading and Text Extraction:
Used PyPDFLoader from langchain_community.document_loaders to load and split pages from a local PDF file (WEF_The_Global_Cooperation_Barometer_2024.pdf). Also tested on MONOPOLY game instructions file.

Text Splitting and Embedding:
After loading the PDF pages, used RecursiveCharacterTextSplitter to split the text into chunks suitable for embedding.
Then, used Chroma to create a vector database (vector_db) from these text chunks, using embeddings from OllamaEmbeddings model named "nomic-embed-text".

Question Generation and Retrieval:
Defined a prompt template (QUERY_PROMPT) to generate alternative versions of a user's question, aimed at improving document retrieval from vector_db.
MultiQueryRetriever is used to integrate the vector database (vector_db) and an LLM (ChatOllama) to retrieve relevant documents based on the user's question.

Question Answering Pipeline:
set up a pipeline (chain) that takes the retrieved documents, prompts the LLM with a context and the user's question, and finally parses the output (StrOutputParser) to get the answer.

Cleaning Up:
At the end of your script, deleting the collection (local-rag) from vector_db, presumably to clean up after your operations.


## Requirements

- Python 3.6+
- LangChain library (install via `pip install langchain`)

## Installation

1. Clone the repository:

   ```
   git clone https://github.com/SSunilDV/PDF_InfoRetrieval..git
   cd your_repository
   ```

2. Install dependencies:

   ```
   pip install -r requirements.txt
   ```

3. Download necessary models or resources as specified in the code comments or documentation.

## Usage

1. Ensure you have a PDF file (`local_path`) ready for processing. Update `local_path` in the script if necessary.

2. Run the script (`pdf_retrieval.ipynb` or your preferred filename):

   ```
   python pdf_retrieval.py
   ```

3. Follow the prompts to interact with the system. Example:

   ```
   What are the 5 pillars of global cooperation?
   ```

4. View the generated answers based on the document retrieval and question answering pipeline.

## Examples

- Example questions:
  - "What are the challenges of climate change mitigation?"
  - "Discuss the impact of technology on education."
  - "Explain the economic implications of globalization."

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact

- **LinkedIn:** [Sunil Durga Venkat](https://www.linkedin.com/in/sunil-durga-venkat/)
- **Email:** [Gmail](mailto:sdvsurimalla@gmail.com), [Outlook](mailto:sxs6577@mavs.uta.edu)
- 
## Acknowledgments

- LangChain developers and contributors for their open-source contributions and support.

