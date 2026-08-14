# Monte Carlo Portfolio Simulation

## Key Concepts

### Financial Data
Firstly, download 300 days of historical stock prices using yfinance. Calculates daily percentage returns and the covariance matrix to track how stocks move together.

### Random Portfolio Allocation

This assigns random weights to each stock within the portfolio, normalised to sum to 100%, representing one possible portfolio construction.

### The Monte Carlo Simulation

Generates 1000 independent simulations of portfolio value over 100 days. Each simulation:
1. Generates random daily returns drawn from a normal distribution
2. Applies Cholesky decomposition to obtain correlations between the returns 
3. Compounds returns each day to get total portfolio value
4. Stores results which can be observed in the constructed plots

### Cholesky Decomposition?

Random noise would mean that the stocks are uncorrelated, as they would move independently in pure randomness. Cholesky decompositions allows for the transformation of this into correlated noise using historical behaviour. For example, if the stocks of HSBA and VOD historically moved together, the simulation would acknowledge this relationship in terms of correlation.

### Interpreting Plot

The 1000 coloured lines represent 1000 possible outcomes:
- **Central tendency:** Average expected portfolio growth
- **Top line:** Best-case scenario (95th percentile)
- **Bottom line:** Worst-case scenario (5th percentile)  
- **Fan width:** Portfolio risk, a wider fan = more volatile

## How to Use

### Prerequisites
- Python 3.10+
- Stock tickers: HSBA.L, VOD.L, GSK.L, MKS.L, BARC.L


### Installation

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### Run

```bash
jupyter notebook Monte_Carlo.ipynb
```

Change the `tickers` variable to compose and simulate different portfolios.

## Technologies

- **yfinance** — Used to retreive stock data
- **NumPy** — Used for matrix operations and to conduct random number generation
- **Pandas** — Data handling
- **Matplotlib** — Visualisation of the simulated portfolio values


## Project Files

- `Monte_Carlo.ipynb` — Complete notebook with code
- `requirements.txt` — Dependencies





