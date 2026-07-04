# -PhonePe-Transaction-Analysis-Dashboard
📈 Interactive **Power BI** dashboard for analyzing **PhonePe transaction data**, featuring KPIs, trends, state-wise analysis, and business insights.
If you mean the Power BI code behind this dashboard, there isn't a single source code that can recreate it. A Power BI dashboard is made using:

Power Query (M) – for data cleaning
DAX Measures – for calculations
Visual formatting – charts, cards, slicers, buttons, images, etc.

From the screenshot alone, I can't recover the exact code.

Here are DAX measures similar to what this dashboard would use:

Total Transactions =
SUM(Transactions[Transaction_Count])
Total Value =
SUM(Transactions[Transaction_Amount])
Unique Users =
DISTINCTCOUNT(Transactions[User_ID])
Successful Transactions =
CALCULATE(
    SUM(Transactions[Transaction_Count]),
    Transactions[Payment_Status] = "Successful"
)
Success Rate =
DIVIDE(
    [Successful Transactions],
    [Total Transactions]
) * 100
Failed Transactions =
CALCULATE(
    SUM(Transactions[Transaction_Count]),
    Transactions[Payment_Status] = "Failed"
)
Pending Transactions =
CALCULATE(
    SUM(Transactions[Transaction_Count]),
    Transactions[Payment_Status] = "Pending"
)
Transaction Value Growth % =
VAR CurrentValue = [Total Value]
VAR PreviousValue =
    CALCULATE(
        [Total Value],
        DATEADD(Calendar[Date], -1, MONTH)
    )
RETURN
DIVIDE(CurrentValue - PreviousValue, PreviousValue)

For the visuals:

KPI Cards → Total Transactions, Total Value, Unique Users, Success Rate
Area Chart → Transactions Over Time
Donut Chart → Age Segment Contribution
Column Chart → Service Transaction Value
Bar Chart → Top 5 Users
Donut Chart → Weekday vs Weekend Usage
Slicers → Month, Payment Status

If you want the exact same PhonePe dashboard, upload either:

the Power BI (.pbix) file, or
the dataset (Excel/CSV).

Then I can provide all the DAX measures, Power Query code, and even recreate the dashboard step by step.
