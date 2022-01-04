# Fintech Challenge 05 -- Financial Planning with APIs

Financial Planning Tools for Emergencies and Retirement

---

## Analysis 

This challenge created two financial analysis tools:
- emergency financial planner (crypto, stocks, bonds)
- retirement planner (stocks/bonds, with different weights and timeframes)

See full analysis details in the notebook [financial_planning_tools.ipynb](./financial_planning_tools.ipynb)

#### DataSets

1. Emergency Planner
  * crypto prices for BTC and ETH from Free Crypto API
  * SPY and AGG prices from alpaca tradeapi, for date 2021-12-30
2. Retirement Planner
  * past three years SPY AGG close data from alpaca trade API

#### Assumptions

1. Emergency Planner
  * saver's monthy income is $12,000
  * portfolio contains 1.2 BTC and 5.3 ETH
  * portfolio contains 110 SPY and 200 AGG shares  
2. Retirement Planner
  * past three years SPY AGG close data from alpaca trade API, from 2018-12-30 -> 2021-12-30
  * portfolio forcasting of 30 yr 60/40 stock/bonds vs 10yr 80/20 stocks/bonds 

#### Summary

1. Emergency Planner Summary:
  *  The saver will have $151094.05, which is enough for an emergency fund. 
2. Retirement Planner Summary:
  * The 30 year 60/40 portfolio had lower/upper bounds of 1.3 -> 26 million dollars. However the 10 year 80/20 portfolio had much smaller lower/upper bounds at 171 K -> 1.2 million dollars. Assuming the saver wants at least 10yrs current salary (approx 1.4 million) in retirement savings before retiring, then NO, it is unlikely that the 10 yr portfolio will give the saver enough money.


See details and visualizations in the notebook [financial_planning_tools.ipynb](./financial_planning_tools.ipynb)

---

## Technologies

This challenge uses [python](https://www.python.org/) 3.7 and the following [built-in](https://docs.python.org/3/py-modindex.html) modules:
- [json](https://docs.python.org/3/library/json.html#module-json)
- [os](https://docs.python.org/3/library/os.html#module-os)

Additionally, it requires:
- [matplotlib](https://matplotlib.org/)
- [pandas](https://pandas.pydata.org/)
- [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/)
- [numpy](https://numpy.org/)
- [requests](https://docs.python-requests.org/en/latest/)
- [python-dotenv](https://pypi.org/project/python-dotenv/)
- [alpaca-trade-api](https://github.com/alpacahq/alpaca-trade-api-python)

See [installation](#installation) below for specifics.

---

## Installation

You will need Python 3.7, that supports for this application to run. An easy way to install python 3.7 is to download and install [Anaconda](https://www.anaconda.com/products/individual). After installing anaconda, open a terminal/command-prompt, and setup a python 3.7 environment, and then activate it like so:

```
# create an anaconda python 3.7 environment
# name can be any friendly name to refer to your environment, eg 'dev'
conda create --name dev python=3.7 anaconda

# activating the environment
conda activate dev

# use pip to install the above modules, eg:
pip install python-dotenv
...etc...
```

## Alpaca API Setup

You must generate an Alpaca API key and secret if you want to run the notebook api queries yourself. To do this, go to [Alpaca API Signup](https://app.alpaca.markets/signup), and create an account, then generate and API key and secret. These values should then be put into a file named `.env` located at the root of this repo, like below. The values will then be read into the notebook by the `load_dotenv()` and `os.getenv()` calls.

Example .env file contents:

```
ALPACA_API_KEY = 'YOUR_API_KEY'
ALPACA_SECRET_KEY = 'YOUR_SECRET_KEY'

```

---

## Usage

The analysis is presented within a [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) notebook. To launch JupyterLab, from the root of this repo dirctory:

```
# within repo root 
$ jupyter lab --ContentsManager.allow_hidden=True
```
You can now open the notebook [financial_planning_tools.ipynb](./financial_planning_tools.ipynb) locally with JupyterLab.

---

## Contributors

[David Lopez](https://github.com/sububer)

---

## License

MIT