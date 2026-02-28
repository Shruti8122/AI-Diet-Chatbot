# 🥗 Diet Specialist AI Chatbot API

An AI-powered Diet Specialist Chatbot built using **FastAPI**, **Groq LLM**, and **MongoDB Atlas**.
The chatbot provides personalized dietary guidance and maintains user-specific chat history with persistent memory.

---

## 🌐 Live API

🚀 Deployed on: Render

https://ai-diet-chatbot-f56g.onrender.com


Test endpoints:

https://ai-diet-chatbot-f56g.onrender.com/
https://ai-diet-chatbot-f56g.onrender.com/chat


---

## 🚀 Features

* 🤖 AI-powered responses using Groq (`openai/gpt-oss-20b`)
* 🥗 Diet-specialized system prompt
* 💾 Stores chat history per user
* 🌍 REST API built with FastAPI
* ☁️ Cloud database using MongoDB Atlas
* 🔄 Persistent conversation memory
* 🌐 CORS enabled for frontend integration
* 🚀 Production deployment on Render

---

## 🛠️ Tech Stack

* **Backend Framework:** FastAPI
* **LLM Provider:** Groq (`openai/gpt-oss-20b`)
* **Database:** MongoDB Atlas
* **Driver:** PyMongo
* **Deployment:** Render

---

## 📂 Project Structure

```
.
├── app.py
├── requirements.txt
├── .env
└── README.md
```

---

## 🔐 Environment Variables

Create a `.env` file in your root directory:

```
GROQ_API_KEY=your_groq_api_key
MONGODB_URI=your_mongodb_connection_string
```

When deploying on Render, add these inside:

**Dashboard → Environment → Environment Variables**

---

## ⚙️ Installation & Local Setup

### 1️⃣ Clone the repository

```
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2️⃣ Create virtual environment

```
python -m venv venv
venv\Scripts\activate   # Windows
```

### 3️⃣ Install dependencies

```
pip install -r requirements.txt
```

### 4️⃣ Run the server

```
uvicorn app:app --reload
```

Server will run at:

```
http://127.0.0.1:8000
```

---

## 📌 API Endpoints

### 🔹 GET `/`

Returns welcome message.

**Response:**

```json
{
  "message": "Welcome to the diet specialist Chatbot API"
}
```

---

### 🔹 POST `/chat`

Send user question to chatbot.

**Request Body:**

```json
{
  "user_id": "123",
  "question": "Suggest a vegetarian weight loss diet plan"
}
```

**Response:**

```json
{
  "response": "Here is a structured diet plan..."
}
```

---

## 🧠 How It Works

1. User sends a question with `user_id`
2. Previous chat history is fetched from MongoDB
3. Prompt is constructed using:

   * System role (Diet Specialist)
   * Chat history
   * Current question
4. Groq LLM generates response
5. Both user message and assistant reply are stored in MongoDB Atlas

---

## 📦 Database Schema

Each chat document:

```json
{
  "user_id": "string",
  "role": "user" | "assistant",
  "message": "string",
  "timestamp": "UTC datetime"
}
```

---

## 🧪 Future Improvements

* 🔐 Authentication system (JWT)
* 📊 Nutrition tracking dashboard
* 🧾 PDF diet plan generation
* 📉 Token usage monitoring
* 📱 Full-stack frontend integration
* 🧠 Optimized memory handling

---

## 👩‍💻 Author

**Shruti Singh**
AI/ML & Full Stack Developer

---
