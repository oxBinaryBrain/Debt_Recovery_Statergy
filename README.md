## Debt Recovery Strategy 
This project aims to analyze a bank's debt recovery strategies for delinquent accounts. The bank assigns delinquent customers to different recovery strategies based on the expected amount the bank believes it will recover from the customer. By analyzing historical data and developing predictive models, the goal is to optimize recovery efforts and maximize the amount of debt collected.


## Project Structure

- `bank_data.csv`: CSV file containing the dataset.
- `bank_data_analysis.py`: Python script for data analysis.
- `README.md`: This file providing an overview of the project.

## Dependencies

- Python 3.x
- Pandas
- Matplotlib
- SciPy

Install the required dependencies using the following command:

```bash
pip install pandas matplotlib scipy
```

## Usage

1. Clone the repository to your local machine:
```bash
git clone https://github.com/yourusername/bank-data-analysis.git
```

2. Navigate to the project directory:
```bash
cd bank-data-analysis
```


3. Run the Python script to perform data analysis:
```bash
python bank_data_analysis.py
```

## Description

- The Python script reads the dataset from `bank_data.csv` using Pandas.
- It performs various data manipulation, visualization, and statistical analysis tasks, including scatter plots, descriptive statistics, and hypothesis testing.
- Statistical tests such as the Kruskal-Wallis test and chi-square test are used to assess relationships and differences between variables.
- Linear regression models are built using the Ordinary Least Squares (OLS) method to analyze the relationship between expected recovery amount, actual recovery amount, and other variables.

## Contributors

- [Your Name]
- [Other contributors]

## License

This project is licensed under the [license name] License. See the LICENSE.md file for details.


