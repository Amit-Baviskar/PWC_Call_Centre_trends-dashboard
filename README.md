# Call Center Performance Analysis Report


## Introduction:
 This report presents the findings from a data analysis project using a Power BI dashboard to monitor and improve the performance of a call center. The analysis is based on a dataset provided by PwC, and the goal was to visualize key performance indicators (KPIs) such as call resolution rates, customer satisfaction, and agent performance. The dashboard offers stakeholders insights into call center efficiency and highlights areas for improvement.

## Table of Contents:

- Introduction
- Problem Statement
- Stakeholders
- Data Preparation
- Data Modeling & DAX Measures
- Insights

# Problem Statement:
The objective of this project was to create an interactive Power BI dashboard for the call center manager, providing relevant KPIs and metrics from the dataset. The dashboard was designed to identify operational bottlenecks, monitor agent performance, and track customer satisfaction levels. Key performance indicators include:

- Overall call resolution rate
- Number of calls answered versus abandoned
- Average speed of answering calls
- Customer satisfaction scores
- Agent-specific performance metrics

## Stakeholders:

- Call Center Manager: Responsible for monitoring and improving call center performance, ensuring customer issues are resolved efficiently, and maintaining a high level of customer satisfaction.
- Customer Support Agents: Their performance metrics are tracked and analyzed, such as the number of calls answered, issues resolved, and customer feedback scores.
- Senior Management: Interested in the overall performance of the call center, particularly trends in customer satisfaction and operational efficiency.
- Data Analysts: Responsible for analyzing the data and providing insights to improve call center operations and agent performance.

## Data Preparation:
The dataset used in this analysis contains 10 columns and 5000 rows of call center data, with information such as call status (answered or abandoned), resolution status, and customer satisfaction scores. The data preparation steps included:

- Cleaning: Removing unnecessary columns and rows, and validating the data types to ensure consistency.
- Transforming: The data was loaded into Power Query for cleaning and transformation before being imported into Power BI for analysis.
- Validation: Ensuring that each field, such as "Answered (Y/N)" and "Resolved," had the correct values and were properly formatted for calculations.

## Data Modeling & DAX Measures:
The cleaned data was modeled using Power BI, and several key DAX (Data Analysis Expressions) measures were created to calculate and display relevant KPIs on the dashboard. Below are some of the key DAX measures:

- Answered Count: This calculates the number of calls that were answered.

       AnsweredCount = CALCULATE(
       COUNT(CallData[Call Id.2]),
       CallData[Answered (Y/N)] = "Y"
       )
- Month: This extracts the month from the call date to analyze call patterns over time.


      Month = FORMAT(CallData[Date], "MMMM")

- Resolved Count: This calculates the number of calls that were resolved.


       Resolved_Count = CALCULATE(
       COUNT(CallData[Call Id.2]),
       FILTER(CallData, CallData[Resolved] = "Y")
       )
These DAX measures allowed us to compute the number of answered and resolved calls, along with other metrics, which were crucial for analyzing overall call center performance

## Insights:
The analysis of the call center data provided several key insights:

### Call Answering and Resolution Rates:

81.08% of the calls were answered, with a similar percentage of issues being resolved. This indicates that the majority of customer issues were addressed during the calls.
However, 18.92% of calls were abandoned or left unresolved, highlighting potential inefficiencies that need to be addressed to improve service quality.

### Customer Satisfaction:

The average customer satisfaction score was 3.40, with most ratings falling between 3 and 4. There was a noticeable dip in customer satisfaction from January to March, suggesting that service quality may have declined over this period.


### Agent Performance:

Joe had the fastest average speed of answering calls but did not have the highest resolution rate.
Jim had the highest resolution rate despite a slower response time, indicating that a lower speed of answering calls might not necessarily correlate with poor performance.
Becky had the slowest response time but was able to resolve a high percentage of calls.


### Monthly Call Trends:

January saw the highest number of answered calls, while both February and March showed a decrease in both answered and resolved calls. This trend may point to seasonal factors or operational challenges during these months.

### Call Topics:

Most calls were related to streaming and payment issues, followed by technical support and administrative support. These insights can help the call center allocate resources more efficiently to address frequently occurring issues.

### Conclusion:
The Power BI dashboard successfully provided a detailed analysis of the call center’s operations, highlighting key metrics such as customer satisfaction, call resolution rates, and agent performance. Based on these insights, stakeholders can take targeted actions to improve service efficiency, optimize agent performance, and ultimately enhance the customer experience.
