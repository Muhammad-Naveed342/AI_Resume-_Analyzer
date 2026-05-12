# 🚀 AI Resume Analyzer 2025

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-Modern%20API-009688.svg)](https://fastapi.tiangolo.com/)
[![Google Drive](https://img.shields.io/badge/Google%20Drive-Integration-4285F4.svg)](https://developers.google.com/drive)
[![AI Powered](https://img.shields.io/badge/AI-GPT--4o/5-orange.svg)](https://openai.com/)

An advanced, asynchronous recruitment automation pipeline that transforms manual screening into a streamlined AI-driven workflow. It seamlessly integrates Google Drive, high-fidelity AI OCR, and intelligent candidate matching to deliver actionable insights directly to Google Sheets.

---

## 🌟 Key Features

-   **🔄 Automated Drive Synchronization:** Recursively scans Google Drive for new resumes and Job Descriptions (JDs).
-   **👁️ High-Fidelity AI OCR:** Uses GPT-4o Vision to convert PDFs and documents into clean, structured Markdown text.
-   **🧠 Intelligent Candidate Matching:** Automatically ranks candidates against specific job requirements using advanced AI scoring.
-   **📊 Dynamic Google Sheets Integration:** Proactively creates and updates dedicated Google Sheets for every job position.
-   **🌐 Real-time Control Center:** Interactive FastAPI-powered dashboard for manual triggers, scheduling, and live progress tracking.
-   **⚡ Asynchronous Processing:** Built with `asyncio` for high-concurrency handling of multiple files and folders.
-   **🎨 Customizable AI Prompts:** Fine-tune extraction and scoring logic using YAML-based prompt templates.
-   **🛡️ Smart Tracking:** Robust marker-based system ensures no duplicate processing and seamless recovery from interruptions.
-   **🐳 Docker Ready:** Fully containerized for easy deployment and consistent environments.

---

## 🏗️ System Architecture

The project follows a modular, service-oriented architecture:

-   **`core/`**: Configuration management (`config.py`), global status tracking, and logging utilities.
-   **`engines/`**: The AI core.
    -   `GPT5OCREngine`: Handles document-to-markdown conversion.
    -   `GPT5ParserEngine`: Extracts structured JSON from resumes (Skills, Experience, Education).
    -   `GPT5JDParserEngine`: Distills job descriptions into key requirements.
    -   `GPT5ScoringEngine`: Computes the match percentage and generates summaries.
-   **`prompts/`**: Externalized YAML templates for prompt engineering, allowing easy logic updates without code changes.
-   **`services/`**: Secure integration with Google Drive and Google Sheets APIs.
-   **`frontend/`**: Modern, responsive UI for system monitoring and control.
-   **`scripts/`**: Setup utilities for OAuth authentication and environment configuration.

---

## 🛠️ Technology Stack

| Category | Tools |
| :--- | :--- |
| **Language** | Python 3.10+ |
| **Backend** | FastAPI, Uvicorn |
| **Async Support** | Asyncio |
| **Cloud Integration** | Google Drive API, Google Sheets API |
| **AI Models** | OpenAI GPT-4o / Vision |
| **Frontend** | HTML5, CSS3 (Vanilla), JavaScript |
| **Environment** | UV Package Manager, Docker, Docker Compose |

---

## 🚀 Getting Started

### 1. Prerequisites
- Python 3.10 or higher.
- Google Cloud Project with Drive and Sheets APIs enabled.
- OpenAI API Key.

### 2. Installation

Clone the repository and install dependencies using `uv` (recommended) or `pip`:

```bash
# Using UV (Recommended)
uv sync

# Using Pip
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Configuration

1.  **Environment Variables:** Create a `.env` file in the root directory:
    ```env
    OPENAI_API_KEY=your_openai_key
    GOOGLE_DRIVE_FOLDER_ID=your_root_folder_id
    GOOGLE_SERVICE_ACCOUNT_FILE=credential.json
    ```
2.  **Google Credentials:**
    - Place your Service Account `credential.json` in the root folder.
    - Place your OAuth `oauth_client.json` in the `scripts/` folder.
    - Run the OAuth setup:
      ```bash
      python scripts/setup_oauth.py
      ```

---

## 🖥️ Usage

### Running the API Server
Start the backend and UI:
```bash
python api_server.py
```
Access the dashboard at: `http://localhost:5000`

### Interactive Dashboard Features:
-   **Manual Run:** Trigger the full pipeline across all folders.
-   **Scheduler:** Enable background polling (e.g., every 15 minutes) to keep results updated.
-   **Live Progress:** Monitor OCR status, parsing, and scoring in real-time.
-   **Direct Links:** Quick access to the root Google Drive folder.

### Docker Deployment
```bash
docker-compose up --build
```

---

## 🧪 Testing

The project includes a comprehensive test suite for AI engines:
```bash
pytest
```
*Extracted test results and AI logs are stored in the `tests/` and `logs/` directories.*

---

## 📁 Project Structure

```text
.
├── core/                # System configuration & status management
├── engines/             # AI processing logic (OCR, Parser, Scoring)
├── services/            # Google Cloud API integrations
├── frontend/            # Web dashboard (UI.html)
├── scripts/             # Setup and utility scripts
├── tests/               # Automated test suites
├── downloads/           # Local cache & processing markers
├── api_server.py        # FastAPI entry point
├── main_async.py        # Core pipeline logic
└── Dockerfile           # Container configuration
```

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---
*Developed with ❤️ by Muhammad Naveed*

https://www.youtube.com/watch?v=fwkMtMeErvc

# Source Code present in Private Repo 
