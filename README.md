# Repository for Hosoe & Sunagawa et al. (2022)

This repository provides the code and data accompanying the paper:

> **Hosoe J, Sunagawa J, Nakaoka S, Koseki S and Koyama K** (2022).
> Data mining for prediction and interpretation of bacterial population behavior in food.
> *Front. Food. Sci. Technol.* 2:979028.
> doi: [10.3389/frfst.2022.979028](https://doi.org/10.3389/frfst.2022.979028)

---

## Overview

This study applies data mining to the [ComBase](https://www.combase.cc/) database to predict and interpret bacterial growth/inactivation behavior in food. An XGBoost model is trained with hyperparameter tuning (GridSearchCV) and SHAP (SHapley Additive exPlanations) values are used to interpret model predictions.

---

## Repository Structure

```
paper_combase_2022/
├── README.md
├── data/
│   └── data_2022.csv          # Preprocessed ComBase dataset
├── notebooks/
│   └── code_datamining_Hosoe_ver1.ipynb  # Full analysis notebook
└── .devcontainer/
    ├── Dockerfile             # Docker image definition (Python 3.8.12)
    ├── devcontainer.json      # VS Code Dev Container configuration
    └── requirements.txt       # Python package dependencies
```

---

## Requirements

| Category | Package | Version |
|---|---|---|
| Core | numpy | 1.22.4 |
| | pandas | 1.3.5 |
| Visualization | matplotlib | 3.5.3 |
| | seaborn | 0.11.2 |
| Machine Learning | scikit-learn | 1.0.2 |
| | xgboost | 1.5.0 |
| Interpretability | shap | 0.40.0 |
| Encoding | category_encoders | 2.4.0 |
| Notebook | jupyter | 1.0.0 |
| | ipykernel | 6.16.2 |

> **Note on XGBoost version:** Prediction results may differ across XGBoost versions. The results in the paper were obtained with **v1.5.0** (local) and **v0.9** (Google Colab). GridSearchCV and SHAP computations are computationally intensive; running locally is recommended over Colab.

---

## Setup

### Option 1: VS Code Dev Container (Recommended)

Requires [Docker Desktop](https://www.docker.com/products/docker-desktop/) and the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR-USERNAME/paper_combase_2022
   cd paper_combase_2022
   ```
2. Open the folder in VS Code.
3. When prompted, click **"Reopen in Container"**, or open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) and select **"Dev Containers: Reopen in Container"**.
4. The environment is built automatically. Select the **`Python (ComBase_2022)`** kernel in the notebook.

### Option 2: Docker (Command Line)

1. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/).

2. Clone the repository:
   ```bash
   git clone https://github.com/YOUR-USERNAME/paper_combase_2022
   cd paper_combase_2022
   ```

3. Build the Docker image:
   ```bash
   docker build .devcontainer/ -t combase2022:latest
   ```

4. Run the container:
   ```bash
   docker run -p 8888:8888 -v $(pwd):/workspace combase2022:latest \
     jupyter notebook --ip=0.0.0.0 --allow-root --no-browser
   ```

5. Open the URL shown in the terminal (e.g., `http://127.0.0.1:8888/?token=...`) in your browser.

### Option 3: Local Python Environment

```bash
pip install -r .devcontainer/requirements.txt
jupyter notebook notebooks/code_datamining_Hosoe_ver1.ipynb
```

---

## Usage

Open `notebooks/code_datamining_Hosoe_ver1.ipynb` and run the cells in order. The notebook covers:

1. Data loading and preprocessing from `data/data_2022.csv`
2. Feature encoding with `category_encoders`
3. XGBoost model training with `GridSearchCV` hyperparameter tuning
4. Model evaluation
5. SHAP-based prediction interpretation and visualization

---

## Citation

If you use this code or data, please cite:

```bibtex
@article{hosoe2022datamining,
  author  = {Hosoe, Jun and Sunagawa, Junpei and Nakaoka, Shinji and Koseki, Shigenobu and Koyama, Kento},
  title   = {Data mining for prediction and interpretation of bacterial population behavior in food},
  journal = {Frontiers in Food Science and Technology},
  volume  = {2},
  pages   = {979028},
  year    = {2022},
  doi     = {10.3389/frfst.2022.979028}
}
```

---

## License

This repository is intended for academic reproducibility. Please contact the authors for other uses.
