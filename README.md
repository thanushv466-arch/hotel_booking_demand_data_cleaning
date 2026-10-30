# Hotel Booking Demand — Data Cleaning

This project completes a data-cleaning workflow using the Hotel Booking Demand dataset.

## Files
- `Hotel_Booking_Data_Cleaning.ipynb` — documented cleaning notebook.
- `requirements.txt` — Python dependencies.
- `GITHUB_PUBLISHING.md` — publishing steps.

## Dataset
Download `hotel_bookings.csv` from the Hotel Booking Demand dataset on Kaggle and place it beside the notebook, or upload it when prompted in Google Colab. The raw dataset is not included in this repository.

## Cleaning decisions
- `children`: median imputation.
- `country`: fill missing values with `Unknown`.
- `agent`, `company`: fill missing IDs with `0` to represent no recorded agent/company.
- Exact duplicate rows: removed; the dataset has no unique booking ID, so exact duplicates are treated as indistinguishable repeated records.
- Outliers: detected using IQR and box plots. Plausible extremes are retained. Negative values in non-negative count/price fields are removed as logically invalid.
- Nominal categories: one-hot encoded. Existing binary flags remain numeric.

Run in Google Colab or Jupyter. The notebook saves `hotel_bookings_cleaned.csv` and `hotel_bookings_encoded.csv`.
