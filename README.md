# knowledgeLock

Local knowledge-base pipeline for scraping locksport forum content, indexing the resulting Markdown with PageIndex, and querying it from the command line.

## Setup

Clone the repository and enter it:

```bash
git clone https://github.com/kaa-serpent/knowledgeLock.git
cd knowledgeLock
```

Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

On Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Create a local environment file and fill in the required values:

```bash
cp .env.example .env
```

On Windows PowerShell:

```powershell
Copy-Item .env.example .env
```

Fill in your locksport.fr credentials in `.env`. If you are using Ollama's
defaults, leave the Ollama values unchanged.

Install and start Ollama before indexing or querying:

```bash
ollama serve
```

In a separate terminal, pull the configured model:

```bash
ollama pull gemma4
```

## Usage

Scrape the configured forum:

```bash
python scrape.py --site locksport_fr
```

Index scraped Markdown files:

```bash
python index.py
```

Query the local knowledge base:

```bash
python query.py "your question"
```
