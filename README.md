### Amazon Music Clustering Explorer

Interactive Streamlit dashboard to explore clustering of Amazon Music tracks with multiple algorithms (K-Means, DBSCAN, Hierarchical), rich visualizations, advanced filtering, and similarity recommendations.

---

### Features
- **Multiple clustering methods**: switch between K-Means, DBSCAN, and Hierarchical.
- **Interactive visualizations**: bar charts, radar plots, correlation heatmap, and PCA scatter.
- **Advanced filters**: filter by genres and audio features (`danceability`, `energy`, `valence`, `tempo`).
- **Search & analyze**: search songs, analyze an artist, and find similar songs via cosine similarity.
- **Export**: download filtered data as CSV or JSON; quick summary report.

---

### Project Structure
```
e:\amz\
  app.py
  requirements.txt
  amazon_music_clusters_with_all_methods.csv
  single_genre_artists.csv
  AMC.ipynb
  Screenshot 1.png
  Screenshot 2.png
  Screenshot 3.png
  Screenshot 4.png
  Screenshot 5.png
  Screenshot 6.png
```

---

### Prerequisites
- Python 3.9+ recommended
- Windows PowerShell (this README uses Windows commands)

---

### Setup
1) Clone or copy this folder to your machine.
https://github.com/eprakash2/AMAZON-MUSIC-CLUSTER

2) Create and activate a virtual environment (Windows PowerShell):
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

3) Install dependencies:
```powershell
pip install -r requirements.txt
```

If you encounter an issue with `pip` using cached wheels, try:
```powershell
pip install --no-cache-dir -r requirements.txt
```

---

### Data
- Place `amazon_music_clusters_with_all_methods.csv` in the project root (same folder as `app.py`).
- The app expects at least these columns (additional columns are handled gracefully):
  - `name_song`, `name_artists`, `genres`, `danceability`, `energy`, `valence`, `tempo`
  - Clustering columns: `cluster` (K-Means), `cluster_dbscan`, `cluster_hc`
- If some optional features are missing (e.g., popularity, followers), the app fills in sensible defaults to remain functional.

---

### Run
Start the Streamlit app from the project root:
```powershell
streamlit run app.py
```
Streamlit will print a local URL (typically `http://localhost:8501`). Open it in your browser.

---

### Usage Tips
- Use the sidebar to choose the clustering method and adjust filters.
- Search tabs let you:
  - Find songs by title or artist
  - Analyze an artist’s cluster distribution and top energetic tracks
  - Find similar songs based on audio features using cosine similarity
- Use Export buttons to download the currently filtered dataset.

---

### Screenshots
Images below are included in the repo for quick reference:
- `Screenshot 1.png`
- `Screenshot 2.png`
- `Screenshot 3.png`
- `Screenshot 4.png`
- `Screenshot 5.png`
- `Screenshot 6.png`

You can drag them into the README preview in your editor or open them directly to see the UI.

---

### Troubleshooting
- "File not found: amazon_music_clusters_with_all_methods.csv": ensure the CSV is in the same folder as `app.py`.
- Blank charts or errors on filters: verify the CSV contains the expected column names and numeric types for audio features.
- Port already in use: run with a different port:
```powershell
streamlit run app.py --server.port 8502
```
- Virtual environment activation policy: if PowerShell blocks activation, run (as Administrator or with appropriate policy):
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

---

### Development Notes
- The app uses `@st.cache_data` for CSV loading to improve performance. Clear cache from the Streamlit menu if you update the CSV.
- PCA uses standardized features (`danceability`, `energy`, `valence`, `tempo`). Ensure they are numeric.

---

### License
This project is provided as-is for educational and research purposes. Add your preferred license if redistributing.


