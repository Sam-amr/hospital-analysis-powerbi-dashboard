# Hospital Analysis Dashboard using Power BI

## Project Overview

This project presents an interactive Hospital Analysis Dashboard developed using Power BI to analyze patient admissions, treatment costs, hospital performance, departmental efficiency, and operational KPIs.

The dashboard helps stakeholders monitor hospital operations, identify trends, improve resource allocation, and support data-driven healthcare decisions.

## Business Problem

Hospitals generate large amounts of operational and patient data daily. However, without proper visualization and analytics, it becomes difficult for management to:

- Monitor patient trends

- Track departmental performance

- Analyze treatment costs

- Evaluate occupancy and resource utilization

- Identify operational inefficiencies

This dashboard was created to transform raw healthcare data into actionable insights.

## Project Objectives

- Analyze patient admissions and discharge trends

- Monitor hospital department performance

- Track treatment and operational costs

- Evaluate patient demographics and age distribution

- Identify busiest departments and peak admission periods

- Create an executive-level dashboard for quick decision-making

## Tools & Technologies Used 

- Power BI

- Power Query

- DAX

- Microsoft Excel 

- Data Modeling

- Data Visualization

## Data Cleaning & Transformation

The following preprocessing steps were performed using Power Query:

-Removed duplicate records

-Handled missing/null values

-Standardized department names

-Converted date columns into proper datetime format

-Created calculated columns for Month and Year analysis

-Corrected inconsistent categorical values

-Created relationships between tables

## Data Modeling

A star schema model was implemented to improve dashboard performance and ensure proper relationship management.

### Key relationships included:

Date Table ↔ Admissions Table

Department Table ↔ Patient Records

Doctor Table ↔ Treatment Records

### Model optimization techniques:

Removed unnecessary columns

Optimized relationships

## Key Performance Indicators (KPIs)

The dashboard includes the following KPIs:

1) Total Patients
2) Treatment Cost
3) Average Length of Stay
4) Ongoing Treatment Rate
5) Success Rate
6) Failure Rate

## Executive Summary Page 

### KPIs Included: 

- Total Patients
- Total Cost 
- Average Length of Stay
- Ongoing Treatment Rate
- Success Rate
- Failure Rate

### Features:

- Interactive slicers
- Dynamic KPI cards

This page helps management monitor operational performance and identify trends requiring immediate attention. 

## Hospital Operations Analysis

This dashboard page focuses on operational efficiency and patient flow analysis.

### Visuals Included: 

- Department Patient Load
- Monthly Admissions Trend
- Treatment Outcome Distribution

### Key Insights: 

- Identified departments with highest patient load
- Analyzed seasonal admission trends
- Compared successful vs unsuccessful treatment outcomes

This analysis helps hospital administrators optimize staffing and departmental planning.

## Department Performance Analysis 

This page evaluates hospital department efficiency using operational and financial KPIs.

### Visuals Included: 

- Average Stay by Department
- Department-wise Cost Analysis
- Department Occupancy Metrics

### Key Insights: 

- Departments with highest operational costs
- Departments with longest patient stay durations
- Occupancy distribution across departments

Supports management decisions related to budgeting, infrastructure planning, and operational optimization.

## Doctor Performance Analysis 

This dashboard page evaluates doctor-level performance metrics and workload distribution.

### Visuals Included: 

- Doctor Workload Analysis
- Doctor Success Rate
- Doctor Summary Table

### Key Insights: 

- Doctors handling highest patient volumes
- Performance comparison among doctors
- Treatment success patterns
- Workload balancing opportunities

This analysis supports performance evaluation, staffing decisions, and healthcare quality improvement.

## Patient Demographics Analysis

This page analyzes patient demographics and recovery trends.

### Visuals Included: 

- Gender Distribution
- Recovery by Age Group
- Age Distribution Of Patiennts 

### Key Insights: 

- Most common patient age groups
- Recovery rate variations by age
- Gender-wise patient distribution
- Demographic treatment patterns

Helps hospitals improve patient targeting, treatment planning, and demographic-specific healthcare services.

## Treatment Analysis

This dashboard page evaluates treatment performance and operational trends.

### Visuals Included: 

- Treatment Success Rate
- Weekly Treatment Trends
- Comparative Outcome Analysis

### Key Insights: 

- Weekly treatment performance fluctuations
- Success rate trends over time
- Treatment efficiency analysis
- Operational treatment patterns

Supports quality monitoring and healthcare performance improvement.

## DAX Measures Used In The Project 

### 1. Avg Length of Stay: 

Avg Length of Stay = AVERAGE(Patients[Length Of Stay]) 

### 2. Department Patient Count:

Department Patient Count = COUNT(Patients[PatientID]) 

### 3. Failure Rate: 

Failure Rate = DIVIDE(
    CALCULATE(
        COUNT(Treatments[TreatmentID]),
        Treatments[Outcome] = "Failure"
    ),
    COUNT(Treatments[TreatmentID])
) 

### 4. Ongoing Treatment Rate: 

Ongoing Treatment Rate = DIVIDE(
    CALCULATE(
        COUNT(Treatments[TreatmentID]),
        Treatments[Outcome] = "Ongoing"
    ),
    COUNT(Treatments[TreatmentID])
) 

### 5. Success Rate:

Success Rate =  DIVIDE(
    CALCULATE(
        COUNT(Treatments[TreatmentID]),
        Treatments[Outcome] = "Success"
    ),
    COUNT(Treatments[TreatmentID])
) 

### 6. Total Cost:

Total Cost = SUM(Treatments[Cost]) 

### 7. Total Patients: 

Total Patients = DISTINCTCOUNT(Patients[PatientID]) 

## Future Improvements

- Add predictive analytics using Python
- Integrate SQL database connectivity
- Implement real-time hospital monitoring
- Add machine learning-based patient risk analysis
- Improve mobile responsiveness

## Conclusion

This project demonstrates how Power BI can transform raw healthcare data into meaningful business insights. The dashboard enables hospital management to monitor operational performance, improve patient care, and support strategic decision-making through data-driven analysis.
