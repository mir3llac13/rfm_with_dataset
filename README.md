# RFM Customer Segmentation Project
This project performs RFM (Recency, Frequency, Monetary) analysis on a retail transactions dataset from Kaggle. It segments customers into categories like "Champions," "Loyal Customers," "Potential," "At Risk," and "Lost" to optimize marketing strategies.

## Installation and Requirements

To run this project locally, follow these steps:

1. **Set Up a Python Environment**:
   ```bash
   python -m venv rfm_env
   source rfm_env/bin/activate  # On Windows: rfm_env\Scripts\activate

## Install Required Libraries
pip install pandas numpy matplotlib jupyter kagglehub

## Download The Dataset

The dataset is automatically fetched using kagglehub.dataset_download("prasad22/retail-transactions-dataset") within the notebook.
Ensure you have a Kaggle API token (download from Kaggle and place kaggle.json in ~/.kaggle/).

2. **Launch Jupyter Notebook**
jupyter notebook  

## Usage

Follow these steps to use the RFM analysis notebook:

1. **Open the Notebook**:
   - Launch Jupyter Notebook and open `RFM_Analysis.ipynb`.
2. **Run the Cells**:
   - Execute the cells sequentially to calculate RFM scores and generate segments.
   - Key steps include data loading, aggregation (Recency, Frequency, Monetary), and scoring (1-5 scale).
3. **View Results**:
   - The notebook outputs a table with `R_Score`, `F_Score`, `M_Score`, `RFM_Score`, and `Segment` columns.
   - A pie chart visualizes the segment distribution (e.g., ~25% "Lost", 25% "Loyal Customers").
4. **Example Code Snippet**:
   ```python
   rfm = df.groupby('Customer_Name').agg({
       'Date': lambda x: (analysis_date - x.max()).days,
       'Transaction_ID': 'count',
       'Amount': 'sum'
   }).rename(columns={'Date': 'Recency', 'Transaction_ID': 'Frequency', 'Amount': 'Monetary'})

 ## Results and Findings

- **Key Metrics**: Approximately 330k rows analyzed, with 192 unique customers. Frequency is often low (mostly 1), indicating low loyalty.
- **Segment Distribution**: Example output shows ~25% "Lost", 25% "Loyal Customers".
- **Visualization**: A pie chart displays segment percentages for easy interpretation.
- **Insights**: Low Recency scores suggest many inactive customers; high Monetary in "Champions" segment indicates value from loyal users.
- **Example Output**: 
- **Future Improvements**: Integrate K-Means clustering for advanced segmentation.
- - Updated on October 6, 2025
