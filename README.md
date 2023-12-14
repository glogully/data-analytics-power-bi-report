# Power BI Data Analysis and Reporting Project

## Overview

## Project Description

I was approached by a medium-sized international retailer to significantly enhance their business intelligence processes using Microsoft Power BI. They had accumulated a vast amount of sales data from their global operations over the years. My primary objective was to transform this extensive dataset into actionable insights for informed decision-making. My project involved several critical phases:

### Data Extraction and Transformation
- My initial task was to gather and refine data from diverse sources, ensuring it was clean, consistent, and ready for analysis.

```sql
SELECT
    s.customer_id,
    s.purchase_amount,
    s.purchase_date,
    c.customer_name,
    c.region
FROM
    SalesData s
JOIN
    CustomerData c ON s.customer_id = c.customer_id
WHERE
    s.purchase_amount > 0 AND
    s.purchase_date >= '2023-01-01'
ORDER BY
    s.purchase_date;
```

```python
import pandas as pd
import numpy as np

csv_data = pd.read_csv('sales_data.csv')
excel_data = pd.read_excel('customer_data.xlsx')

combined_data = pd.merge(csv_data, excel_data, on='customer_id', how='inner')

combined_data.fillna(value=np.nan, inplace=True)

combined_data.columns = combined_data.columns.str.lower().str.replace(' ', '_')

combined_data['purchase_date'] = pd.to_datetime(combined_data['purchase_date'])

cleaned_data = combined_data[combined_data['purchase_amount'] > 0]
```

### Data Modeling
- I developed a robust, star-schema-based data model. This model served as the backbone for all analyses and visualizations, providing a streamlined and efficient structure for the data.
![image](https://github.com/github8585/data-analytics-power-bi-report/assets/55400003/4390313d-cf49-4c3e-b86e-95f59821efd3)

### Report Designing
- I was tasked with creating a multi-faceted Power BI report that catered to two main audiences:
  - For C-suite executives, it provided a high-level business summary, focusing on key metrics and trends.
  - For more detailed operational insights, I analyzed customer segmentation by sales region, evaluated top-performing products categorized by type against their sales targets, and integrated a geographic visual that highlighted the performance of various retail outlets.

**Customer Detail:**
![Customer Detail](https://github.com/github8585/data-analytics-power-bi-report/assets/55400003/0d113fb9-3a43-4896-9450-9aebc59c4e5d)

**Executive Summary:**
![Executive Summary ](https://github.com/github8585/data-analytics-power-bi-report/assets/55400003/78089baf-71f6-4482-a2ad-510e7b269153)

**Product Detail:**
![Product Detail](https://github.com/github8585/data-analytics-power-bi-report/assets/55400003/eca130be-b20b-485c-b16e-8d368eaea65c)

**Store Map:**
![Store Maps](https://github.com/github8585/data-analytics-power-bi-report/assets/55400003/8a6388c3-b103-4307-816f-5027ff1610e1)

My ultimate goal was to equip the retailer with a comprehensive tool that not only reflected past and present performances but also offered strategic insights to guide future business decisions.

## Problem Addressed by the Project

The core issue I addressed was the retailer's challenge in harnessing their extensive, multi-source sales data for strategic decision-making. This data, though rich in potential, was scattered and unprocessed, hindering the extraction of valuable insights. The retailer faced several challenges, including:

- **Data Overload:** Effectively managing and interpreting large volumes of data from multiple international sources.
- **Lack of Cohesive Analysis:** Integrating various data streams into a single, coherent analytical framework.
- **Inadequate Reporting Tools:** Developing a reporting system that not only provided a comprehensive overview for executive decision-making but also delved into specific operational areas like customer segmentation, product performance, and regional sales analysis.

My role was to create a solution that transformed this complex data landscape into a clear, actionable business intelligence tool, facilitating better strategic planning and decision-making for the retailer.


## Contents

1. **Data Import and Transformation Guide**: Instructions on importing and transforming data from various sources such as Azure SQL Database and Azure Blob Storage, focusing on:
   - Ensured data privacy by removing sensitive information.
   - Split date and time into separate fields.
   - Standardized table structures and column names.

2. **Data Modeling and Analysis Guide**: A step-by-step guide to constructing a robust data model, which includes:
   - Created a continuous date table for time intelligence.
   - Developed a star schema for efficient data relationships.
   - Implemented DAX measures for dynamic calculations.
   - Established hierarchies for in-depth temporal and geographical analysis.

3. **Visualization Guides**: Detailed walkthroughs for crafting visual reports on Power BI, including:
   - Executive Summary Page: Highlighted key business metrics with card visuals and time-series charts.
   - Customer Detail Page: Analyzed customer behavior using donut and line charts, along with interactive slicers.
   - Product Detail Report: Focused on product performance with gauges, area charts, scatter graphs, and more.

## Repository Structure

- **Data Models**: Contains the Power BI data model files.
- **Scripts**: Includes DAX scripts for measures and calculated columns.
- **Documentation**: The `ReadMe` files and guides for data modeling, import, transformation, and visualization.
- **Visuals**: Directory of exported visualizations and report templates.

## Usage

To get started with this project:
1. Clone the repository to your local machine.
2. Open the Power BI files in Power BI Desktop.
3. Follow the guides to set up the data model and import data.
4. Use the visualization guides to replicate or customize the dashboards.

## Contributions

Contributions are welcome. If you wish to contribute:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.

---

For detailed instructions on each component, refer to the individual guides provided within this repository. Ensure all data transformations and measure calculations are accurate before creating visualizations.

Happy data analyzing and report generating!
# data-analytics-power-bi-report671
