# 🌆 CityPulse: Real-Time Urban Anomaly Detector

CityPulse is a smart city simulation and anomaly detection system that monitors urban patterns using multi-dimensional sensor data. It flags anomalies like sudden traffic surges, abnormal silence, or pollution spikes — helping us understand when a city behaves unusually.

## 🚀 Project Overview

This project simulates a real-world urban monitoring platform by integrating various city signals such as:

- 🚗 Traffic density  
- 🔊 Noise levels  
- 🌫️ Air pollution (PM2.5 & PM10)  
- ⚡ Power usage  
- 🚶‍♂️ Foot traffic  
- 📍 Location (latitude & longitude)  
- ⏰ Time features (hour of day, day of week)

The goal is to **detect anomalies** in real-time-like data and cluster unusual events (e.g., festival, protest, accident).

## 📊 Why I Created My Own Dataset

While public APIs exist for real-world data, they are often:

- **Inconsistent** across cities or formats  
- **Rate-limited** or behind paywalls  
- **Lacking granularity** (e.g., neighborhood-level noise)

So, I **curated a synthetic dataset** using distributions and values inspired by real APIs. This gave me full control to:

- Inject meaningful anomalies  
- Simulate city-scale data across 100 zones  
- Prototype freely without API restrictions

## 📡 Referenced APIs & Data Sources

| Sensor Type        | Source / API                                                                                                               | Notes                                          |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| 🛣️ Traffic        | [HERE API](https://developer.here.com/), [TomTom](https://developer.tomtom.com/), Mumbai Traffic Police (Twitter scraping) | Real-time vehicle speed, congestion            |
| 🌫️ Air Quality    | [OpenAQ](https://docs.openaq.org/), [IQAir API](https://www.iqair.com/air-pollution-data-api)                             | PM2.5, NO₂, etc. for Indian cities             |
| 🔊 Noise Levels    | [NoiseTube](http://www.noisetube.net/), or simulated                                                                       | Very rare; simulated decibel levels            |
| 🚶‍♂️ Foot Traffic | Google Mobility Reports (CSV), [Strava Metro (sim)](https://metro.strava.com/)                                            | Daily footfall % in zones                      |
| ⚡ Electricity Load| [MERIT India](https://meritindia.in/dashboard), or simulated                                                               | Power usage by grid or zone                    |
| 🌡️ Temperature    | [OpenWeather API](https://openweathermap.org/api)                                                                          | Localized weather data by lat-long             |

## 📁 Dataset Structure

A CSV named `simulated_urban_sensor_data.csv` contains:

| Column Name      | Description                          |
|------------------|--------------------------------------|
| `timestamp`       | Time of observation (hourly)         |
| `zone`            | Sector name (e.g., "Sector 78")      |
| `traffic_density` | Cars/hour in that zone               |
| `noise_level`     | Ambient sound level in decibels      |
| `pm2_5`           | Fine particle air pollution (µg/m³)  |
| `pm10`            | Coarse particle air pollution (µg/m³)|
| `power_usage`     | Electricity use in kWh               |
| `foot_traffic`    | Number of people passing per hour    |
| `lat`, `lon`      | Zone geolocation                     |

## 🧠 What This Project Does

- Simulates 100 city zones over a 30-day period (hourly resolution)  
- Injects realistic anomalies (e.g., noise drop, traffic spikes)  
- Builds baseline behavior models using time and zone  
- Applies **Isolation Forests** and **DBSCAN** to detect anomalies  
- Clusters anomalies to summarize events: protest, accident, blackout  
- Generates alert messages and interactive dashboards

## 📊 Visuals & Analytics

- 📈 Line charts for sector-wise trends  
- 🗺️ PyDeck map showing zone traffic density  
- 📌 Clustered anomaly events  
- ⚠️ Alerts like:  
  `🛑 Alert: Abnormal patterns detected in Sector 12`

## 🛠️ Tech Stack

- **Python:** Data simulation & modeling  
- **Pandas, NumPy:** Data wrangling  
- **Scikit-learn:** Isolation Forest, DBSCAN  
- **Matplotlib, PyDeck:** Visualization  
- **Jupyter Notebook:** Development environment  

## 📌 Next Steps

- Replace synthetic data with live API feeds  
- Add new sensor types (weather, water usage)  
- Build a web dashboard using Streamlit or Dash  
- Extend anomaly detection logic with LSTM or Autoencoders

## 🤝 Contributing

If you're passionate about smart cities, real-time anomaly detection, or urban analytics — feel free to fork and build upon this project!

## 📫 Contact

Made with 💡 by Mridul Gupta 
Reach out via [LinkedIn](https://linkedin.com/in/mridul--gupta) 
