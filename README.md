# Support Vector Machines (SVM)

This folder contains comprehensive tutorials on **Support Vector Machines (SVM)**, a powerful classification algorithm that finds optimal decision boundaries by maximizing the margin between classes.

## 📚 Contents

### 1. `SVM.ipynb`
**Introduction to Support Vector Machines: Concepts and Implementation**

A comprehensive introduction to SVM covering both theory and practice:

- **SVM Concepts**:
  - **Optimal Hyperplane**: Decision boundary that maximizes margin
  - **Support Vectors**: Data points closest to the decision boundary
  - **Margin**: Distance between decision boundary and nearest points
  - Mathematical formulation: $w^T x + b = 0$

- **Kernels Explained**:
  - **Linear Kernel**: Straight decision boundary
    - Suitable for linearly separable data
  - **Polynomial Kernel**: Curved boundaries of fixed degree
    - Handles non-linear patterns with polynomial curves
  - **RBF (Gaussian) Kernel**: Flexible, smooth boundaries
    - Maps data to infinite-dimensional space
    - Most flexible, handles complex non-linear patterns

- **Practical Implementation**:
  - **Dataset**: Student pass/fail prediction
    - Features: Hours studied, Attendance
    - Target: Passed (binary classification)
    - 120 students with realistic patterns

- **Workflow**:
  1. Data visualization (scatter plot by class)
  2. Train/test split and feature scaling
  3. Linear SVM training and evaluation
  4. Decision boundary visualization
  5. Performance interpretation

- **Model Evaluation**:
  - Accuracy: 0.867 (86.7%)
  - Classification report with precision, recall, F1
  - Class-wise performance analysis
  - Interpretation of results

**Key Learning Outcomes:**
- Understand SVM's margin maximization principle
- Learn about support vectors and their importance
- Understand different kernel types and when to use each
- Implement linear SVM with scikit-learn
- Visualize decision boundaries
- Interpret classification performance

### 2. `SVM-II.ipynb`
**Advanced SVM: Multiple Kernels and Comparison**

An advanced tutorial comparing different SVM kernels on the same dataset:

- **Dataset**: Same student pass/fail dataset (120 students)
  - Features: Hours studied, Attendance
  - Reproducible with fixed random seed

- **Kernels Compared**:
  1. **Linear SVM**:
     - Kernel: `'linear'`
     - C parameter: 1.0
     - Best for linearly separable data
  
  2. **Polynomial SVM**:
     - Kernel: `'poly'`
     - Degree: 3
     - C parameter: 1.0
     - Gamma: `'scale'`
     - Handles polynomial relationships
  
  3. **RBF (Radial Basis Function) SVM**:
     - Kernel: `'rbf'`
     - C parameter: 1.0
     - Gamma: `'scale'`
     - Most flexible, smooth boundaries

- **Comprehensive Evaluation**:
  - Accuracy and F1 score for each kernel
  - Classification reports
  - Decision boundary visualizations
  - Confusion matrices
  - Best model selection

- **Visualization**:
  - Decision boundaries for each kernel type
  - Comparison of how different kernels separate classes
  - Support vector identification

**Key Learning Outcomes:**
- Compare different SVM kernels on same dataset
- Understand kernel selection criteria
- Learn to tune SVM hyperparameters (C, gamma, degree)
- Visualize non-linear decision boundaries
- Select best kernel for specific problem

## 🛠️ Technologies Used

- **pandas**: Data manipulation
- **numpy**: Numerical operations
- **matplotlib**: Visualization and decision boundary plotting
- **scikit-learn**:
  - `SVC`: Support Vector Classifier
  - `train_test_split`: Data splitting
  - `StandardScaler`: Feature scaling (important for SVM)
  - `accuracy_score`, `f1_score`: Performance metrics
  - `classification_report`: Detailed evaluation
  - `ConfusionMatrixDisplay`: Confusion matrix visualization

## 📋 Prerequisites

- Understanding of classification problems
- Knowledge of decision boundaries
- Familiarity with feature scaling importance
- Basic understanding of kernel methods
- Python programming with scikit-learn

## 🚀 Getting Started

1. **Install Required Packages**:
   ```bash
   pip install pandas numpy matplotlib scikit-learn
   ```

2. **Run the Notebooks**:
   - Start with `SVM.ipynb` for fundamental concepts
   - Follow with `SVM-II.ipynb` for kernel comparison

## 📊 Dataset Information

**Student Pass/Fail Dataset**:
- **Size**: 120 students
- **Features**:
  - `Hours`: Hours studied per week (1-10)
  - `Attendance`: Attendance percentage (50-100%)
- **Target**: `Passed` (0 = Fail, 1 = Pass)
- **Pattern**: Score = 0.5 × Hours + 0.05 × Attendance + noise
- **Class Balance**: ~23% passed (imbalanced dataset)

## 💡 Key Concepts

### Support Vectors
- Data points closest to the decision boundary
- Define the margin
- Only these points matter for the decision boundary
- Removing non-support vectors doesn't change the model

### Margin Maximization
- **Goal**: Find the widest possible margin between classes
- **Benefit**: Better generalization, more robust to new data
- **Mathematical**: Maximize distance to nearest points

### Kernel Trick
- Maps data to higher-dimensional space
- Allows linear separation of non-linearly separable data
- Computes similarity without explicit transformation
- Common kernels: Linear, Polynomial, RBF

### Hyperparameters

**C Parameter**:
- Controls trade-off between margin width and classification errors
- **Large C**: Narrow margin, fewer misclassifications (may overfit)
- **Small C**: Wide margin, more misclassifications (may underfit)

**Gamma (RBF/Polynomial)**:
- Controls influence of individual training examples
- **Large gamma**: Tight boundaries around each point (may overfit)
- **Small gamma**: Smooth boundaries (may underfit)

**Degree (Polynomial)**:
- Polynomial degree for polynomial kernel
- Higher degree = more complex curves

## 🎯 Kernel Selection Guide

| Kernel | Best For | Pros | Cons |
|--------|----------|------|------|
| **Linear** | Linearly separable data | Fast, interpretable | Limited to linear patterns |
| **Polynomial** | Moderate non-linearity | Flexible curves | Sensitive to degree choice |
| **RBF** | Complex non-linear patterns | Very flexible, smooth | Can overfit, slower |

## 📝 Notes

- **Feature Scaling is Critical**: SVM is sensitive to feature scales
- Always use `StandardScaler` before training SVM
- Results are reproducible with fixed random seeds
- Decision boundary visualizations help understand model behavior
- Both notebooks use the same dataset for consistency

## 🔗 Related Topics

- **Classification**: See `Classification/` folder for other algorithms
- **Model Evaluation**: See `model_evaluation/` folder for metrics
- **Kernel Methods**: Advanced topics in machine learning

## 💡 Real-World Applications

SVM is widely used in:
- **Text Classification**: Spam detection, sentiment analysis
- **Image Recognition**: Handwriting recognition, face detection
- **Bioinformatics**: Protein classification, gene expression
- **Financial Analysis**: Stock market prediction, credit scoring
- **Medical Diagnosis**: Disease classification from medical images

## ⚠️ Important Considerations

1. **Scaling Required**: Always scale features before SVM
2. **Memory Intensive**: Can be slow on very large datasets
3. **Kernel Selection**: Try multiple kernels and compare
4. **Hyperparameter Tuning**: Use cross-validation for C and gamma
5. **Interpretability**: Less interpretable than linear models or trees

