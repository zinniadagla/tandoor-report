# Evaluating the Tandoor Intervention on Winter Revenue

This report looks at whether adding a tandoor to a restaurant raised winter revenue and profit. The tandoor was 
switched on 27 October 2025. The analysis compares the winters of 2023 and 2024 (before the tandoor) against 
Winter 2025 (after) and projects Winter 2026. The restaurant is fully vegetarian and works entirely within the 
Indian market. All money values are in Indian Rupees. The tandoor was already owned, bought in 2021, so its purchase 
price is treated as a sunk cost, and only the operating cost is charged against the revenue gain.

## Question
Winter revenue ran below the rest of the year. The tandoor sells winter items (tandoori rotis, parathas, soya chaap, paneer tikka) 
whose demand peaks from November to February and drops away by March. The question is whether using the tandoor raised 
winter revenue enough to pay for its own coal and staffing, and whether it narrowed the seasonal gap it was meant to fix.

## Main result
Mean daily winter revenue rose from ₹7.684 in the pooled baseline to ₹9.341 in Winter 2025, a rise of about ₹1.657 per operating day 
(+21,6%). 
A Welch t-test gives t = 5,1304 (p < 0,001) and Cohen's d = 0,5936, a medium effect. Revenue also became steadier: the coefficient 
of variation fell from 35,7% to 30,8%. After the coal and staffing costs, that leaves a net of ₹69.458 over the winter window, which 
carries no Diwali days.

Section 9 scores the tandoor against seven criteria: five hits and two partials. The revenue rise is significant and medium in size, 
revenue became more predictable, and the full winter makes a profit overall. It does less well on its narrowest target. 
The January-February weak season rose by ₹1.315 per day (+20,1%) against the pooled baseline, but on its own it does not 
pay for the tandoor's running cost. Measured against the most recent prior winter, the extra Jan-Feb revenue of ₹52.084 
sits below the ₹61.660 running cost for those two months, a net of -₹9.576. The profit margin fell from 17,5% in Winter 2024 to 14,1%
and the seasonal gap narrowed only a little, from 28,1% below non-winter to 26,5%.

Note: Winter 2025 is a single post-intervention winter (n = 1). The report shows what happened alongside the tandoor, 
not that the tandoor caused it, and other year-specific causes cannot be ruled out. The 2026 figure is a projection built 
on stated assumptions, not a prediction.

## Method
The analysis works through nine sections:
| Section | Content |
|---|---|
| 1 | Executive summary |
| 2 | Methodology and data integrity |
| 3 | Descriptive baseline (Winters 2023 and 2024) |
| 4 | Post-intervention analysis (Winter 2025) |
| 5 | Statistical testing |
| 6 | Effect quantification and profitability |
| 7 | Sensitivity analysis |
| 8 | Winter 2026 forecast |
| 9 | Conclusion |

The winter window is November to February. Diwali, a major Indian festival whose dates shift each year, 
is treated as a confound and handled separately, since it brings a revenue spike that has nothing to do with the tandoor. 
Winter 2025 has no Diwali days inside the window, which gives a cleaner test. Two versions of the 2023-2024 baseline have been
calculated, one including Diwali days and one excluding them. The non-Diwali version is used for the statistical comparison.

Testing uses Welch's t-test with the Mann-Whitney U test as a non-parametric check, and Cohen's d for effect size. 
Section 7 runs the comparison again under five scenarios: closed days counted as zero revenue, a 2024-only baseline, 
the top 5% of days removed, a Diwali-adjusted Winter 2025, and a higher coal cost. 
Each one tests whether the result depends on that single choice.

Section 2.7 sets out the operational context, including where the tandoor sits at the restaurant entrance. 
It includes a photograph of the tandoor in operation.

## Limitations
Section 9.2 of the report sets out three limits: Winter 2025 is a single season, so the tandoor cannot be 
separated from a year that was strong for another reason; some of the rise may come from the tandoor being 
visible at the entrance rather than from the food; and the net figure treats all the extra revenue as the tandoor's, 
which is an assumption, not a measurement.

A fourth is noted here. Daily revenue is not independent from one day to the next. Table 3.4 shows a day-of-week 
pattern before the tandoor, and Table 4.3.1 shows the same pattern after it. Some days are simply busier than others, 
so knowing the day already tells you something about the revenue.

Welch's t-test and the Mann-Whitney U test in Section 5 both assume every day is a separate piece of information. 
Because the days follow a weekly rhythm, there is less information here than the day count suggests. 
The p-values are therefore more confident than the data allows. The size of the effect and its direction 
still hold; only the confidence is overstated. The report does not measure how strong the pattern is, 
which would need an autocorrelation check I did not run. A time series model would handle this properly.

I found this after the report was written. I have left the analysis as it was run rather than revise it quietly, 
because the error states what I am missing more exactly than I could: I can run a method, but I could not tell 
which method the data was asking for.

## Files
| File | Content |
|---|---|
| tandoor_report.ipynb | The full report: code, tables, and graphs |
| restaurant_data.xlsx | Source data (daily sales and monthly expenses) |
| images/tandoor.jpg | Photograph of the tandoor at the restaurant entrance (Figure 1, Section 2.7) |

## Running it
The notebook reads restaurant_data.xlsx from the same folder, so both files need to sit together. 
Run the notebook from top to bottom; it prints the tables in order and draws eight graphs.
It requires pandas, numpy, matplotlib and scipy.

## Data
daily_sales holds one row per calendar day with the date, day name, and revenue. Closed days carry no revenue 
and are marked as closures. These days are operational closures giving staff rest around busy festival periods, 
not holidays; festival days themselves appear as operating days.
monthly_expenses holds the monthly cost lines used for the profit calculation in Section 6.
All figures are pre-income-tax. Income tax is left out because rebate thresholds make tax liability 
differ across years for reasons unrelated to how the business performed.

## Conventions
All numbers use European formatting: period as the thousands separator, comma as the decimal separator. 
So ₹1.234,56 is one thousand two hundred thirty-four rupees and fifty-six paise.
Point differences between percentages are reported in percentage points (pp).



