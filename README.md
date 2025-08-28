## 🚀 API Quickstart

📖 Full reference: [scrayz.com/docs](https://scrayz.com/docs)

### Base URL

### Endpoint


GET /api/users/scrape-linkedin
### Query Parameters
- `api_key` — your API key
- `linkedln_username` — public identifier (e.g., `maxim-haim`)
- `data_type` — one of: `basic`, `experience`, `education`, `skills`, `all` (recommended)

---

### Example: cURL
```bash
curl -G "https://api.scrayz.com/api/users/scrape-linkedin" \
  --data-urlencode "api_key=YOUR_API_KEY" \
  --data-urlencode "linkedln_username=maxim-haim" \
  --data-urlencode "data_type=all" \
  -H "accept: application/json"


### Example: Python
import requests

url = "https://api.scrayz.com/api/users/scrape-linkedin"
params = {
    "api_key": "YOUR_API_KEY",
    "linkedln_username": "maxim-haim",
    "data_type": "all"
}
res = requests.get(url, params=params, headers={"accept":"application/json"})
print(res.json())

Example: Node.js

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

