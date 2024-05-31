# Datasheet Template

As far as you can, complete the model datasheet. If you have got the data from the internet, you may not have all the information you need, but make sure you include all the information you do have. 

## Motivation

- The dataset was created to analyze and implement Modern Portfolio Theory (MPT) using historical stock data. The purpose was to demonstrate the concepts of portfolio optimization, efficient frontier construction, and asset allocation strategies. 
- The dataset was created by the author of the python notebook by querying the selected UK Stock Tickers, Date Ranges, Currency is GBP on uk.investing.com and exporting a csv.

## Composition

- The dataset comprises historical stock price data for various companies listed on the FTSE 100 index, as well as data for the FTSE 100 index itself and the United Kingdom 3-month and 6-month bond yields.   
- There are 15 files which contain historical data related to 13 Stocks, 1 Index (FTSE100) and 1 Gilt. Each file contains daily prices, opening prices, high prices, low prices, trading volumes, and percentage changes for each day starting 24th April 2021 - 24th May 2024.    
- No missing Data in the dataset
- All data in the files is non confidential and publicly available from uk.investing.com. 

## Collection process

- The data was acquired from the uk.investing.com website, as mentioned above. 
- The dataset includes stock data for 13 Stocks, FTSE 100 index, 3M Gilt between 24th April 2021 - 24th May 2024.   
- The dataset was queried on uk.investing.com on 25th May 2024. 

## Preprocessing/cleaning/labelling

- No cleaning and labelling was necessary for consuming the files downloaded from uk.investing.com.
- Following preprocessing steps were required to consume the % change data in the files as per models input requirements:
    - Converting daily stock returns to weekly returns by resampling the data.
    - Removing the last week's data to ensure complete weeks.
 
## Uses

- The dataset could potentially be used for other tasks related to portfolio optimization, risk management, asset allocation, and financial modeling. 
- One potential limitation is that the dataset only covers a specific time period (April 2021 to May 2024), which may not be representative of other market conditions or time periods.
- Consumers of the dataset should be aware that the analysis and results presented in the notebook are based on historical data and may not accurately reflect future market performance or risks.
- The dataset should not be used for tasks that require real-time or up-to-date financial data, as it represents a specific historical snapshot.

## Distribution

- The dataset for the selected Stocks, FTSE100 and UK 3M Gilt Instrument is freely available on uk.investing.com as per its terms and conditions. 

## Maintenance

- The dataset available with the model will not be updated from its original source uk.investing.com.  

