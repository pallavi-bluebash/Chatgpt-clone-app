# 💬 ChatGPT Clone App

ChatGPT Clone – An AI-Powered Chatbot with Context Memory, Weather Intelligence, and Seamless User Experience

This is a full-stack **ChatGPT Clone** web application built using **FastAPI** for the backend and **Streamlit** for the frontend. It integrates OpenAI's `gpt-3.5-turbo` model and supports chat history, contextual memory, user authentication, and weather information via OpenWeatherMap API.

---

## Features

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

Follow these step-by-step instructions to run the ChatGPT Clone App locally:

---

### 🧰 Prerequisites

- Python 3.8 or above installed
- PostgreSQL installed and running
- Git installed
- OpenAI API Key and OpenWeatherMap API Key

---

### 📁 1. Clone the Repository

```bash
git clone https://github.com/yourusername/chatgpt-clone.git
cd chatgpt-clone
````

> Replace `yourusername` with your actual GitHub username.

---

### 🐘 2. Setup PostgreSQL Database

1. Open PostgreSQL CLI or PgAdmin
2. Create the database:

```sql
CREATE DATABASE Chatgpt;
```

3. (Optional) Create a user and grant privileges:

```sql
CREATE USER pallavi WITH PASSWORD 'yourpassword';
GRANT ALL PRIVILEGES ON DATABASE Chatgpt TO pallavi;
```

---

### 🔐 3. Create `.env` File

In the root of the project, create a `.env` file and add the following:

```env
OPENAI_API_KEY=your_openai_api_key
WEATHER_API_KEY=your_openweather_api_key
DATABASE_URL=postgresql://username:password@localhost:5432/Chatgpt
```

> Replace with your actual credentials.

---

### 🧪 4. Create a Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate      # Linux/macOS
venv\Scripts\activate         # Windows
```

---

### 📦 5. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### ⚙️ 6. Run Alembic Migrations

Alembic is used to create your database tables from SQLAlchemy models.

#### ✅ When to run Alembic?

* After first setting up the project (initial migration)
* Whenever you change your models (`models/`)

#### ▶️ To run migrations:

```bash
alembic upgrade head
```

> Make sure `alembic.ini` and `env.py` are correctly configured to use the `DATABASE_URL` from `.env`.

If you ever change a model and want to generate a new revision:

```bash
alembic revision --autogenerate -m "Your message"
alembic upgrade head
```

---

### 🚀 7. Run Backend (FastAPI)

```bash
cd app
uvicorn main:app --reload
```

📍 FastAPI runs at: [http://127.0.0.1:8000/docs]

---

### 💻 8. Run Frontend (Streamlit)

Open a **new terminal**, activate your virtual environment again if needed:

```bash
cd (frontend folder_name)
streamlit run streamlit_app.py
```

📍 Streamlit UI opens at: [http://localhost:8501](http://localhost:8501)

---

### 🧪 9. Test the App

* ✅ Register and login
* ✅ Start chatting with GPT
* ✅ Get city-wise weather
* ✅ View and continue previous chat history

---
