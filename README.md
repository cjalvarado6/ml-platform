# ML Model Playground
**An interactive machine learning explainer platform**

## Overview
The **ML Model Playground** is an interactive, educational platform designed to help users **understand how machine learning models behave**, not just what predictions they produce.

Instead of focusing on raw performance, the platform emphasizes:
- Explainability
- Model behavior
- Tradeoffs between algorithms
- The impact of inputs, parameters, and hyperparameters

Users learn by **experimenting**, **comparing scenarios side by side**, and **observing how internal model behavior changes**.

> ⚠️ This tool is for **educational and exploratory purposes only** and should not be used for real-world decision-making.

---

## Core Goals
- Make ML models **intuitive and inspectable**
- Enable **side-by-side comparisons** to highlight tradeoffs
- Teach *why* predictions change, not just *what* they are
- Provide a reusable, extensible framework across ML tasks

---

## Supported ML Tasks
The platform is organized by ML task, with a consistent layout across sections.

- **Classification** ✅ (Phase 1)
- Regression (Planned)
- Clustering (Planned)

Each task contains subtabs for different model types.

---

## Phase 1: Classification Playground (MVP)

### Supported Models
- Logistic Regression
- Random Forest
- Gradient Boosted Trees (e.g. XGBoost / LightGBM)

These models were selected to expose:
- Linear vs non-linear decision boundaries
- Interpretable vs ensemble methods
- Bias–variance tradeoffs

---

## User Experience

### High-Level Layout
- **Top-level navigation** by ML task
- **Sidebar** for dataset and model selection
- **Main content area** with tabbed views

### Main Tabs
1. Playground  
2. Model Internals  
3. Explainability  
4. Metrics  

---

## Interaction Model

### Inputs
Users can:
- Adjust feature inputs
- Adjust model hyperparameters directly
- Select datasets (built-in for Phase 1)

All changes are applied via a **manual “Run” button** to reinforce cause → effect relationships.

---

### Scenario Comparison
A core feature of the platform.

- Two side-by-side panels
- Same dataset and model
- Different inputs and/or hyperparameters
- Visual comparison of:
  - Predictions
  - Probabilities
  - Feature importance

This enables users to answer:

> *“What changed, and why?”*

---

## Outputs

### Predictions
- Predicted class
- Class probability distribution

### Explainability
- Feature importance visualization
- Textual explanation highlighting top contributors

Example:
> “The prediction was primarily driven by feature X, followed by Y and Z.”

---

### Metrics
Displayed in a dedicated tab:
- Accuracy / AUC
- Confusion matrix
- Dataset statistics (size, class balance)

Advanced metrics may be hidden behind toggles to avoid overload.

---

## Design Principles
- **Explainability over optimization**
- **Consistency across model types**
- **Same data, different inductive biases**
- **Metadata-driven UI**
- **Educational clarity before visual complexity**

---

## Technical Architecture

### Backend
- FastAPI
- sklearn-based models
- SHAP for explainability
- JSON metadata defining:
  - Features
  - Hyperparameters
  - Input constraints

### Frontend
- React / Next.js
- Dynamic UI generated from metadata
- Side-by-side comparison panels
- Visualization libraries for charts

### Deployment
- Frontend: Vercel
- Backend API: Managed container hosting (e.g. Render / Fly.io)

---

## Project Status
🚧 **Phase 1 (Classification Playground) in active development**

---

# Roadmap & Backlog

## Phase 1 — Classification MVP (Current)
**Goal:** Establish core UX, architecture, and educational value.

### Must-Have
- Classification task section
- Logistic Regression, Random Forest, GBT models
- Built-in datasets
- Manual Run trigger
- Side-by-side scenario comparison
- Feature importance visualization
- Core metrics (Accuracy, AUC, Confusion Matrix)
- Educational disclaimer
- Clean README + architecture documentation

### Nice-to-Have
- Preset scenarios (e.g. “High Risk”, “Low Risk”)
- Input validation warnings
- Collapsible advanced hyperparameters

---

## Phase 2 — Regression Playground
**Goal:** Extend framework to numeric prediction tasks.

### Features
- Regression task section
- Models:
  - Linear Regression
  - Ridge / Lasso
  - Gradient Boosted Regressor
- Outputs:
  - Predicted value
  - Error range / confidence interval
- Explainability:
  - Feature importance
  - Partial dependence plots
- Metrics:
  - RMSE
  - MAE
  - R²

---

## Phase 3 — Clustering Playground
**Goal:** Explain unsupervised learning behavior.

### Features
- Clustering task section
- Models:
  - K-Means
  - DBSCAN
  - Hierarchical clustering
- Interactive cluster visualization
- Parameter sensitivity exploration
- Metrics:
  - Silhouette score
  - Cluster size distributions

---

## Phase 4 — Dataset Uploads
**Goal:** Allow users to explore their own data.

### Features
- CSV upload
- Schema inference
- Feature selection UI
- Validation and error handling
- Privacy-safe, ephemeral processing

---

## Phase 5 — Advanced Explainability
**Goal:** Deepen intuition for advanced users.

### Features
- SHAP waterfall plots
- Counterfactual explanations
- “What would need to change to flip this prediction?”
- Model comparison summaries

---

## Phase 6 — Learning & Documentation
**Goal:** Turn the platform into a guided learning tool.

### Features
- Inline tooltips
- “What is happening?” explanations per model
- Interactive walkthroughs
- Glossary of ML concepts

---

## Long-Term Ideas
- In-browser model execution (WebAssembly)
- Notebook export of scenarios
- Save/share experiment configurations
- Teaching mode for instructors
- Lightweight benchmarking mode

---

## License
MIT (or TBD)
