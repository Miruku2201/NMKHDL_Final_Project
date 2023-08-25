﻿# Data analysis and prediction on book data from TIKI
## Project structure
```
D:.
│   .gitignore        # Git ignore file
│   changelog.txt     # Changelog
│   README.md         # This file
│   Report.pdf        # Report
│
├───.ipynb_checkpoints           # Checkpoint folder
│       preprocessing-checkpoint.ipynb # Checkpoint file
│
├───column                      # Column folder: explain the meaning of each column
│       Columns.csv             # Column file
│       Columns.xlsx            # Column file 
│
├───evaluating                  # Evaluating folder: contains the evaluating results
│       all_scores.csv
│       all_scores_2.csv
│       result.csv
│       scores.csv
│       scores_2.csv
│
├───features                    # Features folder: contains the features of the model (after preprocessing and extracting) 
│       processed.csv           # Processed file
│
├───full_data                   # Full data folder: contains the full data after crawling
│       data.csv                # Full data file
│       part_1.csv
│       part_2.csv
│       part_3.csv
│       part_4.csv
│       part_5.csv
│
├───id_data                     # ID data folder: contains the ID data 
│       books_id.csv
│       categories_id.csv
│       id_df.json
│
└───notebooks                   # Notebooks folder: contains the notebooks
        crawl.ipynb             # Crawl data from TIKI
        models.ipynb            # Models
        preprocessing.ipynb     # Preprocessing
        question.ipynb          # Answer the questions
```
## I. Data crawling
- Crawl data from TIKI via API using several libraries: json, requests, pandas, time, tqdm, ... then save the data to csv files.
  1. Crawl id data: books_id.csv, categories_id.csv, id_df.json
  2. Crawl each part of data: part_1.csv, part_2.csv, part_3.csv, part_4.csv, part_5.csv
  3. Merge all parts of data to data.csv
## II. Data preprocessing
- Preprocess the data: remove duplicates, remove outliers, remove unnecessary columns, rows, use regex to extract features, ...
- Save the processed data to csv file.
## III. Data analysis and answer the questions:
- Why are there duplicate names of books?
- How does the low average rating affect?
- Are book covers and editions of books a significant factor that customers prioritize when hunting for books?
- How are books that receive a lot of customer attention and reviews typically promoted or offered with discounts?
- Do the number of pages and the book cover have an impact on the pricing of books?
- What are the current trends and conditions of books in today's market?
=> Answer the questions by using data analysis and visualization.
## IV. Data modeling
- Use the processed data to build models.
- Perform categorical and numerical analysis.
- Identify the features that have the most impact on the discount percentage of books.
- Observe the distribution of the features to determine the ouliers and data centrality.
- Split the data into training and testing sets.
- Define a pipeline to preprocess numerical and categorical data.
- Final, use the processed data to build some models (Linear Regression, Random Forest, Gradient Boosting, TranformTargetRegressor) and choose the best model and best hyperparameters by using RandomizedSearchCV.
- Evaluate the models by using MAE, MSE, ... and save the results to csv files.
