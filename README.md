# Mapping Locations in *Around the World in 80 Days*

This repository contains all data and code used to extract, validate, classify, and map geographic locations mentioned in Jules Verne’s *Around the World in 80 Days* using NLP and transformer models.

## Repository Structure

### 1. data/
This folder contains all datasets required for the workflow:
- around_world_80_days.csv --> cleaned novel text split by chapters.
- cities15000.txt --> GeoNames database used to validate city names.
- sentence_city_pairs.xlsx --> manually labelled ground-truth test data.
- synthetic_training_improved.xlsx --> synthetic training dataset for the classification models.

### 2. clean_book.R
Retrieves the novel from Project Gutenberg and performs all preprocessing (metadata removal, chapter detection, formatting).  
Run this file first if you want to regenerate the cleaned text.

### 3. ner_extraction_and_validation.ipynb
Runs three NER models (spaCy Small, spaCy RoBERTa, Hugging Face BERT), extracts location entities, and validates them against the GeoNames database.  
Outputs a validated list of cities and sentence-city pairs.

### 4. journey_classification_and_mapping.ipynb
Trains the classification models (BERT and RoBERTa) using the synthetic dataset, predicts visited vs. mentioned cities, performs geocoding, and generates the final ordered journey.

### 5. around_the_world_journey_map.html
The final interactive Folium map showing the reconstructed journey.  
Download and open in any browser to view.

### 6. environment.yaml
Conda environment file used for this project.
Can be used to recreate the exact environment used to run all notebooks.

## How to Run
1. To recreate the environment and run the notebooks, create the Conda environment and activate it:
    ```
    conda env create -f environment.yaml
    ```
2. (Optional) Run `clean_book.R` if you wish to re-download and clean the novel.
3. Run `ner_extraction_and_validation.ipynb` to extract and validate all locations.
4. Run `journey_classification_and_mapping.ipynb` to classify visited cities and generate the final map.
5. Open `around_the_world_journey_map.html` in your browser to explore the journey.

## Notes
- Data required for running the notebooks is contained in the `data/` folder.
