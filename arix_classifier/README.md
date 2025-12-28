# arXiv Paper Classifier

An AI-powered web application that automatically classifies research papers into academic categories using machine learning. Built with **Flask** and **CatBoost**, achieving **87.56% classification accuracy**.

**Technologies:** Python, Flask, CatBoost


## Overview

The **arXiv Paper Classifier** is a full-stack web application designed to categorize research papers based on their title and abstract. It provides accurate predictions across multiple academic domains, complete with confidence scores, user authentication, history tracking, and an administrative dashboard.


## Features

### Machine Learning

* CatBoost-based classification model with 87.56% accuracy
* Hybrid feature engineering using TF-IDF and domain-specific keywords
* Top 5 category predictions with confidence percentages

### Application Functionality

* Classification across 5 academic domains
* User authentication with email verification
* Classification history tracking for each user
* Admin dashboard for user management and analytics

### User Experience

* Modern, responsive web interface
* Clean layout with smooth transitions and animations
* Email notifications via Flask-Mail


## Supported Academic Categories

| Category              | Description                                             |
| --------------------- | ------------------------------------------------------- |
| AI & Machine Learning | Artificial intelligence, neural networks, deep learning |
| Physics               | Theoretical, experimental, and applied physics          |
| Mathematics           | Pure and applied mathematics                            |
| Biology & Health      | Biological sciences, medical and health research        |
| Chemistry & Materials | Chemistry, materials science, and related fields        |


## Demo

### Main Classifier Interface

* Input paper title and abstract
* Receive instant classification results
* View confidence scores and top predictions
* Access classification history

### Admin Panel

* View all registered users and statistics
* Monitor total classifications
* Inspect user-specific classification history
* Delete non-admin users


## Technology Stack

### Backend

* Python 3.8+
* Flask
* SQLAlchemy
* Flask-Mail
* CatBoost
* Scikit-learn
* Joblib

### Frontend

* HTML5 / CSS3
* Vanilla JavaScript
* Google Fonts (Space Grotesk, Inter)

### Database

* SQLite (development)


## Prerequisites

* Python 3.8 or higher
* pip (Python package manager)
* Gmail account (for email verification)


## Installation

### Option 1: Use Pre-trained Model (Recommended)

Clone the repository:

```bash
git clone https://github.com/yourusername/arxiv-classifier.git
cd arxiv-classifier
```

Create and activate a virtual environment:

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate
```

Install dependencies:

```bash
pip install flask flask-sqlalchemy flask-mail catboost scikit-learn joblib numpy scipy werkzeug
```

Ensure the following files are present in the root directory:

* `catboost_hybrid.cbm`
* `vectorizer.pkl`
* `keywords.pkl`

Configure email settings in `app.py`:

```python
app.config['MAIL_USERNAME'] = 'your-email@gmail.com'
app.config['MAIL_PASSWORD'] = 'your-app-password'
app.config['MAIL_DEFAULT_SENDER'] = 'your-email@gmail.com'
```

Initialize the database and start the application:

```bash
python app.py
```

This will create the SQLite database and a default admin account.


### Option 2: Train Your Own Model (Advanced)

A Google Colab notebook is provided for custom training.

Training steps:

1. Load the arXiv metadata dataset
2. Create a balanced dataset (default: 3,000 papers per category)
3. Clean and preprocess text
4. Train a CatBoost classifier using hybrid features
5. Export trained model files

Generated files:

* `catboost_hybrid.cbm`
* `vectorizer.pkl`
* `keywords.pkl`

Replace the existing model files in the project root and restart the application.

Expected training time: **6–8 minutes**


## Usage

Start the application:

```bash
python app.py
```

Access the application at:

```
http://127.0.0.1:5000
```

### Default Admin Credentials

* Username: `admin`
* Password: `admin123`
* Email: `admin@example.com`

**Important:** Change the admin password after first login.


## Project Structure

```
arxiv-classifier/
│
├── app.py
├── catboost_hybrid.cbm
├── vectorizer.pkl
├── keywords.pkl
├── arxiv_classifier.db
│
├── templates/
│   ├── home.html
│   ├── about.html
│   ├── aboutus.html
│   ├── signup.html
│   ├── login.html
│   ├── classifier.html
│   └── admin.html
│
├── notebooks/
│   └── model_training.ipynb
│
└── README.md
```


## Security Features

* Password hashing using Werkzeug
* Email verification before account activation
* Session-based authentication
* Role-based access control (Admin / User)
* SQL injection protection via SQLAlchemy ORM


## Deployment Recommendations

* Set a secure secret key
* Use a production database (PostgreSQL or MySQL)
* Disable debug mode
* Deploy using Gunicorn
* Enable HTTPS
* Implement rate limiting and CSRF protection


## Team

### Research

* Seetharama Kartheek
* Shaik Sameed

### Design

* K. Sri Akshaya
* P. V. Sai Tejaswi

### Engineering

* Karani Sumana Sree


## Contact

Email: **[sameedsks999@gmail.com](mailto:sameedsks999@gmail.com)**


## License

This project is licensed under the **Creative Commons Attribution–NoDerivatives (CC BY-ND)** license. See the LICENSE file for details.


## Acknowledgments

* arXiv.org for providing the research dataset
* CatBoost development team
* Flask open-source community


## Known Issues

* Email verification requires valid Gmail SMTP credentials
* Large abstracts may increase processing time
* Admin dashboard mobile UI can be improved


## Future Enhancements

* Additional academic categories
* PDF upload with automatic text extraction
* REST API for programmatic access
* Advanced analytics and visualization
* Export classification history
* Multi-language support
* arXiv API integration
* Real-time model retraining
* Docker-based deployment
