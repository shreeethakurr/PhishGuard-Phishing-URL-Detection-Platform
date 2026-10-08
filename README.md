# PhishGuard 🛡️

PhishGuard is a defensive phishing-awareness and URL risk-analysis platform built with React + Vite + Tailwind CSS and Python FastAPI.

## What it does

Enter a URL and PhishGuard analyzes passive URL characteristics such as:

- HTTPS usage
- IP-address hosts
- suspicious URL schemes
- URL length
- suspicious TLDs
- excessive subdomains
- suspicious keywords
- URL encoding / obfuscation indicators
- hostname/domain structure
- look-alike domain indicators
- risky ports

It produces an explainable **0–100 risk score**, severity, findings, and recommendations.

> This project is designed for defensive analysis. It does not exploit websites, brute-force accounts, or perform intrusive scanning.

## Project structure

```text
PhishGuard/
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   └── analyzer.py
│   ├── requirements.txt
│   └── .env.example
├── frontend/
│   ├── src/
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   ├── index.html
│   ├── package.json
│   ├── postcss.config.js
│   ├── tailwind.config.js
│   └── vite.config.js
└── README.md
```

## Run locally

### Backend

```bash
cd backend
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000
```

API docs: http://localhost:8000/docs

### Frontend

Open a second terminal:

```bash
cd frontend
npm install
npm run dev
```

Then open the Vite URL shown in your terminal.

The frontend proxies `/api` requests to the FastAPI server.

## Notes

This first version deliberately avoids claiming that a URL is definitively safe or malicious. It provides a transparent heuristic risk assessment. For production use, reputation feeds and a validated ML model can be added later.
