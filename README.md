![CC BY SA](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)

### Update

Because of my own holiday schedule, I did not update the tables the past weeks. I will be backfilling the data going into next year while also providing more formats and better visualization tools.

### Downloads
[2015](2015/)

### US Equities Correlation Analysis
This project publishes a weekly correlation matrix of all US equities with 
daily trading activity. The correlation analysis is based upon the equity
returns of the last 50, 100, 200, and YTD trading days. Underlying price data
is sourced from a premium market data vendor and correlations are calculated on
split/dividend adjusted log returns.


### Data Files
Every Saturday, four sets of correlation matrices are created, archived, and
uploaded containing the 50, 100, 200, and YTD equity correlation matrices. The
git repository only functions as a download URL mirror and index to the
externally hosted files. Each 7zip correlation matrix archive contains three
files, the actual correlation matrix, a list of symbols contained in the
respective analysis, and the date range of the calculations. 

The compressed files and their contents use the following naming pattern:

    enddate_window.ext
    
    20151106_200d.7z
        20151106_200d.csv
        20151106_200d_symbols.csv
        20151106_200d_dates.csv
    
    20151106_YTD.7z
        20151106_YTD.csv
        20151106_YTD_symbols.csv
        20151106_YTD_dates.csv



### CSV Format
The data CSV files contain large square correlation matrices. The header row is
a comma delimited list of symbols, where the first header field is empty. The
first field in each row is an equity symbol followed by the corresponding
correlations of that symbol to the column symbols. Example:


|      | AAPL | GOOG | IBM  | QQQ  | SPY  |
|------|------|------|------|------|------|
| AAPL | 1.00 | 0.41 | 0.53 | 0.76 | 0.70 |
| GOOG | 0.41 | 1.00 | 0.45 | 0.67 | 0.56 |
| IBM  | 0.53 | 0.45 | 1.00 | 0.67 | 0.72 |
| QQQ  | 0.76 | 0.67 | 0.67 | 1.00 | 0.95 |
| SPY  | 0.70 | 0.56 | 0.72 | 0.95 | 1.00 |


### Python Pandas Example

    > df = pd.read_csv('20151106_YTD.csv', index_col=0, header=0)
    > df.AAPL.GOOG
      0.40999999999


### Contact
If you have comments or issues, please [file an issue]
(http://github.com/astocko/equities_corr/issues/new) or contact me on twitter,
[@astocko](http://twitter.com/astocko).

### License
US Equities Correlation Analysis by [Alexander Stocko](http://github.com/astocko) is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

![CC BY SA](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)
