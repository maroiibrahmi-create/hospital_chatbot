# Hospital Mohammed VI Chatbot

A beginner-friendly educational chatbot built with Python, Streamlit, and the Groq API. It answers administrative questions using `knowledge.json` and keeps conversation history in `st.session_state` for the current Streamlit session.

> **Important:** This is an unofficial educational prototype, not affiliated with the hospital. It is not for medical advice. The JSON file is a static research snapshot; confirm changeable information with the hospital.

## 1. Requirements

- Python 3.10 or newer
- Internet connection
- A Groq API key: <https://console.groq.com/keys>

## 2. Install

Open a terminal in this project folder and create a virtual environment:

### Windows (PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

If PowerShell blocks activation, use Command Prompt instead:

```bat
.venv\Scripts\activate.bat
python -m pip install -r requirements.txt
```

## 3. Configure the API key

Open `.env` and replace the placeholder with your own key:

```env
GROQ_API_KEY=put_your_groq_api_key_here
```

Keep this key private. Do not commit `.env` or share screenshots containing the key. The `.gitignore` file excludes it from Git.

## 4. Run the app

```bash
streamlit run app.py
```

Streamlit will print a local URL (usually `http://localhost:8501`) to open in your browser.

## 5. Features

- Uses `st.chat_message()` and `st.chat_input()`.
- Sends the JSON knowledge and current conversation to Groq.
- Remembers conversation turns in `st.session_state` during the current session.
- Includes a **Clear conversation** button.
- Handles missing keys, invalid JSON, and API/network errors.
- Uses the Groq model `openai/gpt-oss-120b`, listed in Groq's current model catalogue. Model access and free-tier limits can change, so check Groq's model documentation if the model is unavailable.

## Project files

- `app.py` — Streamlit interface and Groq API calls.
- `knowledge.json` — hospital knowledge, assistant persona, instructions, limitations, FAQs, and sources.
- `.env` — local API key configuration (placeholder included).
- `.gitignore` — excludes secrets and temporary files.
- `requirements.txt` — Python dependencies.

## Troubleshooting

- **Missing API key:** Check that `.env` is in the same folder as `app.py` and that the variable is named `GROQ_API_KEY`.
- **Model error:** Check the currently available Groq models and select a supported chat model in `app.py`.
- **Package error:** Run `python -m pip install -r requirements.txt` in the active virtual environment.
- **Knowledge file error:** Ensure `knowledge.json` is next to `app.py` and contains valid JSON.
