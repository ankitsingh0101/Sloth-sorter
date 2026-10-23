# 🦥 Sloth Sorter

A lazy, local-AI file tidier with a web UI. A local open-weight model
(Gemma via Ollama) decides where each file belongs and what to call it.
Your files never leave your machine.

## Setup (Windows, once)
```bat
ollama pull gemma3:4b
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
cd web && npm install && cd ..
```

## Run
Double-click `start.bat` (or run the API and UI in two terminals):
```bat
python -m uvicorn server:app --port 8000
cd web && npm run dev
```
Open http://localhost:3000, paste a folder path, scan, review, apply.

## CLI (no UI)
```bat
python sloth_sorter.py C:\Users\you\Downloads
python sloth_sorter.py C:\Users\you\Downloads --apply
python sloth_sorter.py C:\Users\you\Downloads --undo
```

## Safety
Dry-run first, never overwrites files, refuses drive roots, only touches
the top level of the chosen folder, and logs every move for undo.

## Why open?
Runs offline, keeps personal files private, costs nothing after setup.
