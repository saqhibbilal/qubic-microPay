# Setup – How to Run Micro-Qubic

Steps for running the app after cloning the repo.

---

## 1. Clone and go to project root

```bash
git clone <your-repo-url>
cd qubic-micro
```

All commands below assume you are in `qubic-micro` (project root) unless stated otherwise.

---

## 2. Backend (Flask API)

**Directory:** `backend/`

```bash
cd backend
```

Create and activate a virtual environment:

- **Windows (PowerShell):**
  ```bash
  python -m venv venv
  .\venv\Scripts\Activate.ps1
  ```
- **macOS / Linux:**
  ```bash
  python -m venv venv
  source venv/bin/activate
  ```

Install dependencies and run the app:

```bash
pip install -r requirements.txt
python app.py
```

Leave this terminal open. The API runs at **http://localhost:5000**. On first run it creates the DB and a demo merchant; the **API key** is printed in this terminal—copy it for the frontend.

---

## 3. Frontend (browser)

**Directory:** `frontend/` (or open from project root)

**Option A – Open the HTML file**

- Go to the `frontend` folder and double-click **index.html**, or  
- From project root: open `frontend/index.html` in your browser.

**Option B – Serve with a local server (if needed)**

From project root:

```bash
cd frontend
python -m http.server 8080
```

Then open **http://localhost:8080** in your browser.

---

## 4. Test the app

1. **Merchant tab:** Paste the API key from the backend terminal. Create a resource (name, description, price in QUBIC). Load resources to see it.
2. **User tab:** Enter a wallet address and the resource ID. Create session, then use “Mark as Paid” (demo) and “Check Status” to see the session as paid.
3. **Merchant tab:** Analytics (revenue, sessions) update when you load resources or create/mark sessions.

---

## Summary

| Step   | Where to run      | Command / action                                      |
|--------|-------------------|--------------------------------------------------------|
| Backend  | `backend/`        | `python -m venv venv` → activate → `pip install -r requirements.txt` → `python app.py` |
| Frontend | `frontend/` or root | Open `frontend/index.html` or run `python -m http.server 8080` in `frontend/` |

Backend must be running (port 5000) for the frontend to work.
