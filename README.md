# 🚀 TOPSIS Web Service

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-Web%20Framework-lightgrey?logo=flask)
![Render](https://img.shields.io/badge/Deployed%20on-Render-purple?logo=render)

A lightweight, user-friendly web application that calculates the **TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution)** score for multi-criteria decision analysis. Users can upload their datasets, define criteria, and receive the computed results directly in their inbox.

---

## 🌐 Live Demo
Access the live web application here: **[[Cick Here](https://topsis-raj.onrender.com)]**

*(Note: This service is hosted on a free Render tier. If it hasn't been accessed recently, it may take 1-2 minutes to "wake up" upon your first visit).*

---

## ✨ Features
* **File Upload:** Securely upload CSV datasets.
* **Dynamic Parameter Input:** Accepts custom weights and impacts (positive/negative) for each column.
* **Automated Processing:** Computes the TOPSIS score and ranks the alternatives instantly.
* **Email Delivery:** Automatically emails the final `.csv` result file to the user-provided email address using secure SMTP.
* **Input Validation:** Ensures the number of weights, impacts, and criteria columns match perfectly before processing.

---

## 🧮 How TOPSIS Works
The application evaluates alternatives based on the following mathematical steps:

1. **Vector Normalization:**
   $$r_{ij} = \frac{x_{ij}}{\sqrt{\sum_{k=1}^{m} x_{kj}^2}}$$

2. **Weight Assignment:**
   $$v_{ij} = r_{ij} \times w_j$$

3. **Ideal Best ($V^+$) and Ideal Worst ($V^-$) Calculation:**
   Identifies the maximum and minimum values based on the assigned impacts (`+` or `-`).

4. **Euclidean Distance:**
   Calculates the separation from the ideal best ($S^+$) and ideal worst ($S^-$).

5. **Performance Score:**
   $$P_i = \frac{S_i^-}{S_i^+ + S_i^-}$$
   
   *The final rank is determined by sorting* $P_i$ *in descending order.*

---

## 📝 Usage Guide

To use the live web service, follow these steps on the main page:

1. **Input File:** Upload a valid `.csv` file. The first column should contain object names, and all subsequent columns must be purely numeric.
2. **Weights:** Enter a comma-separated list of numeric weights (e.g., `1,1,1,2,1`).
3. **Impacts:** Enter a comma-separated list of `+` and `-` signs (e.g., `+,+,-,+,+`).
4. **Email:** Provide a valid email address where the results should be sent.
5. Click **Submit**. Check your inbox after a few seconds!

---

## 💻 Local Setup & Installation

If you wish to run this web service locally on your machine, follow these steps:

### 1. Clone the Repository
```bash
git clone [https://github.com/Raaaj2005/Topsis-Web-Service.git](https://github.com/Raaaj2005/Topsis-Web-Service.git)
cd Topsis-Web-Service
```

### 2. Install Dependencies
Ensure you have Python installed, then run:
```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables
To enable the email functionality locally, you must set up your sender credentials. Set your Gmail App Password as an environment variable:

**Windows:**
```cmd
set EMAIL_PASSWORD=your_16_digit_app_password
```
**Mac/Linux:**
```bash
export EMAIL_PASSWORD="your_16_digit_app_password"
```

### 4. Run the Server
```bash
python app.py
```
The application will be accessible at `http://127.0.0.1:5000`.

---

## 📂 Repository Structure

| File/Folder | Purpose |
| :--- | :--- |
| `app.py` | Main Flask application and TOPSIS logic backend. |
| `templates/` | Contains the HTML structure (`index.html`) for the frontend UI. |
| `requirements.txt` | Lists all necessary Python dependencies (Flask, pandas, gunicorn, etc.). |
| `Procfile` | Configuration file for Render/Heroku deployment. |

---

## 👤 Author
Name: **Raj** <br>
Roll Number: **102317090** 
