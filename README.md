# 💬 ChatGPT Clone App

🚀 ChatGPT Clone – An AI-Powered Chatbot with Context Memory, Weather Intelligence, and Seamless User Experience

This is a full-stack **ChatGPT Clone** web application built using **FastAPI** for the backend and **Streamlit** for the frontend. It integrates OpenAI's `gpt-3.5-turbo` model and supports chat history, contextual memory, user authentication, and weather information via OpenWeatherMap API.

---

## 🚀 Features

- 🔐 **User Registration & Login**
- 💡 **Chat with AI (GPT-3.5-Turbo)**
- 💬 **Session-based Chat History stored in PostgreSQL**
- 🧠 **Contextual Memory** (remembers previous messages)
- 🌦️ **Weather Info** via city name
- 🖥️ **Modern UI** using Streamlit
- 🐘 **PostgreSQL** database integration

---

## 🛠️ Tech Stack

| Layer       | Tools / Frameworks          |
|-------------|-----------------------------|
| Frontend    | Streamlit                   |
| Backend     | FastAPI                     |
| AI Model    | OpenAI GPT-3.5-Turbo        |
| Database    | PostgreSQL, SQLAlchemy ORM  |
| Auth        | Custom Header Token (`X-Username`) |
| Weather API | OpenWeatherMap              |

---

## 📦 Project Structure

```bash
chatgpt-clone/
│
├── app/
│   ├── models/            # SQLAlchemy Models
│   ├── routes/            # FastAPI Routes (chat, auth)
│   ├── services/          # OpenAI & Weather integrations
│   ├── schemas.py         # Pydantic Schemas
│   ├── database.py        # DB connection
│   ├── config.py          # App Settings
│   └── main.py            # FastAPI App
│
├── frontend/
│   └── streamlit_app.py   # Streamlit UI
│
├── requirements.txt       # All dependencies
├── README.md              # Project README
└── .env                   # API keys and secrets (not committed)
````

---

## 🔐 Environment Variables (`.env`)

Create a `.env` file in the root with the following:

```env
OPENAI_API_KEY=your_openai_api_key
WEATHER_API_KEY=your_openweather_api_key
DATABASE_URL=postgresql://username:password@localhost:5432/Chatgpt
```

---

## 📦 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/chatgpt-clone.git
cd chatgpt-clone
```

### 2. Create Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate  # Windows: venv\\Scripts\\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run Backend (FastAPI)

```bash
cd app
uvicorn main:app --reload
```

Open: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

### 5. Run Frontend (Streamlit)

```bash
cd ../frontend
streamlit run streamlit_app.py
```

---

## 📝 To Do

* ✅ Add Chat History
* ✅ Contextual memory with OpenAI
* ✅ Weather integration
* 🔄 Token-based auth (future)
* 🌐 Deployment with Docker or Render

---


## 📄 License

This project is licensed under the MIT License.

```
