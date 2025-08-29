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

📖 Full reference: [scrayz.com/docs](https://scrayz.com)

### Base URL
~~~
https://api.scrayz.com
~~~

### Endpoint
~~~
GET /api/users/scrape-linkedin
~~~

### Query Parameters
- `api_key` — your API key  
- `linkedln_username` — public identifier (e.g., `maxim-haim`)  
- `data_type` — one of: `basic`, `experience`, `education`, `skills`, `all` (recommended)  

---

### 🔥 Example: cURL
~~~bash
curl -G "https://api.scrayz.com/api/users/scrape-linkedin" \
  --data-urlencode "api_key=YOUR_API_KEY" \
  --data-urlencode "linkedln_username=maxim-haim" \
  --data-urlencode "data_type=all" \
  -H "accept: application/json"
~~~

### 🐍 Example: Python
~~~python
import requests

url = "https://api.scrayz.com/api/users/scrape-linkedin"
params = {
    "api_key": "YOUR_API_KEY",
    "linkedln_username": "maxim-haim",
    "data_type": "all"
}
res = requests.get(url, params=params, headers={"accept": "application/json"})
print(res.json())
~~~

### 🟢 Example: Node.js
~~~js
const axios = require("axios");

axios.get("https://api.scrayz.com/api/users/scrape-linkedin", {
  params: {
    api_key: "YOUR_API_KEY",
    linkedln_username: "maxim-haim",
    data_type: "all"
  },
  headers: { accept: "application/json" }
})
.then(res => console.log(res.data))
.catch(err => console.error(err));
~~~

---

## 📦 Example Response
~~~json
{
  "status": "ok",
  "data": {
    "profile": {
      "public_id": "maxim-haim",
      "full_name": "Maxim Haim",
      "headline": "Security Lead",
      "location": "New York, United States"
    },
    "experience": [
      {
        "company": "ACME Inc.",
        "title": "Application Security Team Lead",
        "location": "NY, USA",
        "start_month": "Jan",
        "start_year": "2022",
        "end_month": "",
        "end_year": "",
        "description": "Responsible for…"
      }
    ],
    "education": [
      {
        "school": "Some University",
        "degree": "BSc",
        "field": "Computer Science",
        "start_year": "2016",
        "end_year": "2020"
      }
    ],
    "skills": ["AppSec", "Threat Modeling", "Python"]
  }
}
~~~

---

## ⚠️ Common Errors
~~~json
{ "status": "error", "error": "linkedln_username is required" }   // 400 — missing parameter
{ "status": "error", "error": "Unauthorized: invalid api_key" }   // 401 — invalid API key
{ "status": "error", "error": "Profile not found" }               // 404 — not found
{ "status": "error", "error": "Too many requests, please retry later" } // 429 — rate limit
~~~

---

## 📈 Scaling Notes
- Run **batch jobs** with CSV input → JSONL output.  
- Use **multiple workers** + proxy pools for millions/day.  
- Example: 50 workers × 2 req/s → **~8.6M profiles/day**.  
- Shard input files, merge results downstream.  

---

## 📜 License
MIT (or private use — choose what suits your project).
