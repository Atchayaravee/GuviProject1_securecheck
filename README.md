# GuviProject1_securecheck
🚓 SecureCheck

**SecureCheck** is a data analysis and visualization dashboard built using **Streamlit**, **MySQL**, and **Python (Pandas)** to monitor, analyze, and visualize police traffic stop records and related activities such as searches, arrests, and violations. It is designed to help law enforcement agencies or analysts ensure accountability, improve efficiency, and detect patterns in police stop-and-search behavior.

---

# Dataset

traffic_stopsdb - traffic_stops_raw.csv - uncleaned_data

police_stops.csv - cleaned_data


## 📁 Project Structure

Police_SecureCheck/
├── db_conn.ipynb # Jupyter notebook for data preprocessing
├── strmlitapp.py # Streamlit dashboard application
├── requirements.txt # List of Python dependencies
├── police_stops.csv # Raw dataset (CSV format)
└── README.md # Project documentation
## Create virtual environment

python -m venv env
source env/bin/activate        # On Windows: env\Scripts\activate

## install dependencies

pip install -r requirements.txt

Set Up MySQL Database

## Create a database named Securelogs

Import the cleaned data using the provided .csv or from the Streamlit UI 


Update your MySQL credentials in streamlit_app.py:


engine = create_engine("mysql+pymysql://root:root@localhost/traffic_stopsdb")

## Run the streamlit app

streamlit run strmlitapp.py

## Sample querirs
-- Top 10 vehicles involved in drug-related stops



SELECT vehicle_number, COUNT(*) AS drug_stop_count
FROM police_stops
WHERE drugs_related_stop = 1 
GROUP BY vehicle_number 
ORDER BY drug_stop_count DESC 
LIMIT 10;

## 🙋‍♂️ Author
Atchaya S R

## 📜 License
This project is licensed under the MIT License.
