```markdown
# AI Mentor Bootcamp — Vegi Divya Jaswanthi

Public portfolio of 12-day AI Trainer Workshop. By Day 12: 6 daily notebooks + capstone Streamlit URL.
```

**Trainer note:** Write each mentor's repo URL on the whiteboard next to their name. By Day 12 you reference these URLs for grading.

**Acceptance:** `https://github.com/Vdivyajaswanthi123/ai-mentor-portfolio` is publicly accessible.
## Day 1 – Setup complete

- ✅ Google AI Studio API key provisioned
- ✅ Groq API key provisioned
- ✅ Hello-Gemini call working – see [Day1_Setup.ipynb](Day1_Setup.ipynb)

### Screenshot

![Gemini First Call](./gemini_first_call.png)



## Day 4 — n8n Daily News Digest

- ✅ Self-hosted n8n via Docker
- ✅ Workflow: Schedule (7AM IST) → RSS → Gemini summariser → Gmail
- ✅ Workflow JSON committed: [Day4_NewsDigest.json](Day4_NewsDigest.json)
- ✅ Test email screenshot below

![Test email screenshot](./Day4_news_digest_mail.png)

# Day 5 — Résumé Scorer Streamlit

**Live URL:** [https://your-app-name.streamlit.app ](https://resume-scorer-divya.streamlit.app/) 
**Code:** [app.py](app.py)  
**Acceptance Log:** [acceptance_log.md](acceptance_log.md)

## Tools Used

- Continue.dev
- Gemini 2.5 Flash
- Streamlit
- GitHub
- Streamlit Community Cloud

## Features

- Résumé vs JD fit score
- Rationale
- Missing skills
- Suggestions
- 4-axis score breakdown chart
- Free learning resources for missing skills

## Reflection

- This is an AI-assisted prototype.
- To productionise, I would add better error handling, caching, rate limits, and authentication.
- Continue.dev helped scaffold the UI quickly, but manual review was needed for prompt correctness and deployment fixes.

## Day 5 Lab 5B — Hugging Face Pulls

### Models tested
- `facebook/bart-large-mnli` — zero-shot classification
- `distilbert-base-uncased-finetuned-sst-2-english` — sentiment

### Timing comparison

| | min | avg | Notes |
|---|-----|-----|-------|
| API | 0.24s | 0.25s | Cold-start: 20s |
| Local | 0.86s | 0.95s | Download: 60s on first run |

### When to use each (3-line reflection)

1. **API:** for low-volume, occasional calls. Avoids download. Cold-start risk on first call after idle.
2. **Local:** for batch processing 100+ items, where you want predictable latency and don't pay per call.
3. **Production rule of thumb:** if your usage exceeds the API free tier (~30K requests/month at HF), self-host. Otherwise API.
   
## Day 6 Lab 6A — unexpected success

1. **Executed Successfully** 
   Executed without getting eny errors and got unexpected success with success object.
   
## Day 7 Lab 7A — ChromaDB Hello-World

- Embedded 10 CSE Sem 5 paragraphs with all-MiniLM-L6-v2 (384-dim, free)
- Indexed in persistent ChromaDB collection `hello_syllabus`
- Ran 3 semantic queries — observed: top-1 match is relevant when query topic is in corpus, irrelevant when not
- Plotted PCA 2D — visible OS / DBMS clusters

**Reflection:** Semantic search returns nearest, not exact. RAG must enforce citations to catch out-of-corpus queries (this afternoon's Sprint 2).
---
