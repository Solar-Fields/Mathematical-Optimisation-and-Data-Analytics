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

The first example (duplicate_emails_ETL.csv) contains two lists of emails; master and sub. both lists can be arbitrarily large but are smaller for practicing purposes. Both contain duplicate emails and emails with blank spaces or capitalised versions. 
The process begins by cleaning the data. 

```excel
=FILTER(master[Trim],COUNTIF(sub[Trim],master[Trim])>0)
```
