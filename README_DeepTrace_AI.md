
# 🕵️‍♂️ DeepTrace-AI

**AI-Powered Secret Leak Detector for GitHub Repositories**

---

## 🚀 About the Project

Developers often accidentally leak secrets (like AWS keys or DB passwords) in public GitHub repos, which can lead to serious security breaches.

**DeepTrace-AI** solves this by using:
- 🧠 Regex patterns to detect common secret types (fallback layer)
- 🤖 Optional CodeBERT AI classifier for better accuracy
- 📁 GitHub API to scan entire public repositories
- 🛡️ Suggested remediation steps to fix exposed secrets

---

## 🧠 Tech Stack

- **Python**
- 🤗 `transformers` (CodeBERT from HuggingFace)
- 🔍 `re` for regex scanning
- 🌐 `requests` for GitHub file access
- 🧪 Optional: FastAPI, MongoDB, Docker (for expansion)

---

## ⚙️ Installation

```bash
git clone https://github.com/YOUR_USERNAME/deeptrace-ai.git
cd deeptrace-ai

# Create virtual env (optional)
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt
```

**requirements.txt:**
```txt
torch
transformers
requests
```

---

## 🧪 How to Use

### ✅ Option A: Scan a single public `.env` file

```bash
python deeptrace.py
```

Default: It scans Laravel’s sample config file.

### ✅ Option B: Scan entire public GitHub repo

Uncomment these lines in `deeptrace.py`:

```python
owner = "laravel"
repo = "laravel"
scan_github_repo(owner, repo)
```

### ✅ Option C: Scan any raw file URL

```bash
python deeptrace.py
```

Choose option 3 when prompted.

---

## 📈 Sample Output

```
🔍 Scanning .env.example...

⚠️ [Regex] AWS Access Key in .env.example, line 59: AWS_ACCESS_KEY_ID=...
⚠️ [Regex] Generic Password in .env.example, line 60: DB_PASSWORD=...
💡 Suggested Fix:
- Move to .env file or environment variables
- Add file to .gitignore
- Rotate credentials
```

---

## 🎯 Why It Matters

Perfect for:
- ✅ Open source security reviews
- ✅ CI/CD secret scanning
- ✅ GitHub Actions integration
- ✅ Ethical hacking demos

---

## 🏆 Built For

**AI Hackathon 2025**  
By [Your Name]  
Category: Cybersecurity / NLP

---

## 📈 Future Scope

- FastAPI or Streamlit interface
- Alerts via Slack/Telegram
- Secret rotation hooks
- GitHub Actions bot

