# 🔐 DeepTrace-AI: AI-Powered Secret Leak Detector

DeepTrace-AI is an advanced Python tool that scans GitHub repositories, files, and URLs for **hardcoded secrets** using both **regex patterns** and **AI-based classification** (CodeBERT).

---

## 🚀 Features

- ✅ **Regex + AI detection** for secrets like API keys, tokens, passwords
- ⚡ Fast scanning with multithreading
- 🎯 Confidence threshold to reduce false positives
- 🔍 Scans public GitHub repos using the GitHub API
- 📂 Supports `.env`, config files, and raw URLs

---

## 📦 Install Requirements

```bash
pip install torch transformers requests
```

---

## 🧠 AI Model

- Uses [CodeBERT (microsoft/codebert-base)](https://huggingface.co/microsoft/codebert-base)
- Binary classification: Sensitive vs Non-sensitive code lines

---

## 🕹️ How to Use

```bash
python deeptrace_ai_scanner.py
```

Then choose one of the options:

1️⃣ Scan Laravel default `.env.example`  
2️⃣ Scan any GitHub repo recursively  
3️⃣ Scan a raw file URL

---

## 🧪 Example Output

```
Scanning file: .env.example ...
Error [Regex] Generic Password in .env.example, line 15: password=mysecret
Error [AI] Sensitive line in config.py, line 42: stripe_api_key = "sk_test_..."
=== Scan Summary ===
Total files scanned: 5
Files with sensitive info detected: 2
Total issues found: 6
Secure files: 3
```

---

## 📚 Supported Secrets (Regex)

- AWS Access Keys
- Google API Keys
- JWT Secrets
- Bearer Tokens
- Database URLs
- Stripe Keys
- Private SSH Keys
- Generic passwords & API keys

---

## 📜 License

MIT License © 2025

---

## 👨‍💻 Author

Dharmik Dudhat  
Feel free to ⭐ the repo or contribute improvements!
