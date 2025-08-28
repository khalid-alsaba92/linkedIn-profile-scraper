# 🔗 LinkedIn Profile Scraper (No Cookies)

A **large-scale LinkedIn scraper** to extract **millions of public profiles daily** — no login or cookies required.  
Super-fast API + Batch jobs = LinkedIn data at scale 🚀

![FastAPI](https://img.shields.io/badge/API-FastAPI-informational)
![Scale](https://img.shields.io/badge/Throughput-Millions%2Fday-success)
![Auth](https://img.shields.io/badge/Auth-API%20Key-blue)
![Cookies](https://img.shields.io/badge/Login/Cookies-Not%20Required-brightgreen)

---

## ✨ Features
- 📊 **Data Coverage** → basics, experience, education, skills  
- ⚡ **Super-fast API** → fetch profiles on-demand  
- 🗂 **Batch Mode** → process CSV → JSONL  
- 🌍 **Scalable** → designed for millions of profiles per day  
- 🔒 **No login / no cookies required**  

---

## 🚀 API Quickstart

📖 Full reference: [scrayz.com/docs](https://scrayz.com/docs)

### Base URL
https://api.scrayz.com
### Endpoint


GET /api/users/scrape-linkedin

### Query Parameters
- `api_key` — your API key  
- `linkedln_username` — public identifier (e.g., `maxim-haim`)  
- `data_type` — one of: `basic`, `experience`, `education`, `skills`, `all` (recommended)  

---

### 🔥 Example: cURL
```bash
curl -G "https://api.scrayz.com/api/users/scrape-linkedin" \
  --data-urlencode "api_key=YOUR_API_KEY" \
  --data-urlencode "linkedln_username=maxim-haim" \
  --data-urlencode "data_type=all" \
  -H "accept: application/json"


