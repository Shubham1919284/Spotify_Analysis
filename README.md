# 🎶 Spotify Top 50 World – Power BI Dashboard

This repository hosts my **Power BI** dashboard project analyzing Spotify’s Top 50 Global songs data.  
My goal: uncover trends in song popularity, albums, artists, and design a beautiful, Spotify-themed interactive dashboard.

---

## 🗂️ Dataset

The dataset includes (for each song/chart entry):  
- `song` — name of the track  
- `artist` — the performing artist  
- `date` — date when charted  
- `popularity` — Spotify’s popularity score (0–100)  
- `duration_ms` — track duration in milliseconds  
- `album_type` — e.g. single, album, compilation  
- `total_tracks` — number of tracks in that album  
- `release_date` — when the album or track was released  
- `is_explicit` — boolean indicating explicit content  

---

## 🧭 Dashboard Pages & Features

### 1. Overview  
- KPIs: Distinct songs, average popularity, number of artists, average duration  
- Donut charts: album vs single, explicit vs non-explicit, songs by year, avg popularity by album type  
- Slicer for switching between **Month** & **Quarter** views

### 2. Songs  
- Ranking of top songs by popularity  
- Distinct songs per artist, position-1 hits  
- Table with columns: year, album type, avg & max popularity, duration

### 3. Artists  
- Artists with the most charting songs  
- Total popularity per artist  
- Position1 hits per artist  
- Album-level stats: count, avg tracks, popularity

---

## 📊 Key Insights

- **2024 leads**: 2024 charts contribute ~51.6% versus 48.3% from 2023  
- **Albums dominate**: ~66.9% of tracks are from albums, not singles  
- **Explicit vs Non-explicit**: Non-explicit ~60%, explicit ~40%  
- **Top Artists**: Taylor Swift leads with 85 distinct songs; Travis Scott, Drake also strong performers  
- **Seasonal Popularity**: Peaks in July–August — summer releases appear to drive streaming traction  

---

## 🛠 Technical & Measures

Here’s a subset of important DAX measures (defined inside a `_Measures` table) used in this dashboard:

```DAX
MEASURE '_Measures'[Total Songs] = COUNTROWS('Top-50-world')
MEASURE '_Measures'[Distinct Artists] = DISTINCTCOUNT('Top-50-world'[artist])
MEASURE '_Measures'[Avg Popularity] = AVERAGE('Top-50-world'[popularity])
MEASURE '_Measures'[Best Position] = MIN('Top-50-world'[position])
MEASURE '_Measures'[Oldest Release Year] = MINX('Top-50-world', YEAR('Top-50-world'[release_date]))
… (other measures as in project)
These are used in KPI cards, charts, and slicer logic (Month/Quarter switching).
```
---
🧰 Tech Stack & Tools
Power BI Desktop — for creating visuals & data model

DAX — used extensively for measures & filtering logic

Power Query / M — for data preprocessing

Custom dark Spotify-like theme (JSON)
---
Navigation buttons & UI design using bookmarks
--- 
📸 Screenshots
The following screenshots are included in this repo:

Page	Screenshot File	Preview 
| Home Page | Overview Page |  
|-----------|------------|  
| ![Home](https://github.com/Shubham1919284/Spotify_Analysis/blob/1a91c6020702277b1801ff0813ac452c1e25a7b6/Spotify_Analysis(1).png) | ![Index](https://github.com/Shubham1919284/Spotify_Analysis/blob/1a91c6020702277b1801ff0813ac452c1e25a7b6/Spotify_Analysis(2).png) |  
---
| Artists Page | Songs Page |  
|-----------------|----------------------|  
| ![Calculator](https://github.com/Shubham1919284/Spotify_Analysis/blob/1a91c6020702277b1801ff0813ac452c1e25a7b6/Spotify_Analysis(3).png) | ![Members](https://github.com/Shubham1919284/Spotify_Analysis/blob/1a91c6020702277b1801ff0813ac452c1e25a7b6/Spotify_Analysis(4).png) |  
---
🚀 How to Use / Run
Clone this repo:

```bash
Copy code
git clone https://github.com/Shubham1919284/Spotify_Analysis.git
```
```
Open the .pbit or .pbix file (whichever you used) in Power BI Desktop.
```
```
Interact with slicers and visuals; your measures and filters are already embedded.
```
---
👤 Author & Contact
Shubham Kumar Jha

- 🔗 [LinkedIn – Shubham Kumar Jha](https://www.linkedin.com/in/shubham-kumar-jha-1a2b3c)  
- 💻 [GitHub – Shubham1919284](https://github.com/Shubham1919284)
---
🏷️ Tags / Keywords
PowerBI, DataVisualization, Spotify, DAX, Analytics, Dashboard, BI, MusicData, DataStories
