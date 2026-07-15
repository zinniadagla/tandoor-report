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
Mean daily winter revenue rose from ₹7.684 in the pooled baseline to ₹9.341 in Winter 2025, a rise of about 
₹1.657 per operating day (+21,6%). A Welch t-test gives t = 5,1304 (p < 0,001) and Cohen's d = 0,5936, a medium effect. 
The extra revenue comes to ₹69.458 over the clean winter window after the coal and staffing costs.
The verdict is a partial hit. The revenue rise is significant and medium in size, and the full winter makes a profit overall. 
It does less well on its narrowest target. The January-February weak season rose by ₹1.315 per day (+20,1%) against 
the pooled baseline, but on its own it does not pay for the tandoor's running cost. Measured against the most recent prior winter, 
the extra Jan-Feb revenue of ₹52.084 sits below the ₹61.660 running cost for those two months, a net of -₹9.576. The seasonal 
gap narrowed only a little, from 28,1% below non-winter to 26,5%.

Note: Winter 2025 is a single post-intervention winter (n = 1). The results fit a positive tandoor effect but cannot rule 
out other year-specific causes. Claims are stated as association, not proof, and the 2026 figure is a projection under 
stated assumptions, not a prediction.

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

The winter window is November to February. Diwali is treated as a confound and handled separately, since it brings a revenue 
spike that has nothing to do with the tandoor. Winter 2025 has no Diwali days inside the window, which gives a cleaner test. 
Both a full-winter and a non-Diwali baseline have been calculated, and the non-Diwali baseline is used for the statistical comparison.
Testing uses Welch's t-test with the Mann-Whitney U test as a non-parametric check, and Cohen's d for effect size. Section 7 
runs the comparison again under other assumptions (trimmed data, single-year baselines, a Diwali-adjusted baseline) to see 
whether the result depends on any one of these choices. Section 2.7 sets out the operational context, including where the 
tandoor sits at the restaurant entrance. A photograph of the tandoor in operation is included there.

| File | Content |
|---|---|
| tandoor_report.ipynb | The full report: code, tables, and graphs |
| restaurant_data.xlsx | Source data (daily sales and monthly expenses) |
| images/tandoor.jpg | Photograph of the tandoor at the restaurant entrance (Figure 1, Section 2.7) |

## Running it
The notebook reads restaurant_data.xlsx from the same folder, so both files need to sit together. 
Run the notebook from top to bottom; it prints the tables in order and draws eight graphs.
Requires: pandas, numpy, matplotlib, scipy.

## Data
daily_sales holds one row per calendar day with the date, day name, and revenue. Closed days carry no revenue 
and are marked as closures. Closed days are operational closures giving staff rest around busy festival periods, 
not holidays; festival days themselves appear as operating days.
monthly_expenses holds the monthly cost lines used for the profit calculation in Section 6.
All figures are pre-income-tax. Income tax is left out because rebate thresholds make tax liability 
differ across years for reasons unrelated to how the business performed.

## Conventions
All numbers use European formatting: period as the thousands separator, comma as the decimal separator. 
So ₹1.234,56 is one thousand two hundred thirty-four rupees and fifty-six paise.
Point differences between percentages are reported in percentage points (pp).



