# CivicRoute AI

Development for Artificial Intelligence – Course Assessment
Tayyab Sharjil Akram (116062)

## About

This project predicts the category of a civic request (broken streetlight, illegal dumping, pothole or water leak) using a small TensorFlow/Keras model. It is a prototype for the course, not a finished system.

## Data

`data/civic_requests_prepared.csv` is the dataset supplied with the assessment. It has 600 rows and 13 columns, with 150 rows for each category. It is synthetic, so it contains no real people.

## Files

- `civicroute_assessment.ipynb` – all my code and notes
- `data/` – the dataset
- `Selected Evidence/` – accuracy plot and confusion matrix
- `requirements.txt` – libraries I used

## How to run
1. Install libraries: `pip install -r requirements.txt`
2. Open `civicroute_assessment.ipynb` in Jupyter
3. Run all cells from top to bottom

I used Python 3.12 and set the random seed to 42.

## What I did

- Checked the data, the missing values and the class balance
- Kept 8 features and removed `request_id`, `night_report_flag`, `neighbourhood` (possible bias) and `previous_resolution_days` (not known for a new request)
- Filled missing `channel` values with the most common value, and `image_quality_score` with the median
- Encoded the categorical columns and scaled the numerical ones
- Split the data 70/15/15 into train, validation and test
- Trained a small model (Dense 16 → 8 → 4) for 50 epochs

## Results

- Training accuracy: 0.81
- Validation accuracy: 0.68
- Test accuracy: 0.71 (64 of 90 correct)

Illegal dumping was predicted best (20 of 22 correct). The model mixed up potholes and water leaks the most, probably because both are linked to rain. The gap between training and validation accuracy shows some overfitting.

## Limitations

The dataset is small and synthetic, and the test set only has 90 rows. There is no text or image data. I would test the model on more data before trusting it.

## Version Control
- master: stable version of my project
- update-readme-version-control: branch I used to add this section, then merged into master
