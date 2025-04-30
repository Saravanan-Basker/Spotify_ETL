🎧 Spotify Artist ETL & Analytics Tracker

This project performs automated data extraction and analytics on a list of Spotify artist profiles. It is designed as an end-to-end ETL pipeline that fetches artist and track data, stores it in structured format, and provides useful insights and visualizations.

📌 Project Overview
The goal of this project is to:

Collect data from Spotify artist pages
Extract information on top tracks, popularity, and album metadata
Track analytics over time
Visualize metrics like track popularity, followers, and track features


📊 Features

🔗 Supports tracking multiple artist pages via URLs (track_urls.txt)
🛠️ ETL (Extract, Transform, Load) pipeline implemented in Python (Jupyter Notebook)
📈 Visualizations of artist metrics and top tracks
📂 Exported clean dataframes for further analysis
✅ Avoids duplicate records during periodic tracking
🔄 Easily extendable to schedule via Airflow or CRON for periodic tracking


📁 Files

File	Description
ETL&Track_Analytics.ipynb	Main Jupyter notebook for ETL and analytics
track_urls.txt	List of Spotify artist URLs to track
output/ (optional)	Folder for storing CSVs, graphs, and visualizations


⚙️ How It Works

Extract: Load URLs from track_urls.txt and fetch data via Spotify's Web API using spotipy.
Transform: Normalize JSON data into pandas DataFrames.
Load: Display data, export to CSV, or store in a database.
Analyze: Generate visualizations for:
Most popular tracks
Artist followers and popularity
Track: Optionally run at intervals to track changes over time.


🔧 Requirements

Python 3.8+
spotipy
pandas
matplotlib / seaborn
Jupyter Notebook


✅ MySQL Integration 
This project also integrates with MySQL to persist artist and track data after transformation. This enables:

Structured data storage
Easy querying using SQL
Historical tracking and dashboarding

🔗 The pipeline stores:

Artist details
Track metadata


FLow Diagram:

                           +-------------------------+
                           |   track_urls.txt File   |
                           +-----------+-------------+
                                       |
                                       v
                          +------------+------------+
                          |   Jupyter Notebook      |
                          |  (ETL&Track_Analytics)  |
                          +------------+------------+
                                       |
       +-------------------------------+-------------------------------+
       | Extract via Spotipy API                                       |
       v                                                               v
+--------------+      +---------------------+         +--------------------------+
| Artist Data  | ---> | Top Tracks Metadata |  --->   | Audio Features (Track)  |
+--------------+      +---------------------+         +--------------------------+
       \____________________     |     _________________________/
                                v
                   +---------------------------+
                   |   Transform with Pandas   |
                   +---------------------------+
                                |
                                v
                   +---------------------------+
                   |   Load into MySQL DB      |
                   +---------------------------+
                                |
                                v
            +----------------------------------------+
            | Visualize & Analyze (Matplotlib/Seaborn)|
            +----------------------------------------+














