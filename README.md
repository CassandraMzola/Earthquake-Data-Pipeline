# Earthquake Data Pipeline 🌍  

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) 
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white) 
![BigQuery](https://img.shields.io/badge/BigQuery-4285F4?style=for-the-badge&logo=googlebigquery&logoColor=white)

The **Earthquake Data Pipeline** automatically collects live earthquake data from the USGS (United States Geological Survey) and stores it in Google BigQuery. This enables both **real-time and historical analysis** of earthquakes for research, reporting, or data projects.

---

## 🧩 Pipeline Overview

**Pipeline Components**  

- **Python Script:** `src/earthquake_project.py` – fetches, cleans, and uploads earthquake data.  
- **Jupyter Notebook:** `src/earthquake_project.ipynb` – exploration and testing.  
- **Dependencies:** Listed in `requirements.txt`.  

**Data Source**  

- **API:** USGS Earthquake GeoJSON Feed  
- **Frequency:** Hourly (can be scheduled via GitHub Actions or other schedulers)  
- **Data Collected:** Timestamp, location, magnitude, longitude, latitude, depth  

**BigQuery Storage**  

- **Project ID:** `earthquake-project-469810`  
- **Dataset:** `earthquake_dataset`  
- **Table:** `earthquakes`  
- **Upload Mode:** Append (new records added each run)  

**Public Access**  

The dataset is publicly accessible for anyone to query.  

**Full Table Path:**  
earthquake-project-469810.earthquake_dataset.earthquakes

pgsql
Copy code

**Example Query:**  
```sql
SELECT timestamp, location, magnitude, depth
FROM `earthquake-project-469810.earthquake_dataset.earthquakes`
WHERE magnitude >= 5
ORDER BY timestamp DESC
LIMIT 50;
⚙️ Requirements
Python packages (install via requirements.txt):

pandas

requests

google-cloud-bigquery

pandas-gbq

🚀 Usage
Clone the repository

bash
Copy code
git clone https://github.com/CassandraMzola/Earthquake-Data-Pipeline.git
cd Earthquake-Data-Pipeline
Set up Google Cloud credentials

bash
Copy code
export GOOGLE_APPLICATION_CREDENTIALS="path/to/your/key.json"
Install dependencies

bash
Copy code
pip install -r requirements.txt
Run the pipeline

bash
Copy code
python src/earthquake_project.py
Optional: Automate

Use GitHub Actions or any scheduler to run at your desired frequency (e.g., hourly).

Workflow checks out the repo, installs dependencies, and runs the script automatically.

📁 Folder Structure
css
Copy code
Earthquake-Data-Pipeline/
├── src/
│   ├── earthquake_project.py
│   └── earthquake_project.ipynb
├── requirements.txt
└── README.md
🎯 Purpose & Impact
Provides up-to-date earthquake data for researchers, journalists, or analysts.

Enables historical analysis of seismic trends.

Demonstrates data pipeline automation and cloud integration using BigQuery.

📬 Connect With Me
GitHub: CassandraMzola

Portfolio: cassandramzola.vercel.app

Email: cassandramzola@gmail.com

Made with Python, BigQuery, and a love for turning data into action! 🚀
