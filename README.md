<h1 align="center">Wildfire Detection System 🔥</h1>

<div align="center">
   
[![Python](https://img.shields.io/badge/Python-3.10.13-blue.svg?logo=python)](https://www.python.org/downloads/release/python-31013/)
[![Flask](https://img.shields.io/badge/Flask-3.0.3-lightgrey.svg?logo=flask)](https://flask.palletsprojects.com/en/3.0.x/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.16.1-orange.svg?logo=tensorflow)](https://www.tensorflow.org/)
[![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)](https://github.com/username/repo)

</div>

![Wildfire](https://medforest.net/wp-content/uploads/2019/03/forest-fire-2268725_1280.jpg)

## Table of Contents 📚

1. [Background on Wildfires 🌍](#background-on-wildfires-)
2. [Project Overview 🚀](#project-overview-)
3. [Features 🌟](#features-)
4. [Screenshot 📸](#screenshot-)
5. [Installation 🛠️](#installation-%EF%B8%8F)
6. [Usage 💻](#usage-)
7. [File Structure 📁](#file-structure-)
8. [Requirements 📦](#requirements-)
9. [Improvements ✨](#improvements-)
10. [Contributing 🤝](#contributing-)
11. [License 📜](#license-)

---

## Background on Wildfires 🌍

Wildfires pose a significant environmental and economic threat worldwide. Their frequency and intensity have been escalating due to various factors, particularly climate change.

### Key Facts:

- **Global Impact**: Wildfires have caused devastating damage across various regions, from the Amazon Rainforest to Australia. In 2020, wildfires in California alone burned over 4.2 million acres.
- **Frequency**: Over 100,000 wildfires occur annually in the U.S. alone.
- **Economic Impact**: Wildfires cause an estimated $5 billion in damage annually in the U.S.
- **Climate Change**: Rising global temperatures and drier conditions are significantly increasing the risk and severity of wildfires.

These alarming statistics underscore the urgent need for efficient wildfire detection and monitoring systems. Our **Wildfire Detection System** aims to address this need by leveraging cutting-edge technologies and data-driven models.

## Project Overview 🚀

This project presents an innovative solution combining satellite imagery, camera feeds, and weather data to predict the risk of wildfires. Using advanced deep learning techniques, our system performs robust feature extraction and classification to detect potential fire events early.

Our models include:
- **Satellite Classification CNN**: Using ResNet50v2, this model detects wildfire probabilities from satellite images with an accuracy of 97%.
- **Image Classification CNN**: Also based on ResNet50v2, this model identifies fires in uploaded images with an accuracy of 98%.
- **Weather Data Model**: This model predicts wildfire risks from meteorological data with an accuracy of 100%, albeit on a limited dataset.

## Features 🌟

- **Satellite Detection**: Detect wildfires using high-resolution satellite imagery.
- **Camera Detection**: Identify wildfire outbreaks through analysis of images from cameras or drones.
- **Weather Prediction**: Predict wildfire risks based on current and forecasted weather conditions.
- **Alert System**: Receive hourly email alerts about wildfire risks in specified locations.

## Screenshot 📸

Here's a glimpse of the Wildfire Detection System interface:

![Screenshot](src/static/images/Screenshot.png)

## Installation 🛠️

Follow these steps to set up the project locally:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/realOmSahu/Wildfire-Detection
   cd Wildfire-Detection
   ```

2. **Create a virtual environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

   Make sure to run the Jupyter notebooks for model training and saving on Kaggle:
   - Open `wildfire-camera-detection.ipynb` and `wildfire-satellite-detection.ipynb` in Kaggle Notebooks to train and save the respective models.

4. **Set up environment variables**:
   Create a `.env` file and add your Mapbox token and other necessary configurations:
   ```bash
   MAPBOX_TOKEN=your_mapbox_token
   MAILERSEND_KEY=your_mailersend_key
   ```

5. **Initialize the database**:
   ```bash
   python -c 'from src.app import init_db; init_db()'
   ```

6. **Run the application**:
   ```bash
   python src/app.py
   ```

## Usage 💻

Once the application is running, navigate to the homepage to explore the features:

- **Home**: Overview and introduction to the system.
- **Camera Detection**: Upload images for wildfire detection.
- **Satellite Detection**: Analyze satellite data for wildfire hotspots.
- **Alert Service**: Subscribe for wildfire alerts for specific geographic areas.

## File Structure 📁

```bash
.
├── LICENSE  # Project license
├── README.md  # You're here!
├── alerts.db  # Database file for alerts
├── requirements.txt  # List of dependencies
├── analysis  # Analysis and model files
│   ├── meteorological-detection-classification.ipynb  # Notebook for weather-based detection
│   ├── wildfire-camera-detection.ipynb  # Notebook for camera image detection
│   ├── wildfire-satellite-detection.ipynb  # Notebook for satellite image detection
│   ├── meteorological-detection-classification.keras  # Saved weather detection model
│   ├── std_scaler_weather.pkl  # Scaler for weather data
│   ├── wildfire_camera_detection_model.keras  # Saved camera detection model
│   └── wildfire_satellite_detection_model.keras  # Saved satellite detection model
├── src  # Source code directory
│   ├── app.py  # Main application file
│   ├── camera_functions.py  # Functions for camera image processing
│   ├── email_alert.py  # Functions for sending email alerts
│   ├── meteorological_functions.py  # Functions for weather data processing
│   ├── satellite_functions.py  # Functions for satellite image processing
│   ├── static  # Static files (JS, images)
│   │   ├── js  # JavaScript files
│   │   │   ├── alert_map.js  # JS for alert map
│   │   │   ├── camera.js  # JS for camera detection page
│   │   │   └── map.js  # JS for satellite detection map
│   │   ├── images  # Image files
│   │   │   └── Screenshot.png  # Screenshot of the application
│   └── templates  # HTML templates
│       ├── alert.html  # Template for alert page
│       ├── base.html  # Base template
│       ├── detect_camera.html  # Template for camera detection page
│       ├── detect_satellite.html  # Template for satellite image detection
│       └── home.html  # Template for homepage
```

## Requirements 📦

- **Python 3.10.13**
- **Flask 3.0.3**
- **TensorFlow 2.16.1**
- **Pandas 2.2.2**
- **Scikit-Learn 1.5.0**
- **Mailersend 0.5.6**
- **OpenMeteo SDK 1.11.7**

For the full list of dependencies, see the [requirements.txt](requirements.txt) file.

## Improvements ✨

Future enhancements could further improve the effectiveness of the Wildfire Detection System:

- **Diverse Datasets**: Integrating datasets from various regions would improve the system’s global applicability.
- **Data Quantity and Quality**: Expanding the amount and quality of training data can enhance model accuracy.
- **Advanced Algorithms**: Implementing more sophisticated machine learning algorithms could improve detection precision.
- **Real-Time Processing**: Enhancing the system to process data in real-time would provide faster alerts and responses.
- **User Interface**: Improving the UI/UX for easier navigation and interaction.

## Contributing 🤝

We welcome contributions from the community! Please read our [Contributing Guidelines](CONTRIBUTING.md) to get started. Here’s how you can contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a Pull Request (PR) using our [PR Template](.github/PULL_REQUEST_TEMPLATE.md).

For reporting bugs or suggesting features, please use our [Issue Templates](.github/ISSUE_TEMPLATE/bug_report.md).

## License 📜

This project is licensed under the Apache 2.0 License. See the [LICENSE](LICENSE) file for more information.
