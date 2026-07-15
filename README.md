# AI ChatBot 🤖

A simple full-stack AI chatbot powered by **Google's Gemini API**, built with a **FastAPI** backend and a lightweight vanilla JS frontend. The backend keeps the API key secure on the server side, while maintaining per-session chat history.

## Features

- 💬 Real-time conversational chat with Gemini
- 🔒 API key kept secure on the backend (never exposed to the browser)
- 🧠 Session-based chat history (context is remembered during a session)
- 🎨 Clean, minimal dark-themed chat UI
- ⚡ Lightweight — no build tools or frameworks required for the frontend

## Tech Stack

| Layer      | Technology                          |
|------------|--------------------------------------|
| Backend    | Python, FastAPI, Uvicorn              |
| AI Model   | Google Gemini API (`google-generativeai`) |
| Frontend   | HTML, CSS, Vanilla JavaScript         |
| Config     | python-dotenv                        |

## Project Structure

```
AI-ChatBot/
├── backend/
│   ├── main.py            # FastAPI server + Gemini integration
│   ├── requirements.txt   # Python dependencies
│   ├── .env               # API key (not committed to git)
│   └── .gitignore
└── frontend/
    └── index.html         # Chat UI
```

## Setup & Installation

### Prerequisites
- Python 3.9+
- A Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey)

### 1. Clone the repository
```bash
git clone https://github.com/sachinmishra21/AI-ChatBot.git
cd AI-ChatBot/backend
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Configure your API key
Create a `.env` file inside the `backend` folder:
```
GEMINI_API_KEY=your_api_key_here
```

### 4. Run the backend server
```bash
uvicorn main:app --reload --port 8000
```
The API will be running at `http://localhost:8000`.

### 5. Open the frontend
Open `frontend/index.html` directly in your browser (make sure the backend is running).

## API Endpoints

| Method | Endpoint            | Description                     |
|--------|----------------------|----------------------------------|
| GET    | `/`                  | Health check                    |
| POST   | `/chat`              | Send a message, get AI reply    |
| DELETE | `/chat/{session_id}` | Clear a session's chat history  |

**Example request:**
```json
POST /chat
{
  "message": "Hello!",
  "session_id": "abc123"
}
```

**Example response:**
```json
{
  "reply": "Hi there! How can I help you today?"
}
```

## Future Improvements

- [ ] Persistent chat history using a database
- [ ] User authentication
- [ ] Streaming responses (typing effect)
- [ ] Deploy backend (Render/Railway) and frontend (Vercel/Netlify)

## Author

**Sachin Mishra**


## License

This project is open source and available under the [MIT License](LICENSE).
