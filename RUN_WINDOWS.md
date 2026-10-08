# Windows quick start

Backend:
```powershell
cd backend
py -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000
```

Frontend (new terminal):
```powershell
cd frontend
npm install
npm run dev
```
