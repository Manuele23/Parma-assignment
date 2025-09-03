# Parma Calcio 1913 Data Scientist Assignment

![Python](https://img.shields.io/badge/python-3.9%2B-blue.svg)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)
![StatsBombPy](https://img.shields.io/badge/StatsBombPy-1.13.0-red.svg)
![pandas](https://img.shields.io/badge/pandas-2.2.0-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.5.0-orange.svg)
![matplotlib](https://img.shields.io/badge/matplotlib-3.9.0-yellow.svg)
![seaborn](https://img.shields.io/badge/seaborn-0.13.0-teal.svg)

<img src="https://upload.wikimedia.org/wikipedia/it/thumb/9/9a/Parmastemma.png/972px-Parmastemma.png?20130510204047" alt="Parma Calcio Logo" width="90" align="right"/>


This repository contains my solution to the **Parma Calcio 1913 Data Scientist technical assignment**.  
The project is divided into two main tasks, each organized in its own folder:

- **Task 1 – xG Model** (`task1_xg/`): building and evaluating multiple expected goals (xG) models  
- **Task 2 – Ballon d’Or 2015/16** (`task2_ballon_dor/`): ranking players from the Big 5 leagues season 2015/16 to determine the best player according to data  

All data come from the **[StatsBomb Open Data repository](https://github.com/statsbomb/open-data)** and are accessed programmatically using **[statsbombpy](https://github.com/statsbomb/statsbombpy)**, so no manual downloads are required.

## Setup & Installation

Clone the repository locally:

```bash
git clone <repo_url>
cd <repo_name>
```

### Option 1 – Using `setup.ipynb` (recommended)
Open and run `setup.ipynb`.  
It will install all required dependencies automatically in your environment (it considers `requirements.txt`).

### Option 2 – Manual installation with virtual environment
If you prefer an isolated environment:

```bash
# create and activate a virtual environment
python3 -m venv venv
source venv/bin/activate   # on Linux/Mac
venv\Scripts\activate      # on Windows

# install dependencies
pip install -r requirements.txt
```

### [!] Git LFS (for large files)
One large file (`shots_df.csv`) is tracked with **Git LFS**. If you want to download it directly instead of regenerating it from notebooks, make sure you have [Git LFS](https://git-lfs.github.com/) installed:

```bash
git lfs install
git lfs pull
```

### Reproducibility

Once the environment is ready:

1. Clone the repository  
2. Set up the environment (via `setup.ipynb` or virtual env)  
3. Run the notebooks in the provided order  

## Project Structure

```
├── task1_xg/                      
│   ├── data/                        # created Datasets for the task
│   ├── models/                      # trained models (excluded if large)
│   ├── outputs/                     # generated evaluation metrics for each model
│   ├── 01_data_exploration.ipynb  
│   ├── 02_shot_analysis.ipynb     
│   ├── 03_dataset_building.ipynb  
│   ├── 04_linear_regression.ipynb 
│   ├── 05_random_forest.ipynb     
│   ├── 06_xgboost.ipynb           
│   ├── 07_neural_network.ipynb    
│   ├── 08_model_comparison.ipynb  
│   ├── 09_ds_final.ipynb          
│   └── xg_demo.ipynb              
│
├── task2_ballon_dor/              
│   ├── data/                        # created Datasets for the task            
│   ├── 01_data_preparation.ipynb  
│   ├── 02_data_preprocessing.ipynb
│   └── 03_final_ranking.ipynb     
│
├── Assignment.pdf                 
├── requirements.txt               
├── setup.ipynb                    
├── README.md                      
└── .gitignore / .gitattributes
```

## How to Run

### Task 1 – Expected Goals (xG) Model
- Navigate to `task1_xg/`
- For a quick demo, run `xg_demo.ipynb` and go to the last cell to try the demo
- Otherwise, run the notebooks in order from **01** to **09** *(note: this step may take a while, as data retrieval is long)*  
- **Note**: the Random Forest model (`model_rf.pkl`) is **not included** in the repo because of its size:
  - To regenerate it, run `05_random_forest.ipynb`.  
- Final evaluation is in `08_model_comparison.ipynb` and `09_ds_final.ipynb`

### Task 2 – Ballon d’Or 2015/16

- Navigate to `task2_ballon_dor/`
- If you just want to **see the final ranking**, run only:  
  - `03_final_ranking.ipynb`  
- If you prefer to **re-download the datasets and reprocess everything from scratch**, run in order:  
  1. `01_data_preparation.ipynb`  *(note: this step may take a while, as data retrieval is long)*  
  2. `02_data_preprocessing.ipynb`  
  3. `03_final_ranking.ipynb`
     
---

## Notes

- Only **StatsBomb open data** was used, as required by the assignment
- Each notebook includes **detailed Markdown cells** that explain the rationale behind the methodology, the assumptions made, and the simplifications adopted step by step
- Models and outputs too large for GitHub are excluded, but can be easily regenerated locally by running the corresponding notebooks
