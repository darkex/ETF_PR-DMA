# PR-DMA: Portfolio Reporting & Decision Making Aid

## Introduction

Use PR-DMA to obtain useful daily reporting allowing you to monitor your portfolio or part of your portfolio composed of ETFs as closely as possible and make decisions more easily.
Users can choose which ETFs to track.

#### Features:
* Track all ETFs available on `Bourse Direct` (one of the best French broker if not the best)!
* Automated reporting based on user parameters
* Automated technical analysis (TA)
* Slack notifications for the reporting. Emails can be added according to the user's needs.
* Logs available for further exploitation
* Automatically save your market data on your Google Drive (additional settings are required and described later)
* Ongoing documentation

For the moment, four indicators are present in the reporting:

- ADX: stands for Average Directional Movement Index and can be used to help measure the overall strength of a trend. The ADX indicator is an average of expanding price range values and is a component of the Directional Movement System developed by Welles Wilder. More information can be found [here](https://www.fidelity.com/learning-center/trading-investing/technical-analysis/technical-indicator-guide/adx)

- RSI: The Relative Strength Index (RSI), developed by J. Welles Wilder, is a momentum oscillator that measures the speed and change of price movements. The RSI oscillates between zero and 100. Traditionally the RSI is considered overbought when above 70 and oversold when below 30. Signals can be generated by looking for divergences and failure swings. More information can be found [here](https://www.fidelity.com/learning-center/trading-investing/technical-analysis/technical-indicator-guide/RSI)

- Sotchs: The Stochastic Oscillator is a momentum indicator that shows the location of the close relative to the high-low range over a set number of periods. The indicator can range from 0 to 100. The closing price tends to close near the high in an uptrend and near the low in a downtrend. If the closing price then slips away from the high or the low, then momentum is slowing. More information can be found [here](https://www.fidelity.com/learning-center/trading-investing/technical-analysis/technical-indicator-guide/fast-stochastic)

- CCI: The Commodity Channel Index (CCI) measures the current price level relative to an average price level over a given period of time. CCI is relatively high when prices are far above their average. CCI is relatively low when prices are far below their average. Using this method, CCI can be used to identify overbought and oversold levels. More information can be found [here](https://www.fidelity.com/learning-center/trading-investing/technical-analysis/technical-indicator-guide/cci)

Users can add their own indicators. A multitude of indicators is available. The library used is talib. More information on the talib [here](https://github.com/mrjbq7/ta-lib)

## How to setup
1) This project requires Python 3.X.X, which can be found [here](https://www.python.org/ftp/python).

2) To install the dependencies for this project, run `pip install -r requirements.txt`. If you receive a `pip is not  recognized as an internal or external command` error, you need to add `pip` to your environmental `path` variable.

3) Add a directory named `.config` to the root directory of your project and add a `secrets_etf.json` file based on the `secrets_etf_template` already in the directory.
If you run the project without adding this file, the program will create it for you and populate it with the template values.
But before doing so, it is recommended to obtain the credentials.json and token.json files for which templates are available in the `.config` directory. To obtain these files, you can check:
- Cloud Google Access From Python [here](https://cloud.google.com/endpoints/docs/frameworks/python/access_from_python)
- Developers Quick start Python [here](https://developers.google.com/drive/api/v3/quickstart/python)

## How to run
Navigate to the `source_python` file directory in terminal, and run the command :
- `python ETF_write_files.py` to get market data and write in the flat file of each ETF.
- `python ETF_get_signal.py` to get the reporting.
- `python drive_backup.py` to save your ETF flat files on your Google Drive after the small setting described above.

*(Note: I would highly recommend getting the python IDE **PyCharm** by JetBrains. Its a great development tool and makes 
running and debugging this project a breeze. A free community edition can be found 
[here](https://www.jetbrains.com/pycharm/download).)*

## To Be Done / Improvement
The lines of code of this tool are still poorly documented and there are several areas for improvement on which I am still working on.
Also, this tool is aimed at Python developers who are able to perceive certain subtleties of the code not yet described here and who will be able to customise it to their liking and take advantage of it enormously.

Also, for the moment, we are only going to scrape the data of a french broker but you will be able to customize this code in order to scrape the data of any broker. Scraping is a good alternative to financial data which are very expensive to obtain.
In addition, you have to enter the number of ETFs you own because at the moment it is not possible to retrieve your data from the broker. With the advent of Open Banking, it is hoped that this data can be easily and securely retrieved via API.

## Liability
I am not your financial adviser, nor is this tool. Use this program cautiously as it will give you indicators that can help you make investment decisions. Despite the fact that these indicators have proven their usefulness in the past, the truth is that no one can predict the future with any accuracy.
None of the contributors to this project are liable for any loses you may incur. Be wise and always do your own research.

