## Project Overview

The **Student Performance Dashboard** is a comprehensive Power BI solution designed to analyze and visualize **academic performance and student demographics**.
The dashboard enables educators, administrators, and decision-makers to identify trends, compare performance across subjects and classes, and monitor overall student outcomes using interactive visuals.

This project follows **industry-standard Power BI architecture**, including proper data modeling, clean transformations, and reusable DAX measures.

## Objectives

* Analyze student performance across **subjects and exams**
* Compare results by **gender, class, and section**
* Identify **high-performing and low-performing students**
* Provide **interactive insights** using slicers and drilldowns
* Maintain a **scalable, exam-ready Power BI model**

## Data Sources

The dashboard uses **Excel files** as data sources.

### 1️⃣ Students.xlsx

| Column Name | Description               |
| ----------- | ------------------------- |
| StudentID   | Unique student identifier |
| Name        | Student full name         |
| Gender      | Male / Female             |
| Class       | Academic class/grade      |
| Section     | Class section             |

### 2️⃣ Scores.xlsx

| Column Name | Description                   |
| ----------- | ----------------------------- |
| StudentID   | Foreign key to Students table |
| Subject     | Academic subject              |
| Exam        | Exam name/type                |
| Score       | Marks obtained                |

## 🔄 Data Transformation (Power Query)

All transformations were performed using **Power Query Editor**.

### Key Steps:

* Removed null and duplicate records
* Ensured correct **data types** (StudentID as numeric/text key, Score as whole/decimal number)
* Renamed columns for clarity
* Validated referential integrity between tables

No hard-coded logic was applied to ensure **future scalability**.

## Data Model

The project follows a **Star Schema** design.

### Relationships:

* `Students[StudentID]` → `Scores[StudentID]` (One-to-Many)
* Cross-filter direction: **Single**
* Cardinality optimized for performance

This structure ensures:

* Accurate aggregations
* Better performance
* Cleaner DAX measures

## DAX Measures Used

All calculations are implemented using **explicit DAX measures** (no implicit measures).

### Core Measures:

```DAX
Total Students = DISTINCTCOUNT(Students[StudentID])
```

```DAX
Total Score = SUM(Scores[Score])
```

```DAX
Average Score = AVERAGE(Scores[Score])
```

```DAX
Max Score = MAX(Scores[Score])
```

```DAX
Min Score = MIN(Scores[Score])
```

## Visuals Used

The dashboard uses a mix of **analytical and storytelling visuals**:

| Visual Type            | Purpose                         |
| ---------------------- | ------------------------------- |
| KPI Cards              | Total Students, Average Score   |
| Clustered Column Chart | Subject-wise performance        |
| Bar Chart              | Gender-wise comparison          |
| Matrix Table           | Student-level detailed scores   |
| Pie / Donut Chart      | Section or class distribution   |
| Slicers                | Class, Section, Subject, Gender |

## Interactivity & Filters

* **Slicers** for Class, Section, Subject, Gender
* Cross-highlighting between visuals
* Drill-down enabled where applicable
* Responsive layout for different screen sizes

## Performance Optimization

* Star schema modeling
* Single-direction relationships
* Measures instead of calculated columns
* Clean Power Query steps
* No unnecessary visuals or heavy custom visuals

## Insights Enabled

* Identify **top and bottom performing students**
* Compare performance across **subjects and exams**
* Detect **gender-based trends**
* Monitor **class-wise academic outcomes**
* Support **data-driven academic interventions**

## Tools & Technologies

* **Power BI Desktop**
* **Power Query**
* **DAX**
* **Excel (Data Source)**

## File Information

* `Power BI Live project.pbix` – Main Power BI report file
* `README.md` – Project documentation

## Conclusion

This project demonstrates a **professional Power BI workflow**, suitable for:

* Academic evaluation
* Portfolio projects
* Interview demonstrations
* Real-world educational analytics use cases

The dashboard is **scalable, optimized, and exam-ready**, following Microsoft Power BI best practices.
