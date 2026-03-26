🌐 [Leer en Español](data-model_ES.md)

# Data Model

This document describes the main data sources used in the Box Stock Management System.

## 1. SharePoint List: Employee Master

This list is used to validate who can perform stock counts.

### Purpose
To provide the app with a controlled list of employees available for stock counting.

### Example fields
- **Name**: Employee full name
- **Active**: Yes/No field indicating whether the employee is active
- **Email**: Employee email address
- **Roles**: Assigned operational roles or skills

### Usage in the app
- Filters only active employees
- Displays only employees assigned to stock-related tasks
- Provides the responsible user selected at the beginning of the workflow

---

## 2. SharePoint List: Box Stock Records

This list stores all stock counting records entered from Power Apps.

### Purpose
To centralize stock count information and allow traceability, filtering, reporting, and weekly summaries.

### Example fields
- **ProductCode**: Internal code of the box model
- **Description**: Product description
- **Sector**: Area where the stock was counted
- **State**: Product state (for example, bundled or bagged)
- **Pack**: Packaging size (for example, x100)
- **Quantity**: Counted quantity
- **Responsible**: User who performed the count
- **CountDate**: Date of the stock count
- **BatchWeek**: Weekly grouping used for reporting
- **Observations**: Optional notes entered by the user

### Usage in the app
- Stores each stock entry
- Supports weekly stock summary views
- Supports filtering by product, sector, area, and date
- Feeds the Power Automate reporting process

---

## 3. Reporting Output

The reporting process generates an Excel file based on the weekly stock records.

### Purpose
To distribute current stock information to relevant production stakeholders.

### Contents
The report may include:
- Product code
- Description
- Sector
- State
- Pack
- Quantity
- Responsible
- Date
- Weekly batch

### Output channel
- Sent by email through Power Automate
- Can be filtered online or downloaded for further analysis

---

## Notes

This repository contains an anonymized functional representation of the data model.  
Sensitive business information has been removed or generalized.
