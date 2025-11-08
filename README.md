# AI Development Workflow Assignment

## Project Overview

This project, part of the "AI for Software Engineering" course, demonstrates a comprehensive AI development workflow applied to two distinct classification problems: Student Dropout Prediction and Hospital Readmission Prediction. The assignment covers theoretical problem definition, data strategy, model development, evaluation, and critical thinking on ethical implications and trade-offs.

## Project Structure

The repository is organized as follows:

```
.
├── data/                               # Raw datasets for both case studies
├── notebooks/                          # Jupyter Notebooks for practical implementation
│   ├── 1_student_dropout_prediction.ipynb
│   └── 2_hospital_readmission_prediction.ipynb
├── docs/                               # Markdown files for theoretical parts and reflection
│   ├── part3_critical_thinking.md
│   └── part4_reflection_workflow.md
├── README.md                           # Project overview and instructions
├── requirements.txt                    # Python dependencies
└── task.md                             # Detailed project build instructions
```

## Setup and Installation

To set up and run this project, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone <repository_url>
    cd AI_SE_week5_assignment
    ```
2.  **Create a Python Virtual Environment:**
    ```bash
    python -m venv venv
    ```
3.  **Activate the Virtual Environment:**
    *   **Windows:**
        ```bash
        .\venv\Scripts\activate
        ```
    *   **macOS/Linux:**
        ```bash
        source venv/bin/activate
        ```
4.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
5.  **Launch JupyterLab:**
    ```bash
    jupyter lab
    ```
    This will open JupyterLab in your browser, where you can navigate to the `notebooks/` directory and open the `.ipynb` files.

## Part 1: Student Dropout Prediction

### Problem Definition
The goal is to identify students at high risk of dropping out early, enabling targeted interventions to improve retention rates. Key stakeholders include educational institutions and students. The primary KPI is the Student Retention Rate.

### Approach
The approach involves collecting data from Student Information Systems (SIS) and Learning Management System (LMS) logs. Preprocessing steps include handling missing values, feature engineering (e.g., GPA, attendance rate), and categorical encoding.

### Model Architecture
A **Random Forest Classifier** was chosen for its robustness to overfitting and ability to handle diverse feature types. The data was split into 80% training and 20% testing sets. The model was trained on the preprocessed data.

### Key Findings
The model achieved an **accuracy of approximately 77.3%**. The classification report highlighted varying performance across classes (0: Graduate, 1: Dropout, 2: Enrolled), with a lower recall for the 'Dropout' class (0.32), indicating a challenge in correctly identifying all students who eventually drop out.

## Part 2: Hospital Readmission Prediction

### Problem Definition
This case study focuses on predicting hospital readmissions to optimize healthcare resource allocation and improve patient outcomes.

### Approach
The data strategy involves acquiring data from Electronic Health Records (EHR) and administrative sources. Preparation includes feature selection, handling missing values, one-hot encoding for categorical features, and standard scaling for numerical features.

### Model Architecture
A **Random Forest Classifier** was integrated into a `Pipeline` with a `ColumnTransformer` for preprocessing. The training data was split into 80% training and 20% validation sets. The pipeline handles both data transformation and model training seamlessly.

### Key Findings
The model achieved an **accuracy of approximately 81.2%**. However, the classification report revealed a very low recall for the 'readmitted' class (0.01), suggesting that the model is highly biased towards predicting non-readmission and struggles to identify actual readmission cases. This indicates a significant class imbalance issue that needs to be addressed for practical application.

## Part 3: Critical Thinking (Ethics, Bias, Trade-offs)

This section, detailed in `docs/part3_critical_thinking.md`, explores the ethical implications and potential biases in both prediction models. It discusses issues like stigmatization, fairness in resource allocation, and data privacy. It also analyzes the trade-offs between model performance and interpretability, and the critical balance between false positives and false negatives in sensitive domains. The low recall in the hospital readmission model highlights a critical trade-off where minimizing false positives might lead to missing many true readmissions.

## Part 4: Reflection & Workflow Diagram

This section, found in `docs/part4_reflection_workflow.md`, provides a personal reflection on the challenges faced (e.g., data imbalance, feature engineering), key learnings (e.g., importance of EDA, iterative refinement), and future improvements (e.g., advanced preprocessing, hyperparameter optimization, XAI). An embedded Mermaid diagram visually represents the AI development workflow.
