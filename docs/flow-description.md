🌐 [Leer en Español](flow-description_ES.md)

# Flow Description

This document explains the functional workflow of the Box Stock Management System.

## 1. Responsible Selection

The user starts the app by selecting a responsible person.

### Validation
- The app does not allow the workflow to continue unless a responsible user is selected.
- The list of available users comes from the SharePoint Employee Master list.
- Only active and authorized employees are shown.

---

## 2. Counting Context Setup

Once the responsible user is selected, the user defines the counting context:
- sector/location
- product state
- package size

This helps standardize stock records and improve traceability.

---

## 3. Product Search

The user searches for a product using:
- model
- description
- product code
- franchise/reference

### Validation
- The app does not allow quantity entry until a product has been selected.

---

## 4. Count Entry

After selecting a product, the app:
- highlights the selected item
- confirms which product is selected
- enables quantity input
- allows optional observations

### Validation
- Quantity is required
- Quantity accepts numeric values only
- Empty submissions are blocked

---

## 5. Record Storage

When the user confirms the count:
- the entry is stored in the SharePoint stock list
- the selected context is preserved
- the responsible user is associated with the record

This creates traceable and centralized stock data.

---

## 6. Weekly Summary Review

The app includes a summary view where users can:
- filter by date
- filter by area/sector
- filter by product/model
- review total quantities
- expand details of each grouped item

This allows operational review of the weekly stock status.

---

## 7. Email Reporting

At the end of the process, the user can trigger a report by clicking the mail button.

### Confirmation step
The app displays a confirmation message before sending the report.

### Power Automate flow
The flow:
1. receives the request from Power Apps
2. gets the required stock records
3. structures the report data
4. generates an Excel file
5. names the file automatically according to the counting week
6. sends the email to the relevant stakeholders

---

## 8. Final Outcome

The final result is a digitized stock management process with:
- responsible-user validation
- structured and centralized records
- weekly visibility
- improved traceability
- reduced manual effort
- automated communication

---

## Notes

This document describes the functional process at a high level.  
Implementation details may vary depending on the Power Apps and Power Automate configuration.
