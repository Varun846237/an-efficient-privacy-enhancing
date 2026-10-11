An Efficient Privacy-Enhancing Cross-Silo Federated Learning System

A Python and Django-based web application designed to implement privacy-preserving machine learning and secure data processing across decentralized environments without exposing sensitive underlying data.

📌 Project Overview
In traditional centralized machine learning, sensitive data must be collected in a single location, creating significant privacy and security risks. This project addresses those concerns by implementing a privacy-enhancing framework that processes datasets securely while supporting machine learning classification and analysis.

 Key Features
* Privacy-Preserving Data Processing: Integrates privacy-enhancing mechanisms to protect sensitive data attributes during machine learning tasks.
* Role-Based Workflows:
  * Remote User (`Remote_User`): Interface for users to interact with the system, submit queries, and view processed outputs.
  * Service Provider (`Service_Provider`):Administrative and operational module managing underlying data models and processing workflows.
* Machine Learning & Dataset Analysis: Evaluates labeled data (`Datasets.csv`, `Labeled_Data.csv`) for predictive accuracy and classification.
* Interactive Web Interface: Built using Django templates for responsive UI interactions.


🛠️ Tech Stack & Requirements
* Backend Framework: Python 3.8+, Django
* Frontend: HTML5, CSS3, JavaScript (Django Templates)
* Data Processing & ML: Pandas, NumPy, Scikit-learn
* Database: SQLite (default development database)


📂 Project Structure
an-efficient-privacy-enhancing/
├── an_efficient_privacy_enhancing/  # Core Django configuration (settings.py, urls.py, wsgi.py)
├── Remote_User/                      # Module handling remote user logic & interactions
├── Service_Provider/                 # Module handling service provider functions & model management
├── Template/                         # Frontend HTML template files
├── Datasets.csv                      # Main training dataset
├── Labeled_Data.csv                  # Preprocessed / labeled evaluation dataset
├── manage.py                         # Django administrative utility script
├── run.bat                           # Batch execution script for quick local startup
└── .gitignore                        # Git exclusion file (ignores venv, db.sqlite3, cache)

 🚀 Setup & Installation
 Clone the Repository:
 git clone [https://github.com/Varun846237/an-efficient-privacy-enhancing.git](https://github.com/Varun846237/an-efficient-privacy-enhancing.git)
cd an-efficient-privacy-enhancing
 Create and Activate a Virtual Environment:
 python -m venv venv
venv\Scripts\activate   # (On Windows)
 Install Required Packages:
 pip install django pandas numpy scikit-learn
 Apply Database Migrations:
 python manage.py makemigrations
 python manage.py migrate
 Run the Development Server:
 python manage.py runserve
