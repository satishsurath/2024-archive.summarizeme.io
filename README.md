# SummarizeMe.io

AI-powered text summarization made simple. Condense articles, web pages, and PDFs effortlessly. Save time and boost productivity with SummarizeMe.io

[**🔗 Try the live demo here! ➡️ https://SummarizeMe.io**](https://SummarizeMe.io)

## 🚧 Work in Progress 🚧

### ✅ Implemented Features:
- **Summarize Text, URLs and PDF files:** Easily summarize content from plain text, web pages or PDF files.
- **Share Summary:** We generate a unique 🌐 webpage for each of your summary so you can share it with others. 
- **Unlimited Token Support with Chunking:** No more token size limits! The chunking feature allows seamless summarization of any length of text or URL, providing a smooth and efficient experience.
- **Local SQLite File Storage:** Automatically save all files to a local SQLite file.
- **User Session Support:** for additional Security
- **Hash-Based Database Storage for Fast Retrieval:** Optimize the retrieval process by storing the text's hash in our database, allowing for quicker access to existing summaries and saving time.
- **Stats for Nerds:** Display additional statistics and raw JSON output.
- **Dark Mode Support:** Enhance your experience with our dark mode feature.

### 🔜 Upcoming Features:

- Add a Privacy Notice.
- Implement SPAM Protection.
- Integrate additional LLMs (e.g., Google-based models).

## 💻 Installation

1. Create and activate a [new Python virtual environment (venv) or a new conda environment.](/docs/new-virtual-python-env.md)

   
2. Clone this repository:
   ```shell
   git clone git@github.com:satishsurath/SummarizeMe.io.git
    ```

3. Set up Ollama and point the app to your local server (no OpenAI API key is required).
```shell
export OLLAMA_BASE_URL=http://localhost:11434
export OLLAMA_MODEL_PREFERENCE="llama3.1,llama3,qwen2,mistral,gemma,phi3,phi"
# Optional (if you want to pin): export OLLAMA_MODEL=llama3.1
export OLLAMA_REQUEST_TIMEOUT=120
```
4. If you want to persist these values, copy `sample.env` to `.env` and adjust as needed. Set `SQLALCHEMY_DATABASE_URI` for PostgreSQL, for example:
   ```env
   SQLALCHEMY_DATABASE_URI=postgresql+psycopg2://<DB_USER>:<DB_PASSWORD>@<DB_HOST>:5432/<DB_NAME>
   ```
5. Install a model in Ollama (example: `ollama pull llama3.1`).
6. Configure your admin username and password for log access:
```shell
export summarizeMeUser=[YOUR ADMIN USERNAME HERE]
export summarizeMePassword=[YOUR ADMIN PASSWORD HERE]
``` 

7. Install all Python dependencies in your environment:
```shell
pip install -r requirements.txt
```
8. Initialize the Database 
```shell
flask db init
flask db migrate -m "entry_post table"
flask db upgrade
```
9. Congratulations! You are ready to run your Flask App!
```shell
flask run
```
