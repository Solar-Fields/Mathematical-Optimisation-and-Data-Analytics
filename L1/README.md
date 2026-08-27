# Introduction to Business Analytics

Data analytics is the process of collecting, cleaning, processing, and analyzing data to
obtain useful information and insight.

| Concept | The Question | Example |
|---|---|---|
| **Data preparation** | Is the data usable? | Clean duplicates, missing values, dates, combine datasets |
| **Descriptive analytics** | **What happened?** | Sales dashboard, traffic trends |
| **Predictive analytics** | **What is likely to happen?** | Forecast demand, predict churn |
| **Prescriptive analytics** | **What should we do?** | Optimise delivery routes/inventory |
| **Supervised ML** | Do we have a target/label? | Predict house price / churn |
| **Unsupervised ML** | No target — can we find structure? | Customer segmentation |
| **Reinforcement learning** | Can an agent learn actions from rewards? | Route/control/recommendation decisions |

## Duplicate Emails Task

### 1. Excel Tables

The source datasets were converted into Excel Tables:

- `master`
- `sub`

Structured references were then used instead of fixed cell ranges. This allows
formulas to automatically include new rows added to the datasets.

In the file `Processing` the emails are cleaned using formulas:

```excel
=LOWER(TRIM(A2))
```
and duplicates counted using:
```excel
=COUNTIF($B$2:$B$14,B2)
```
They are then combined and cleaned using the ``Power Query`` method. Which confines the data processing steps into a single dynamic pipeline which can be loaded into excel as an excel table, making it easier to reference for analysis:
```
master ──┐
         ├→ Append → TRIM → LOWER → Remove Duplicates → Output
sub ─────┘
```
The process can be viewed by clicking on `Queries & Connections` in the excel search bar. 

Finally, the summary statistics are created to find the overlapping emails between `sub` and `master` in:

- `Summary`

```excel
=FILTER(mastertrim,COUNTIF(subtrim,mastertrim))
```


