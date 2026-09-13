# Support Ticket Classification & Prioritization

## Project Overview

This project develops a machine learning system to automatically classify customer support tickets into relevant categories and predict their priority using Natural Language Processing (NLP).

The system processes ticket subject and description text to:

* Classify tickets into support categories
* Predict ticket priority as High, Medium, or Low
* Evaluate model performance using accuracy, precision, recall, classification reports, and confusion matrices

The solution can help support teams organize incoming tickets and identify high-priority issues faster.

---

## Objectives

The main objectives of this project are:

1. Clean and preprocess raw support ticket text.
2. Convert text into numerical features using TF-IDF.
3. Classify support tickets into appropriate categories.
4. Predict ticket priority levels.
5. Evaluate the performance of the machine learning models.
6. Visualize ticket distributions and model performance.

---

## Dataset

The project uses a multilingual support ticket dataset containing 4,000 support tickets.

Important fields used in the project include:

* `subject` — Ticket subject
* `body` — Ticket description
* `queue` — Support category
* `priority` — Ticket priority
* `language` — Ticket language

The `subject` and `body` fields are combined to create the text input used by the machine learning models.

---

## Technologies Used

* Python
* Pandas
* NumPy
* NLTK
* Scikit-learn
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## Methodology

### 1. Text Preprocessing

The ticket subject and body are combined into a single text field.

The following preprocessing steps are applied:

* Convert text to lowercase
* Remove punctuation and unnecessary characters
* Remove stopwords
* Handle missing text values
* Tokenize text during preprocessing

Stopwords from English, German, Spanish, French, and Portuguese are removed because the dataset contains multiple languages.

---

### 2. TF-IDF Feature Extraction

TF-IDF (Term Frequency-Inverse Document Frequency) is used to convert ticket text into numerical features.

Both unigrams and bigrams are considered so that the model can learn individual words as well as short phrases.

---

### 3. Ticket Category Classification

A Linear Support Vector Machine (`LinearSVC`) is trained to classify tickets into their appropriate support queues.

The model uses the TF-IDF representation of the ticket text as input.

---

### 4. Priority Prediction

A second Linear Support Vector Machine (`LinearSVC`) is trained to predict ticket priority.

The model predicts:

* High
* Medium
* Low

Priority is learned from patterns in the ticket text rather than being assigned using a manually defined rule.

---

## Model Performance

### Ticket Category Classification

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 56.63% |
| Precision | 55.58% |
| Recall    | 56.63% |

### Priority Prediction

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 58.38% |
| Precision | 58.99% |
| Recall    | 58.38% |

Class-wise performance is also provided in the notebook through classification reports.

---

## Visualizations

The project includes the following visualizations:

1. Ticket Category Distribution
2. Ticket Priority Distribution
3. Ticket Category Confusion Matrix
4. Ticket Priority Confusion Matrix

These visualizations help understand ticket volume, class distribution, and model classification performance.

---

## Example Prediction

The trained models can process a new support ticket and automatically predict:

* Support category
* Priority level

The new ticket is first cleaned and transformed using the same TF-IDF vectorizer used during training.

---

## Business Use

This system can help support managers, SaaS teams, and customer service organizations by:

* Automatically routing incoming tickets
* Identifying high-priority tickets
* Reducing manual ticket sorting
* Improving support workflow
* Helping teams handle large ticket volumes efficiently
* Supporting faster response to important customer issues

The system can be integrated into a support workflow where new tickets are automatically classified before being assigned to support staff.

---

## Project Workflow

```text
Support Ticket
      ↓
Subject + Body
      ↓
Text Cleaning
      ↓
Stopword Removal
      ↓
TF-IDF Feature Extraction
      ↓
 ┌───────────────────────┐
 │                       │
 ↓                       ↓
Category Model       Priority Model
(LinearSVC)          (LinearSVC)
 │                       │
 ↓                       ↓
Ticket Category      Priority Level
                     High / Medium / Low
```

---

## Project Structure

```text
FUTURE_ML_02/
│
├── dataset-tickets-multi-lang3-4k.csv
├── Support_Ticket_Classification.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

---

## How to Run

### 1. Install the required libraries

```bash
pip install -r requirements.txt
```

### 2. Open Jupyter Notebook

```bash
jupyter notebook
```

### 3. Open the notebook

```text
Support_Ticket_Classification.ipynb
```

### 4. Run the notebook cells from top to bottom

The notebook will:

1. Load the dataset
2. Explore ticket categories and priorities
3. Clean and preprocess ticket text
4. Generate TF-IDF features
5. Train the category classification model
6. Train the priority prediction model
7. Evaluate both models
8. Generate confusion matrices
9. Demonstrate prediction on a new ticket

---

## Conclusion

This project demonstrates an NLP-based machine learning solution for support ticket classification and prioritization.

The workflow includes text preprocessing, TF-IDF feature extraction, LinearSVC classification, priority prediction, model evaluation, and visualization.

The resulting system provides a practical foundation for automating support ticket routing and prioritization in customer support environments.
