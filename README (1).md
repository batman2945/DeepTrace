
# 🕵️‍♂️ DeepTrace-AI
**AI-Powered Secret Leak Detector for GitHub Repositories**

> Detects exposed API keys, passwords, tokens, and sensitive configs in public code using NLP + Regex.

---

## 🚀 About the Project

Developers often accidentally leak secrets (like AWS keys or DB passwords) in public GitHub repos, which can lead to serious security breaches.

**DeepTrace-AI** solves this by using:
- 🤖 CodeBERT (a transformer-based AI model) to understand and classify code lines
- 🧠 Regex patterns to detect common secret types (fallback layer)
- 📁 GitHub API to scan entire public repositories
- 🛡️ Suggested remediation steps to fix exposed secrets

---

## 🧠 Tech Stack

- **Python**
- 🤗 `transformers` (CodeBERT from HuggingFace)
- 🔍 `re` for regex scanning
- 🌐 `requests` for GitHub file access
- 💡 Optional: FastAPI, MongoDB, Docker (extendable)

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

---

## 🔍 Sample Output

```
🔍 Scanning .env.example...

⚠️ [Regex] AWS Access Key in .env.example, line 59: AWS_ACCESS_KEY_ID=
💡 Suggested Fix:
   → Rotate the key via AWS Console and store it in environment variables.

⚠️ [AI] Sensitive line in .env.example, line 27: DB_PASSWORD=
💡 Suggested Fix:
   → Review the line. Avoid hardcoding sensitive data. Use env variables or config management tools.
```

---

## 💡 Remediation Advice

For each detected secret, DeepTrace-AI will suggest one or more of the following:
- Move to `.env` file or environment variables
- Add file to `.gitignore`
- Rotate API keys or passwords
- Use secrets managers like AWS Secrets Manager, Vault, etc.

---

## 🎯 Why It Matters

Unlike simple regex scanners, DeepTrace-AI uses **AI to understand intent** behind code lines — catching edge cases, comments, and uncommon secret formats too.

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

---
