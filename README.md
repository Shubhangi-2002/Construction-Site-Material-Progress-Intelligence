# Construction-Site-Material-Progress-Intelligence


### Project Overview

ConstructionOS is a construction analytics proof of concept focused on monitoring residential construction progress and material inventory through structured data and interactive dashboards.

The project demonstrates how construction-related operational data can be organized, processed, and analyzed using:

- **MySQL** – Database design, relational data management, triggers and backend logic
- **SQL** – Data queries and operational analysis
- **Power BI** – Interactive dashboards and reporting
- **DAX** – KPI calculations and analytical measures
- **Simulated Data** – Workflow-based construction project records

The primary objective is to demonstrate how data analytics can support project monitoring, inventory control, operational transparency, and management decision-making.

### Project Objectives

- Develop a relational database structure for construction operations.
- Represent site-level workflows through progress updates and inventory transactions.
- Implement SQL backend logic for automatic stock updates.
- Create decision-oriented Power BI dashboards.
- Analyze construction progress and material utilization.
- Demonstrate the application of analytics in construction and operations management.

### Real-World Workflow Representation

| Operational Role | Activity | Database Representation |
|---|---|---|
| Site Engineer | Updates flat-level work progress | `progress_tracking` |
| Storekeeper | Records material receipts and issues | `material_transactions` |
| Project Manager | Reviews construction progress and stock | Power BI dashboards |
| Management | Monitors overall project performance | Executive Summary |

**Data note:** All records used in this proof of concept are simulated. The database structure and workflows are designed to represent typical residential construction operations.

### Database Design – MySQL

The database consists of 16 tables organized into four major functional areas.

**1. Construction Structure**
- Projects
- Wings
- Floors
- Flats

**2. Progress Tracking**
- Task_Master
- Subtask_Master
- Progress_Status
- Progress_Tracking

**3. Materials & Inventory**
- Material_Inventory
- Material_Transactions
- Material_Stock_Summary

**4. Users & Operational Governance**
- Users
- Contractors
- Departments

**5. Experimental RCC Activity**
- RCC_Slab_Sheet
- RCC_Column_Sheet

Primary and foreign key relationships represent construction dependencies, including the hierarchy:

`Project → Wing → Floor → Flat`

### SQL Backend Logic & Inventory Management

Material stock calculations are handled at the MySQL database level rather than being independently recalculated in Power BI.

MySQL triggers automatically update the stock summary whenever material transactions are recorded.

**Stock calculation workflow:**

- Opening Stock – Initial available quantity
- Received Quantity – Increases available stock
- Issued Quantity – Decreases available stock
- Current Stock – Latest available balance maintained in the summary table

This separation keeps transaction processing and reporting responsibilities distinct.

### Power BI Dashboards

**1. Executive Summary Dashboard**

Purpose: Provide management with an overview of construction and inventory performance.

Key metrics:
- Overall project progress percentage
- Completed and in-progress flats
- Material inventory value
- Contractor count
- Construction progress trends over time

**2. Flat Progress Tracker**

Purpose: Monitor construction activities at individual flat level.

Features:
- Wing, floor and flat-level drilldown
- Task-wise and subtask-wise progress tracking
- Status filtering: Not Started, In Progress and Completed
- Flat-level completion percentage
- In-progress subtask count
- Last updated date
- Daily progress trend
- Task-level progress table

This dashboard supports detailed monitoring of construction activities and work completion.

**3. Material Inventory Dashboard**

Purpose: Monitor material availability and inventory movement.

Features:
- Opening stock, received quantity, issued quantity and current stock KPIs
- Low, Medium and High stock classification
- Material-wise received versus issued analysis
- Conditional formatting for low-stock materials
- Category, unit and stock-level slicers
- Separate analysis of inventory transactions and current stock

### SQL, DAX & Analytics Implementation

The project incorporates the following analytical techniques:

- Custom DAX measures for average progress per flat.
- Latest subtask-level progress aggregation.
- Context-aware KPIs responding to report slicers.
- `HASONEVALUE()` for controlling KPI visibility.
- SQL triggers for automatic inventory updates.
- Relational data modelling using primary and foreign keys.
- Separation of backend calculations and Power BI reporting logic.

### Technology Stack

| Layer | Technology |
|---|---|
| Database | MySQL |
| Data Modelling | Relational Schema |
| Backend Logic | SQL Triggers |
| Analytics | Power BI |
| Query Language | SQL |
| Calculations | DAX |
| Version Control | GitHub |

### Business & Research Applications

ConstructionOS demonstrates how analytics can support construction project management through:

- Operational process mapping
- Structured information flow
- Data-driven progress monitoring
- Inventory visibility and control
- Management reporting
- Construction operations analysis

The project can also serve as a proof of concept for academic research involving construction operations and management analytics.

### Current Limitations

- All data is simulated.
- RCC activity tables are not fully integrated into the dashboards.
- No frontend or data-entry application is currently available.
- Predictive analysis is not yet implemented.

### Future Enhancements

- Develop a web-based interface using HTML, CSS and JavaScript.
- Integrate API-based data ingestion.
- Implement role-based access control.
- Introduce construction delay prediction.
- Develop material demand and stock forecasting.

### Key Learning Outcomes

- Understanding relational database design for operational workflows.
- Applying SQL triggers to automate inventory updates.
- Translating operational requirements into structured data.
- Building interactive Power BI dashboards.
- Developing DAX measures for business reporting.
- Separating database processing from visualization.
- Identifying opportunities for data-driven operational improvements.

