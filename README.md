# Green Gentrification in Amsterdam: An Analysis (2020-2024)

## Project Overview

This repository contains the code, data, and results for the research project investigating the relationship between urban greening initiatives and gentrification indicators in Amsterdam's neighborhoods (*buurten*) between 2020 and 2024. The project aimed to:

1.  Estimate the potential causal impact of significant green space changes using a Difference-in-Differences (DiD) model.
2.  Develop and evaluate machine learning models (including Logistic Regression, KNN, SVM, Random Forest, and LightGBM) to predict future gentrification risk based on baseline neighborhood characteristics.

This research was conducted as part of the "Planetary Health and the Symbiotic City" course within the Honours Programme at Vrije Universiteit Amsterdam (2025) in a group of 3 total members.

## Repository Structure

* `notebooks/`: Contains Jupyter Notebooks (`.ipynb`) detailing the workflow:
    * `01_fetch_data.ipynb`: Fetches historical green space data via Overpass API.
    * `02_preprocess_data.ipynb`: Cleans, merges, and imputes data from various sources (OSM, CBS, O&S).
    * `03_analysis.ipynb`: Performs the Difference-in-Differences causal analysis.
    * `04_random_forest_classifier.ipynb`: Initial predictive modeling and feature importance analysis with Random Forest.
    * `05_model_comparison.ipynb`: Compares multiple tuned ML models.
    * `06_lightGBM_future_prediction.ipynb`: Trains the final LightGBM model and generates future risk predictions.
* `data/`: Contains essential input data files (`.csv`, `.json`) required to run the notebooks. Raw downloads and intermediate files are excluded but were part of the process (see `.gitignore`).
* `results/`: Contains key output files, including DiD sensitivity results (`.csv`), final predictions (`.csv`), and generated figures (`.png`).
* `README.md`: This file.
* `.gitignore`: Specifies files and folders intentionally excluded from the repository (e.g., virtual environment, unused files).
* `requirements.txt`: Lists the necessary Python libraries to run the code.
* `GentrAIfication Exploring the Association between Urban Greening and Gentrification.pdf`: The final scientific report detailing the methodology, findings, and discussion.

## How to Run

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/tommasozf/amsterdam-green-gentrification.git
    cd <repository-folder>
    ```
2.  **Set up the Python environment:**
    * It is highly recommended to use a virtual environment:
        ```bash
        python -m venv .venv
        # Activate the environment (Linux/macOS):
        source .venv/bin/activate
        # Or on Windows CMD:
        # .venv\Scripts\activate
        ```
    * Install the required libraries:
        ```bash
        pip install -r requirements.txt
        ```
3.  **Run the Jupyter Notebooks:** Execute the notebooks in sequential order (`01` through `06`) from within the `notebooks/` directory using Jupyter Lab or Jupyter Notebook.
    * **Note:** `01_fetch_data.ipynb` interacts with the external Overpass API and may take significant time to run. Pre-fetched data is included in the `data/` folder.

## Overview of Data Sources

* **Green Space:** OpenStreetMap (accessed via Overpass API)
* **Socio-Economic:** Statistics Netherlands (CBS StatLine - *Kerncijfers Wijken en Buurten*)
* **Facilities & Boundaries:** Onderzoek en Statistiek (O&S), City of Amsterdam

## Important Note on Methodology

Almost all of the code is AI-generated. As of writing, I am not a particularly skilled programmer and I would've had to invest considerable time if I were to write code myself. Due to time constraints (this was a 8-week course, but the time available/spent working on this project was effectively 3-4 weeks) and this being on top of the standard academic curriculum, this was not possible. 

I mostly gave high-level instructions to Gemini 2.5 Pro and Claude Sonnet 4.5 at each step to take care of the actual coding. I have changed a few lines here and there but not a significant amount. This also allowed me to keep the scope as broad as I did - relatively speaking, as it is by most means quite narrow, only focusing on selected Amsterdam neighborhoods.

However, I was satisfied with the process and with what I was able to accomplish, considering that it was my first data science project and that I had to teach myself the theory and tools required.

I am sure there are still mistakes I have committed and overseen, but the research and statistical findings should hold. If you're reading this, please feel free to provide any feedback on any aspect of the project. 
