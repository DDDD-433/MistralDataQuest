# SQLquest – AI-Powered Data Storytelling

SQLquest converts plain-English questions into SQL queries, runs them against your database, and returns narrative insights alongside interactive visualizations — all powered by [Mistral AI](https://mistral.ai/).

## Features

- **Natural language → SQL** – ask questions in plain English; Mistral generates the query
- **Editable SQL** – review and tweak the AI-generated query before it executes
- **Narrative insights** – get a human-readable explanation of the results (formal or casual tone)
- **Auto-visualizations** – bar charts, pie charts, time-series lines, scatter plots, and more
- **Query history** – every successful question is saved in the sidebar for one-click replay
- **CSV export** – download any result set as a CSV file with a single click
- **Flexible database support** – SQLite (default + file upload), PostgreSQL, and MySQL
- **Bring your own API key** – use the built-in key or supply your own Mistral API key

## Quick Start

### Prerequisites

- Python 3.11+
- A [Mistral API key](https://console.mistral.ai/)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/DDDD-433/MistralDataQuest.git
cd MistralDataQuest

# 2. Create and activate a virtual environment (optional but recommended)
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -e .
```

### Running the app

```bash
# Set your Mistral API key (or enter it in the sidebar at runtime)
export MISTRAL_API_KEY="your_key_here"

streamlit run app.py
```

The app will open at `http://localhost:8501`.

### Using a custom database

| Option | How |
|---|---|
| **Default SQLite** | Built-in sample data (employees, products, sales) – no setup needed |
| **Upload SQLite** | Use the sidebar to upload any `.db` / `.sqlite` file |
| **PostgreSQL** | Set `DATABASE_URL` env var *or* enter credentials in the sidebar |
| **MySQL** | Enter host/port/credentials in the sidebar |

## Project Structure

```
├── app.py              # Streamlit UI
├── database.py         # Database abstraction (SQLite / PostgreSQL / MySQL)
├── mistral_service.py  # Mistral API integration (SQL generation + narrative)
├── data_analysis.py    # Statistical analysis of query results
├── visualization.py    # Plotly chart generation
├── data/               # Default SQLite database (auto-created)
├── uploaded_db/        # Uploaded SQLite files (auto-created)
└── pyproject.toml      # Python project metadata & dependencies
```

## Environment Variables

| Variable | Description |
|---|---|
| `MISTRAL_API_KEY` | Default Mistral API key used by the app |
| `DATABASE_URL` | PostgreSQL connection URL (optional) |

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Commit your changes and push
4. Open a Pull Request

## License

MIT
