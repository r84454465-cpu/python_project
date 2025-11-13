# python_project

# FastAPI + Google Gemini 2.5 Flash Backend


## Features

### `POST /login/`
- Validates username & password
- Returns a Bearer token

### `POST /prompt/`
- Requires token
- Sends prompt to Gemini 2.5 Flash
- Returns generated AI text
- Saves prompt + response to history.json

### `GET /history/`
- Requires token
- Returns complete conversation history


##  Project Structure

```
fastapi-llama-replicate/
├─ app/
│  ├─ main.py
│  ├─ routes.py
│  ├─ auth.py
│  ├─ schemas.py
│  ├─ storage.py
│  ├─ services/
│  │   └─ replicate_client.py   # Gemini client inside this file
├─ history.json
├─ requirements.txt
└─ README.md
```

---

## Setup Instructions

### Create Virtual Environment

python -m venv env


### Activate

Windows:

env\Scripts\activate


###  Install Dependencies

pip install -r requirements.txt


##  Configure Gemini API Key

Get your API key from:

https://aistudio.google.com/app/apikey

Then update:

app/services/replicate_client.py

Replace:

GEMINI_API_KEY = "[paste gemini key here]"


## Run Server

uvicorn app.main:app --reload --port 8000


## API Examples

###  Login

POST /login/
{
  "username": "ayan",
  "password": "ayan123"
}


### Prompt
Headers:

Authorization: Bearer ayan-123

Body:

{
  "prompt": "what is kolkata ?"
}


### 3️⃣ History

GET /history/
Authorization: Bearer ayan-123


##  Demo Users

| Username | Password   | Token             |
|----------|------------|--------------------|
| ayan     | ayan123    | ayan-123    |


##  Technologies

- FastAPI  
- Uvicorn  
- Google Gemini API  
- Pydantic  
- Python 3.10+  
- JSON storage (no database)


## Summary

This backend is:
- Simple  
- Fast  
- Clean  
- Fully functional  
# python_project
