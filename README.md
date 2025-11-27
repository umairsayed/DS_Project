Mapping Locations in Around the World in 80 Days
Data Science Research Project – Final Repository

This repository contains all code, data, and outputs for my project “Mapping Locations in Classic Novels Using Named Entity Recognition.”
The goal of the project is to extract, validate, classify, and map geographic locations mentioned in Jules Verne’s Around the World in 80 Days using NLP and transformer models.

Repository Structure

1. data/

Contains all datasets used in the workflow:

- around_world_80_days.csv — cleaned novel text split by chapters (from gutenbergr).

- cities15000.txt — GeoNames database file for validating extracted city names.

- sentence_city_pairs.xlsx — manually labelled ground-truth dataset for evaluation.

- synthetic_training_improved.xlsx — synthetic training data used for fine-tuning classification models.

2. clean_book.R

Retrieves the raw novel from Project Gutenberg and performs preprocessing, metadata removal, and chapter segmentation.

3. ner_extraction_and_validation.ipynb

Applies three NER models (spaCy Small, spaCy RoBERTa, Hugging Face BERT) and validates extracted location names against the GeoNames database.

4. journey_classification_and_mapping.ipynb

Trains BERT and RoBERTa classifiers on synthetic data, predicts visited vs. mentioned cities, geocodes locations, and generates the final ordered journey.

5. around_the_world_journey_map.html

Interactive Folium map showing the reconstructed route taken in the novel.
(Download + open in browser to explore.)
