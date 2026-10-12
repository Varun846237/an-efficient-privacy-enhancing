An Efficient Privacy-Enhancing Cross-Silo Federated Learning for False Data Injection Attack Detection in Smart Grids

 1. Project Overview

This project is associated with the study of false data injection attack detection in smart-grid environments, with an emphasis on machine learning, data security, and privacy-aware system design.

The current repository contains a Python and Django web application that provides a classification workflow for data labelled as either `0` or `1`. The inspected implementation uses text feature extraction and multiple machine-learning classifiers to generate predictions and evaluate classification performance.

The broader research topic explores cross-silo federated learning, where multiple participants can collaboratively develop machine-learning models without directly sharing their raw data.

 2. Project Objectives

- Explore machine-learning approaches to classification and attack-detection problems.
- Develop a Django-based application for submitting data and displaying classification predictions.
- Compare the performance of multiple machine-learning classifiers.
- Examine evaluation measures such as accuracy, confusion matrices, and classification reports.
- Study the role of data privacy and secure collaborative learning in sensitive application domains.
- Identify the implementation and validation work required to connect a research framework with a reproducible software system.

 3. Current Implementation

The inspected code includes the following components:

| Component | Implementation |
|---|---|
| Web framework | Django |
| Data handling | Pandas and NumPy |
| Feature extraction | Scikit-learn `CountVectorizer` |
| Naive Bayes | `MultinomialNB` |
| Support Vector Machine | `LinearSVC` |
| Logistic Regression | `LogisticRegression` |
| Decision Tree | `DecisionTreeClassifier` |
| Random Forest | `RandomForestClassifier` |
| SGD classifier | `SGDClassifier` with hinge loss |
| Ensemble prediction | `VotingClassifier` combining five classifiers |
| Evaluation | Accuracy, confusion matrix, and classification report |
| Data storage | MySQL configured in Django settings |
| Interface | Django templates with HTML, CSS, and JavaScript |

The service-provider workflow trains and evaluates the individual classifiers. The remote-user prediction workflow trains the five-model voting ensemble and uses it to generate a prediction from submitted text.

Note:The listed implementation reflects the inspected Python source files. It does not establish that the application has been tested successfully in every environment or that the reported classification results are reproducible.

 4. Current Machine-Learning Workflow

The inspected training and prediction code follows this general workflow:

1. Load the dataset from `Datasets.csv`.
2. Read the `Label` column and map its values to the corresponding binary classes.
3. Extract the `Body` field as the input text.
4. Transform the text into numerical features using `CountVectorizer`.
5. Split the data into training and testing sets using an 80:20 ratio.
6. Train and evaluate individual classifiers.
7. Calculate accuracy, confusion matrices, and classification reports.
8. In the remote-user workflow, combine five classifiers using a `VotingClassifier`.
9. Generate a prediction for the submitted text and display the result through the Django interface.
10. Store prediction information and make relevant results available through the application.

The current implementation uses text-based features. Therefore, the presence of the project's smart-grid title alone should not be interpreted as evidence that the application has been evaluated on electrical measurements or a verified smart-grid dataset.

5. Research Context and Scope

The broader research topic concerns privacy-aware collaborative learning for false data injection attack detection in smart grids.

Research concepts associated with this topic include:

- Cross-silo federated learning.
- Local model training across participating data silos.
- Model aggregation.
- Secure aggregation.
- Differential privacy.
- Homomorphic encryption.
- Data preprocessing and class-imbalance handling.
- Anomaly detection and evaluation on suitable datasets.

These concepts require separate implementation and verification. In the currently inspected repository, I did not find sufficient evidence to establish a complete cross-silo federated-learning pipeline, secure aggregation, differential privacy, homomorphic encryption, or SMOTE as implemented features.

They are therefore documented here as research context or potential future work, not as verified capabilities of the current application.

6. Technology Stack

- Programming language: Python
- Web framework: Django
- Machine learning: Scikit-learn
- Data processing: Pandas and NumPy
- Feature extraction: CountVectorizer
- Database: MySQL, as configured in `settings.py`
- Frontend: HTML, CSS, JavaScript, and Django templates
- Dataset format: CSV

 7. Repository Structure

The main project components include:

an-efficient-privacy-enhancing/
├── an_efficient_privacy_enhancing/
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── Remote_User/
│   ├── views.py
│   └── models.py
├── Service_Provider/
│   └── views.py
├── Template/
├── Datasets.csv
├── manage.py
├── run.bat
└── README.md


This is an overview of the principal files and directories. Other application files, templates, and configuration files may also be present in the repository.

8. Installation and Setup

Prerequisites

Install the following before running the application:

- Python compatible with the project's Django and Scikit-learn dependencies.
- pip.
- MySQL Server.
- Git.

 Step 1: Clone the repository


git clone https://github.com/Varun846237/an-efficient-privacy-enhancing.git
cd an-efficient-privacy-enhancing


 Step 2: Create a virtual environment

python -m venv venv


On Windows:


venv\Scripts\activate


Step 3: Install dependencies

python -m pip install --upgrade pip
pip install django pandas numpy scikit-learn xlwt mysqlclient


If installation fails because of a dependency or version incompatibility, resolve that issue and record the tested package versions in a `requirements.txt` file.

Step 4: Configure MySQL

The current Django settings specify a MySQL database named `an_efficient_privacy_enhancing`.

Create the database in MySQL:


CREATE DATABASE an_efficient_privacy_enhancing
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;

Configure the database name, username, password, host, and port in the project's Django settings to match your local MySQL installation.

Do not publish database passwords, production secret keys, or other sensitive credentials in the repository.

Step 5: Apply database migrations

python manage.py makemigrations
python manage.py migrate


Step 6: Start the development server

python manage.py runserver

Open the local address displayed by Django in your terminal.

Setup note:These are the expected setup steps based on the inspected configuration. Successful execution may require additional dependency fixes or local configuration. The application should be tested from a clean environment before the instructions are treated as verified.

 9. Dataset and Reproducibility

The inspected implementation reads `Datasets.csv` and expects the `Body` and `Label` columns for its classification workflow.

Before publishing experimental results, document:

- The dataset's original source and licence.
- The meaning of each label and the target classification task.
- The number of records and the class distribution.
- The preprocessing steps and feature-extraction configuration.
- The training and testing procedure.
- The software and dependency versions.
- The evaluation results for each classifier.

The source and domain of the dataset must be verified before describing it as a smart-grid dataset. Do not publish invented dataset details or unverified performance figures.

10. Current Limitations

The current implementation has several limitations that should be considered when interpreting its results:

- The inspected feature-extraction workflow is based on text rather than a demonstrated electrical-measurement pipeline.
- The code does not currently demonstrate independent training across multiple federated data silos.
- A model-aggregation process for federated learning has not been established in the inspected source.
- Secure aggregation, differential privacy, homomorphic encryption, and SMOTE have not been verified as implemented.
- Experimental results need reproducible testing and documentation.
- Database configuration and development security settings require review before deployment.

These limitations define the difference between the current software implementation and the broader research objectives.

11. Future Work

Potential future work includes:

1. Obtaining and documenting an appropriate, licensed smart-grid dataset with clearly defined false data injection attack labels.
2. Implementing local model training across multiple simulated data silos.
3. Developing and validating a federated model-aggregation mechanism.
4. Investigating secure aggregation and differential privacy, with explicit descriptions of their threat models and limitations.
5. Evaluating appropriate data-preprocessing and class-imbalance techniques where justified by the dataset.
6. Comparing models using accuracy, precision, recall, F1-score, and ROC-AUC where applicable.
7. Repeating experiments with reproducible splits, random seeds, and documented configurations.
8. Measuring model performance and communication costs across centralized and federated baselines.
9. Improving application security, configuration management, and automated testing.

These items are proposed extensions and should not be interpreted as completed functionality.

 12. Academic Integrity and Project Scope

This repository documents the current Django-based classification application and its inspected machine-learning workflow. The broader project title reflects the research problem and intended privacy-aware direction. Any claim that federated learning or privacy-preserving mechanisms have been implemented must be supported by the corresponding source code, experimental results, and technical documentation.

The distinction between the current implementation, the research concepts studied, and future development is intentional. It helps ensure that the repository can be assessed accurately and that its technical claims remain verifiable.

 13. Author and Project Information

- Project title: An Efficient Privacy-Enhancing Cross-Silo Federated Learning and Applications for False Data Injection Attack Detection in Smart Grids
- Project type: Undergraduate team project
- Team size: Four members
- Repository: https://github.com/Varun846237/an-efficient-privacy-enhancing

This project provided an opportunity to explore machine learning, software development, model evaluation, and the challenges involved in translating a research idea into a verifiable application.
