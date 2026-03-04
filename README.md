# Eva AI Backend 🧠
> Think it. Say it. Done.

FastAPI backend powering **Eva** — an AI assistant for busy parents.  
Built with Groq (LLaMA 3) + SQLite. Deploy-ready for Render or DigitalOcean.

---

## Features

| Endpoint | Eva Feature | Description |
|---|---|---|
| `POST /speak-it` | **Speak It** | Natural language → structured task via Groq AI |
| `POST /plan-it` | **Plan It** | Goal text → full weekly plan |
| `POST /focus-mode` | **Focus Mode** | AI picks your top 3 priorities |
| `POST /shift-it` | **Shift It** | Reschedules tasks across next 3 days |
| `GET/POST/PUT/DELETE /tasks` | Tasks | Full task CRUD |
| `GET/POST/PUT /quick-list` | **Quick List** | Grocery/errand list with duplicate detection |
| `GET /goals` | Goals | View all saved goals and plans |

---

## Run Locally

```bash
pip install -r requirements.txt
GROQ_API_KEY=your_key_here uvicorn main:app --reload
```

Open **http://localhost:8000/docs** for the interactive API docs.

---

## Deploy to Render

1. Push this repo to GitHub
2. Go to [render.com](https://render.com) → New → Web Service
3. Connect your GitHub repo
4. Set **Build Command**: `pip install -r requirements.txt`
5. Set **Start Command**: `uvicorn main:app --host 0.0.0.0 --port $PORT`
6. Add environment variable: `GROQ_API_KEY` = your Groq key
7. Click Deploy

---

## Test the AI

Once running, try this in `/docs`:

**POST /speak-it**
```json
{ "voice_input": "dentist for Jake Tuesday 3pm" }
```

**POST /plan-it**
```json
{ "goal": "Run a 5K in 3 months, early mornings only" }
```

**POST /focus-mode**
```json
{}
```
