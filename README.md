# 🚀 Recruitment Agency

<div align="center">

**The Modern Platform for Recruitment Excellence**

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-brightgreen.svg)](https://www.python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-00a393.svg)](https://fastapi.tiangolo.com)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

[🌐 Live Demo](#demo) • [📖 Documentation](#quick-start) • [🤝 Contributing](#contributing) • [💬 Support](#contact--support)

</div>

---

## 📸 Demo

![Recruitment Agency Dashboard](https://img.shields.io/badge/GIF_PLACEHOLDER-Dashboard_Walkthrough-ff69b4?style=for-the-badge)

*Replace with actual dashboard GIF at: `assets/demo-dashboard.gif`*

<details>
<summary><b>🎬 Watch Features in Action</b></summary>

- 🔍 **[Candidate Search & Filtering GIF](assets/search-demo.gif)** — Find top talent in seconds
- 📋 **[Pipeline Management GIF](assets/pipeline-demo.gif)** — Visual hiring workflow
- 📧 **[Bulk Outreach GIF](assets/outreach-demo.gif)** — Automated candidate engagement
- 📊 **[Analytics Dashboard GIF](assets/analytics-demo.gif)** — Real-time recruitment metrics

</details>

---

## 🎯 Overview

> **Recruitment Agency** is a lightweight, feature-rich platform that empowers recruitment teams to source, track, and engage candidates faster. Combining structured candidate profiles with flexible hiring pipelines and intelligent automation, it streamlines the entire recruitment lifecycle while maintaining simplicity and control.

**Perfect for:**
- 👥 Mid-to-large recruitment agencies
- 🏢 Corporate talent acquisition teams
- 💼 Executive search firms
- 🌍 Remote-first hiring operations

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🔎 **Smart Candidate Profiles** | Searchable, filterable candidate database with custom fields |
| 🔄 **Flexible Job Pipelines** | Configurable hiring workflows tailored to your process |
| 📥 **Bulk Import/Export** | CSV & Excel support for seamless data management |
| 🔐 **Role-Based Access** | Granular permissions and audit logs for compliance |
| 🔗 **REST API** | Integrate with your favorite ATS, CRM, or analytics tools |
| ⚡ **Automated Outreach** | Email sequences, reminders, and follow-up automation |
| 📊 **Analytics Dashboard** | Track pipeline metrics, conversion rates, and KPIs |
| 🌙 **Dark Mode** | Eye-friendly interface for long recruiting sessions |


---

## 🛠️ Technology Stack

<table>
  <tr>
    <td><b>Backend</b></td>
    <td>Python 3.10+, FastAPI, Uvicorn</td>
  </tr>
  <tr>
    <td><b>Database</b></td>
    <td>PostgreSQL (primary), Redis (caching & jobs)</td>
  </tr>
  <tr>
    <td><b>Frontend</b></td>
    <td>React / Vue (optional SPA)</td>
  </tr>
  <tr>
    <td><b>Task Queue</b></td>
    <td>Celery + Redis for background jobs</td>
  </tr>
  <tr>
    <td><b>DevOps</b></td>
    <td>Docker, GitHub Actions, AWS/GCP</td>
  </tr>
  <tr>
    <td><b>Monitoring</b></td>
    <td>Prometheus, Grafana (optional)</td>
  </tr>
</table>

---

## 🚀 Quick Start

### 📋 Requirements

- **Python 3.10+**
- **PostgreSQL 12+** (or SQLite for development)
- **Redis 6+** (for background tasks)
- **Git**
- **pip** or **Poetry**

### 📦 Installation

**1️⃣ Clone the repository:**

```bash
git clone https://github.com/MustafaKocamann/Recruitment-Agency.git
cd Recruitment-Agency
```

**2️⃣ Create & activate a virtual environment:**

```bash
python -m venv venv

# On Windows:
venv\Scripts\activate

# On macOS/Linux:
source venv/bin/activate
```

**3️⃣ Install dependencies:**

```bash
pip install -r requirements.txt
```

**4️⃣ Configure environment:**

```bash
cp .env.example .env
# Edit .env with your database credentials, JWT secret, etc.
```

**5️⃣ Initialize the database:**

```bash
python -m alembic upgrade head
```

### ▶️ Run Locally

**Start the backend server:**

```bash
uvicorn app.main:app --reload
```

Visit 🌐 **http://localhost:8000** → API docs at `/docs`

**In a separate terminal, start the worker (for background jobs):**

```bash
celery -A app.tasks worker --loglevel=info
```

**Start the frontend (if applicable):**

```bash
cd frontend
npm install
npm run dev
```

---

## ⚙️ Configuration

Key environment variables in `.env`:

```env
DATABASE_URL=postgresql://user:password@localhost/recruitment_db
REDIS_URL=redis://localhost:6379/0
JWT_SECRET=your-super-secret-key-here
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASSWORD=your-app-password
```

---

## 💡 Usage Examples

### 🌐 Web UI

**Creating a job opening:**
1. Dashboard → **New Job** → Fill form → **Save**
2. Share link with recruiting team
3. Track applicants in real-time

**Importing candidates:**
1. Candidates → **Import** → Upload CSV
2. Map fields → **Validate** → **Import**
3. Search and filter by any attribute

### 🔌 API Usage

**Create a candidate:**

```bash
curl -X POST http://localhost:8000/api/v1/candidates \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "first_name": "Alex",
    "last_name": "Taylor",
    "email": "alex@example.com",
    "source": "LinkedIn",
    "skills": ["Python", "FastAPI", "PostgreSQL"]
  }'
```

**Response:**

```json
{
  "id": "cnd_12345abcde",
  "first_name": "Alex",
  "last_name": "Taylor",
  "email": "alex@example.com",
  "source": "LinkedIn",
  "skills": ["Python", "FastAPI", "PostgreSQL"],
  "created_at": "2026-02-22T14:30:00Z"
}
```

---

## 🏗️ Project Architecture

```
Recruitment-Agency/
├── app/
│   ├── main.py              # FastAPI app entry point
│   ├── api/                 # API routes
│   ├── models/              # SQLAlchemy ORM models
│   ├── schemas/             # Pydantic request/response schemas
│   ├── services/            # Business logic
│   ├── tasks/               # Celery background tasks
│   └── utils/               # Helper functions
├── migrations/              # Alembic database migrations
├── tests/                   # Unit & integration tests
├── requirements.txt         # Python dependencies
├── .env.example             # Environment template
├── docker-compose.yml       # Local development stack
└── README.md                # This file
```

---

## 🧪 Testing

**Run all tests:**

```bash
pytest
```

**Run with coverage:**

```bash
pytest --cov=app tests/
```

**Run specific test file:**

```bash
pytest tests/test_candidates.py -v
```

---

## 🔄 CI / CD

GitHub Actions pipeline runs on every PR:
- ✅ **Linting** (Flake8, Black, isort)
- ✅ **Unit Tests** (pytest)
- ✅ **Type Checking** (mypy)
- ✅ **Security** (bandit)
- ✅ **Build & Push** to container registry

---

## 👥 Contributing

**We ❤️ contributions!** Here's how to get started:

1. 🍴 **Fork** the repository
2. 🌿 **Create a feature branch:** `git checkout -b feature/amazing-feature`
3. ✍️ **Commit changes:** `git commit -m "Add amazing feature"`
4. 📤 **Push branch:** `git push origin feature/amazing-feature`
5. 📬 **Open a Pull Request** with a clear description

**Before submitting:**
- Add tests for your changes
- Run `pytest` to ensure all tests pass
- Follow our [CONTRIBUTING.md](CONTRIBUTING.md) guide

---

## 📜 Code of Conduct

We are committed to providing a welcoming environment for all contributors. See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

---

## 🔒 Security

**Found a vulnerability?** Please email **security@recruitment-agency.dev** with details. Do NOT open a public issue.

---

## 📄 License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.

```
MIT License © 2026 Mustafa Kocaman
```

---

## 📞 Contact & Support

| | |
|---|---|
| 👨‍💻 **Developer** | [Mustafa Kocaman](https://github.com/MustafaKocamann) |
| 📧 **Email** | support@recruitment-agency.dev |
| 💬 **Discussions** | [GitHub Discussions](https://github.com/MustafaKocamann/Recruitment-Agency/discussions) |
| 🐛 **Issues** | [GitHub Issues](https://github.com/MustafaKocamann/Recruitment-Agency/issues) |
| 📖 **Wiki** | [Project Wiki](https://github.com/MustafaKocamann/Recruitment-Agency/wiki) |

---

## 🎉 Acknowledgements

Built with ❤️ using cutting-edge open-source technologies. Special thanks to the amazing FastAPI, SQLAlchemy, and PostgreSQL communities.

---

<div align="center">

**Give this project a ⭐ if it helped you!**

[⬆ Back to top](#-recruitment-agency)

</div>