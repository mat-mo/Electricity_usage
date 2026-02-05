# Electricity Usage Comparison Tool ⚡

A modern, privacy-first web application designed to help Israeli consumers analyze their electricity consumption and choose the most cost-effective provider.

**[View Live Version](https://mat-mo.github.io/Electricity_usage/)**

## 🌟 Features

- **Smart Meter Eligibility Checker**: Search by city, street, and house number to verify if a smart meter is installed or planned for installation in 2026.
- **CSV Consumption Analysis**: Upload your official usage data from the Israel Electric Corporation (IEC) for precise calculations.
- **Automated Plan Comparison**: Compares your actual usage against various market offers:
    - **Fixed Discount Plans**: (e.g., 5-7% off 24/7).
    - **Time-of-Use Plans**: (e.g., cheaper rates at night or during the day).
    - **Tiered Plans**: Plans that adjust based on consumption volume.
- **Interactive Visualizations**:
    - **Consumption Profile (Radar Chart)**: See your average usage patterns throughout the day.
    - **Daily Consumption (Bar Chart)**: Track your usage trends over time.
- **Privacy-First**: All data analysis is performed locally in your browser. Your consumption files and addresses are never uploaded to any server.
- **Modern UI/UX**: Built with Tailwind CSS, featuring a responsive design and full Dark Mode support.

## 🛠️ Technology Stack

- **Frontend**: HTML5, Vanilla JavaScript, [Tailwind CSS](https://tailwindcss.com/) (via CDN).
- **Data Parsing**: [PapaParse](https://www.papaparse.com/) for efficient client-side CSV processing.
- **Charts**: [Chart.js](https://www.chartjs.org/) for data visualization.
- **Backend (Build-time)**: Python for database sharding and processing.

## 📁 Project Structure

- `index.html`: The main application entry point and logic.
- `plans.json`: Configuration file containing all electricity provider plans and rates.
- `build_database.py`: Python script to generate the address database shards.
- `data/`: Contains sharded JSON files for cities and smart meter addresses.
- `iec_sources/`: Directory for raw data sources (ignored by git).

## 🚀 Build & Data Updates

The application uses a sharded database to keep the frontend lightweight. To update the smart meter address database:

### 1. Requirements
- Python 3.x
- `pandas` library

```bash
pip install pandas
```

### 2. Run the update script
The script will download the latest official address list, process it, and generate individual JSON files for each city in the `data/` directory.

```bash
python3 build_database.py
```

## 🧹 Maintenance & Housekeeping

### Updating Electricity Plans
When providers change their rates or introduce new plans:
1. Open `plans.json`.
2. Add or modify the plan objects.
3. The frontend will automatically reflect these changes upon the next reload.

### Deployment
This project is optimized for static hosting (e.g., GitHub Pages). To deploy:
1. Ensure all changes are committed.
2. Push to the relevant branch/remote:
   - **Beta**: `git push beta main`
   - **Production**: `git push prod main`

### Privacy Compliance
Ensure that no raw consumption files or PII (Personally Identifiable Information) are added to the repository. The `data/` directory should only contain public-domain address information regarding smart meter availability.

---
*Created and maintained by [mat-mo](https://github.com/mat-mo).*