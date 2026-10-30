# portfolio-vs-sp500-benchmarking
Quantitative risk-return analysis of a custom asset portfolio and benchmarking against the S&P 500 using Python.

## Quick Start

```bash
pip install yfinance pandas numpy plotly

import yfinance as yf
import pandas as pd
import numpy as np
import plotly.io as pio

pio.templates.default = "seaborn"

# Download stocks and S&P 500 data
stock_data = yf.download('MSFT AAPL SONY META GME AMZN TSLA EC', period='max').dropna()['Close']
benchmark_data = yf.download('^GSPC', period='max').dropna()['Close']
benchmark_data = pd.DataFrame(benchmark_data)
benchmark_data.columns = ['S&P 500']
