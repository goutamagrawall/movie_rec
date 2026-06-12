# Movie Recommender

A local movie recommender system with a FastAPI backend and a Streamlit frontend.

## Project structure

- `main.py` - FastAPI backend with TMDB integration and TF-IDF recommendation logic
- `app.py` - Streamlit frontend UI for searching movies and showing recommendations
- `requirements.txt` - Python dependencies
- `runtime.txt` - Python runtime file for hosting platforms
- `df.pkl`, `indices.pkl`, `tfidf_matrix.pkl`, `tfidf.pkl` - prebuilt local TF-IDF assets used by the backend
- `.env` - environment variables (not committed)

## Setup

1. Create and activate a Python virtual environment.

```bash
python -m venv .venv
.\.venv\Scripts\activate
```

2. Install dependencies.

```bash
pip install -r requirements.txt
```

3. Create a `.env` file with your TMDB API key.

```bash
TMDB_API_KEY=your_tmdb_api_key_here
```

## Run

### Backend

```bash
python -m uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

### Frontend

```bash
python -m streamlit run app.py
```

Then open the Streamlit app at `http://localhost:8501`.

## GitHub deployment

1. Create a new GitHub repository in your account.
2. Add the remote and push:

```bash
git remote add origin https://github.com/<your-username>/<repo-name>.git
git branch -M main
git push -u origin main
```

## Notes

- Keep `.env` out of GitHub because it contains secrets.
- If the repository grows large, consider using Git LFS for binary data files.
