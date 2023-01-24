# eerie_dreq
Workings for EERIE data request

The Excel files in the `xls` directory were generated by dreqPy version 1.2.0 using the commands:

```
python3 -m venv ../../venvs/dreqpy
. ../../venvs/dreqpy/bin/activate
pip install dreqpy xlsxwriter
export LANG=en_GB.utf8
export LOCALE=en_GB.utf8

drq -m HighResMIP -e HighResMIP -p 3 --xls
```

The final PRIMAVERA data request is available at:

```
PRIMAVERA/PRIMAVERA_Data_Request_v01_00_13.xlsx
```

The first attempt at a data request is in the `eerie_first_draft` directory. `PRIMAVERA_top_50.xlsx` is from version 1.2.0 of dreqPy and I have modified the variables manually. `HighResMIP.xlsx` is the original unmodified output from dreqPy for reference. In the modified spreadsheet I have aimed to keep the top approximately 50 most frequently accessed variables from PRIMAVERA using Appendix C from [10.5281/zenodo.3961931](https://doi.org/10.5281/zenodo.3961931). Approximately 50 variables were chosen as this included the most frequently accessed monthly, daily and sub-hourly variables. This aim was achieved by just keeping the Amon, Oday, SIday and day tables and a few high frequency variables. The Omon and SImon tables would have been left in but they were not included by dreqPy and the reason for this needs to be investigated and these tables added. The following high frequency variables were added at a frequency of 6 hours: pr, psl, tas, uas, vas and zg. These variables were chosen because they are surface only and were the most frequently accessed in Appendix C. Most of these high frequency variables were available in the 6hrPlevPt table, but pr had to be taken from the custom Prim6hr table, which was not ideal but should be easy to implement; Prim6hr could also be renamed to something more appropriate for EERIE.

I am not very experienced with Excel and so this could be implemented in a more efficient way. I had to do much manual copying and pasting. It is also difficult to test that I have not made any errors. In a programming language I would write unit tests to check for errors. Ideally this spreadsheet should be carefully reviewed by someone else to check for errors. I will try some manual error checking myself over the next few days.

Please note that I have hidden many columns so that I could see the dimensions column and the data volumes column.
