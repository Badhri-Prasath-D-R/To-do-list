# ✅ To-Do List App — Built with Flask, SQLite & SCSS

A full-stack task management web application built with **Python**, **Flask**, and **SQLite**. Features a clean, styled UI with **SCSS** and supports creating, editing, and deleting tasks — all persisted in a database.

---

## 📸 Preview

> *(Add a screenshot of the app here — highly recommended for hirer appeal!)*

---

## ✨ Features

- **Add Tasks** — Submit new tasks via a simple form on the home page
- **Edit Tasks** — Update existing task content through a dedicated edit page
- **Delete Tasks** — Remove tasks instantly with a single click
- **Persistent Storage** — All tasks saved to a SQLite database with auto-creation on first run
- **Timestamps** — Each task is stored with its creation time (UTC) and displayed in creation order
- **SCSS Styling** — Custom styles compiled on-the-fly via Flask-SCSS
- **Deployment Ready** — Reads the `PORT` environment variable for easy cloud deployment

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core backend language |
| Flask | Web framework & routing |
| Flask-SQLAlchemy | ORM for database interaction |
| SQLite | Embedded relational database |
| Flask-SCSS | SCSS compilation for styling |
| HTML (Jinja2) | Templated frontend views |
| SCSS | Custom CSS styling |

---

## 📦 Installation & Setup

### Prerequisites
- Python 3.x
- pip package manager

### Steps

```bash
# Clone the repository
git clone https://github.com/Badhri-Prasath-D-R/To-do-list.git
cd To-do-list

# (Optional) Create and activate a virtual environment
python -m venv venv
source venv/bin/activate       # macOS/Linux
venv\Scripts\activate          # Windows

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
```

Open your browser and visit `http://127.0.0.1:5000/`

---

## 🗺️ App Routes

| Method | Route | Description |
|---|---|---|
| `GET` | `/` | View all tasks |
| `POST` | `/` | Submit a new task |
| `GET` | `/delete/<id>` | Delete a task by ID |
| `GET` | `/edit/<id>` | Load the edit page for a task |
| `POST` | `/edit/<id>` | Save updated task content |

---

## 🗄️ Database Model

The `MyTask` model stores the following fields:

| Field | Type | Description |
|---|---|---|
| `id` | Integer (PK) | Auto-incremented unique ID |
| `content` | String(100) | The task description |
| `complete` | Integer | Completion status |
| `created` | DateTime | Timestamp of creation (UTC) |

The `database.db` SQLite file is auto-generated in the `instance/` folder on first run.

---

## 📁 Project Structure

```
To-do-list/
├── app.py               # Flask app, DB model, and all route logic
├── requirements.txt     # Python dependencies
├── templates/
│   ├── index.html       # Home page — task list and add form
│   └── edit.html        # Edit page — update task content
├── static/
│   └── *.scss           # SCSS stylesheets
└── instance/
    └── database.db      # Auto-generated SQLite database
```

---

## ☁️ Deployment

The app is configured for deployment on platforms like **Render** or **Railway**. The port is dynamically read from the `PORT` environment variable:

```python
port = int(os.environ.get("PORT", 5000))
app.run(host="0.0.0.0", port=port)
```

Simply connect your GitHub repo to your preferred hosting platform and deploy directly.

---