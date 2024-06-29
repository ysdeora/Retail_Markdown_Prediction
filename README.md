# Pre-Season Markdown Prediction

This document outlines the process for predicting price markdowns for future incoming SKUs based on historical behavior of items.
Overall Process
![](https://github.com/ysdeora/Retail_Markdown_Prediction/blob/main/psmf_gif.gif)

## Process Overview

The prediction process is divided into two main sections:

1. Markdown Window Prediction
2. Markdown Depth Prediction

### Section 1: Markdown Window Prediction

This section focuses on determining when markdowns are likely to start in an item's lifecycle.

#### Steps:

1. **Calculate Markdown Start Percentage for Historical Items**
   - Determine the percentage of lifecycle when markdown starts for all historical items.

2. **List Markdown Start Lifecycle Percentages**
   - Compile a list of markdown start percentages for historical items, along with MFP (Main Functional Product) information.

3. **Calculate Median Lifecycle Percentage**
   - Use the median to arrive at a single value of lifecycle percentage for each MFP group.

4. **Assign Median Lifecycle Percentage to Upcoming Items**
   - For new items in future seasons, assign the median markdown lifecycle start percentage calculated for their respective MFP.

### Section 2: Markdown Depth Prediction

This section focuses on predicting the depth of markdowns for future items.

#### Steps:

1. **Calculate Single Markdown Percentage for Historical Items**
   - Use weighted average with sales to calculate a single markdown depth for all historical Article Color and Country combinations.

2. **Prepare Training Data for Attribute-Based Forecasting Model**
   - Create a data table with product attributes and location attributes as training columns and single markdown depth as the target column.

3. **Depth Prediction for Future Items**
   - Create a similar table of article attributes for future items and use the prediction model to generate markdown depth.

## Summary

The pre-season markdown prediction process combines:

1. **Lifecycle Start Percentage**: A statistical model using the median of markdown starts at the MFP level.
2. **Markdown Depth Percentage**: A machine learning model that understands generic patterns of how product attributes (brand, type, article group, department, etc.) and country relate to historical markdowns, then predicts depth for all future assortments.

This approach allows for accurate prediction of both the timing and depth of markdowns for upcoming SKUs, based on historical data and product attributes.
