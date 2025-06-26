# Chatbot for Customer Support
![Chatbot_for_Customer_Support.jpg](Chatbot_for_Customer_Support.jpg)
◦Engineered a Chatbot for Customer Support using Machine Learning
<br>
◦Coming Soon


Procedure to run Chatbot-
1. Create a virtual environment and install all the dependencies enclosed in requirements.txt
2. Create a groq api key and enter it in .env and connect_memory_with_llm.py files. I have put a comment wherever you need to paste your api key.
3. Put data csv file in data folder. (I already have a customer data of 1,00,000 rows.
4. Run intent_generation.py to create intents.json.
5. Run create_memory_for_llm. It will create a database to store vectors. (it may take some time)
6. Run chatbot.py (Enter streamlit run chatbot.py to open chatbot in local host)

The final structure may look like this


# 🤖 Chatbot Setup Guide

This guide walks you through the steps required to set up and run the chatbot locally using Streamlit and Groq LLM.

---

## 🧰 Prerequisites

- Python 3.8 or higher
- Virtual environment tool (`venv` or `virtualenv`)
- A Groq API key (get it from [Groq Console](https://console.groq.com/))

---

## ⚙️ Installation & Setup

### 1️⃣ Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

---

### 2️⃣ Configure the Groq API Key

#### 🔐 Step A: Add API Key to `.env`

Create a `.env` file in the root directory (if not already present) and add:

```
GROQ_API_KEY=your_groq_api_key_here
```

#### 🛠 Step B: Update `connect_memory_with_llm.py`

Open `connect_memory_with_llm.py` and locate the section with the comment:

```python
# Paste your API key here
```

Replace or add:

```python
groq_api_key = "your_groq_api_key_here"
```

---

### 3️⃣ Add Your Data

Place your customer data CSV file in the `data/` directory.

> ⚠️ **Note:** This chatbot has been tested with datasets up to **100,000 rows**.

Example:

```plaintext
project-root/
└── data/
    └── customer_data.csv
```

---

### 4️⃣ Generate Intents

Run this script to generate the `intents.json` file from your dataset:

```bash
python intent_generation.py
```

---

### 5️⃣ Build Vector Memory (FAISS)

Create vector embeddings and store them in a FAISS index:

```bash
python create_memory_for_llm.py
```

> ⏳ This step may take a few minutes depending on your dataset size.

---

### 6️⃣ Launch the Chatbot

Use Streamlit to run the chatbot:

```bash
streamlit run chatbot.py
```

Open your browser and visit:

```
http://localhost:8501
```

---

## ✅ You're All Set!

Your chatbot is now running locally!  
You can now interact, test, and enhance it as needed.

---

## 📁 Project Structure Overview

```plaintext
├── chatbot.py
├── connect_memory_with_llm.py
├── create_memory_for_llm.py
├── intent_generation.py
├── requirements.txt
├── .env
├── data/
│   └── customer_data.csv
├── vector/
│   └── faiss_index (auto-created)
└── intents.json (auto-created)
```
