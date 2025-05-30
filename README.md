
# Patient Care Plan Assistant

A web application built with Flask and Google’s Gemini API to extract, analyze, and update patient care plans from PDF uploads and free-text feedback. It auto-detects emergency symptoms, sends urgent alerts, and generates attractively formatted daily care plans using LLM-powered suggestions.

---

## 🔍 Table of Contents

- [Features](#features)  
- [Prerequisites](#prerequisites)  
- [Installation](#installation)  
- [Configuration](#configuration)  
- [Usage](#usage)  
- [Project Structure](#project-structure)  
- [Endpoints](#endpoints)  
- [License](#license)  

---

## 🚀 Features

- **Role switching** between patient and doctor dashboards  
- **PDF parsing** of existing care plans via PyPDF2  
- **Regex-based template extraction** for care-plan sections  
- **LLM-powered updates**: Google Gemini generates polished daily care plans  
- **Emergency detection**: Flags critical symptoms and returns urgent instructions  
- **Session management** for secure, per-user workflows  

---

## ⚙️ Prerequisites

- Python 3.8+  
- Flask  
- PyPDF2  
- google-generativeai SDK  
- A Gemini API key (Google Cloud)  

---

## 🛠 Installation

1. **Clone the repo**  
   ```bash
   git clone https://github.com/yourusername/patient-care-assistant.git
   cd patient-care-assistant
````

2. **Create & activate virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate   # macOS/Linux
   # or
   venv\Scripts\activate      # Windows
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

---

## 🔧 Configuration

Create a `.env` file in the project root:

```ini
# Flask
SECRET_KEY=your_flask_secret_key

# Google Gemini
GEMINI_API_KEY=AIzaSyA3joMQMnael_heUCwpNvoRznCUiU3avf4
GEMINI_MODEL=gemini-2.0-flash-exp
TEMPERATURE=1
TOP_P=0.95
TOP_K=40
MAX_OUTPUT_TOKENS=8192
```

---

## ▶️ Usage

1. **Activate environment**

   ```bash
   source venv/bin/activate
   ```

2. **Run the server**

   ```bash
   python app.py
   ```

3. **Patient portal**

   * Visit `http://127.0.0.1:5001/`
   * Upload care plan PDF and enter feedback

4. **Doctor dashboard**

   * Switch role to “doctor” on the home page
   * View emergency notifications at `http://127.0.0.1:5001/doctor_dashboard`

---

## 📁 Project Structure

```
patient-care-assistant/
├── app.py
├── requirements.txt
├── uploads/                # Temporary PDF uploads
├── templates/
│   ├── index.html
│   └── doctor_dashboard.html
├── static/
│   ├── css/
│   └── js/
└── .env
```

---

## 🔗 Endpoints

* **GET /**
  Home page with role switch and PDF feedback form.

* **POST /switch\_role**
  Sets session role (“patient” or “doctor”).

* **POST /submit\_feedback**
  Parses PDF + feedback, returns updated care plan or emergency instructions.

* **GET /doctor\_dashboard**
  Protected doctor view showing emergency notifications.

* **GET /get\_emergency\_notifications**
  Returns JSON list of flagged emergencies.

---

## 📄 License

This project is licensed under MIT. See the [LICENSE](LICENSE) file for details.

```
```
