# Dump Summary Report Automation (Google Apps Script)

🚀 Overview

This project automates the generation of a store-wise dump summary report using Google Apps Script.

The script reads structured data from a Pivot sheet, dynamically maps SKUs and store names, and populates a Summary sheet with the corresponding dump values.

This eliminates manual lookup operations and ensures accurate, scalable reporting across multiple SKUs and stores.

🧠 Problem Statement

In retail and inventory workflows, generating a dump summary matrix (SKU vs Store) typically requires:

Manual lookups across large pivot tables
Repetitive copy-paste operations
High chances of mismatches and errors
Time-consuming report preparation

As the number of SKUs and stores increases, this process becomes inefficient and difficult to maintain.

🎯 Objective

To build an automated solution that:

Maps SKUs to corresponding store-level dump values
Dynamically reads data from a pivot structure
Populates a structured summary table
Reduces manual intervention and errors
✅ Solution Approach

The solution leverages Google Apps Script to:

Read pivot data from the Pivot sheet
Extract:
Store names (from Summary header row)
Cleaned SKUs (from Summary column)
Identify:
SKU column (cleaned sku)
Store header row (origin)
Match each SKU with each store
Retrieve corresponding dump values
Populate results into the Summary sheet
⚙️ How the Script Works
🔹 Step 1: Access Sheets
Source: Pivot sheet
Target: Summary sheet
🔹 Step 2: Extract Inputs
Store names → Row 2 (columns B onward)
SKUs → Column A (from row 3 onward)
🔹 Step 3: Identify Key Positions
Finds column index for "cleaned sku"
Locates row where "origin" appears (store headers)
🔹 Step 4: Data Mapping Logic

For each SKU:

Search for its row in pivot data
For each store:
Find corresponding column
Extract intersecting value
🔹 Step 5: Build Output Grid

Creates a 2D array representing:

SKU vs Store → Dump Values
🔹 Step 6: Write to Summary Sheet
Outputs results starting from cell B3
Maintains alignment with SKUs and store headers

🛠️ Setup Instructions
Open your Google Sheet
Go to Extensions → Apps Script
Paste the script
Save the project
Run fillDumpSummary()
🔄 Optional Automation
Add a time-driven trigger for periodic updates
Use on-edit trigger for real-time updates
📈 Key Benefits
⏱️ Eliminates manual VLOOKUP/XLOOKUP effort
📊 Enables scalable SKU vs Store reporting
🔁 Ensures consistent data mapping
❌ Reduces mismatch and data errors
⚡ Improves reporting speed significantly
🔍 Use Cases
Retail store performance tracking
SKU-level inventory analysis
Dump/wastage monitoring
Multi-store reporting dashboards
Business analytics and internship projects
🚀 Future Enhancements
🔹 Optimize performance (avoid repeated .findIndex() calls)
🔹 Add support for dynamic pivot structures
🔹 Implement caching for faster execution
🔹 Add error logging and validation alerts
🔹 Build visualization dashboards (Power BI / Looker Studio)
🔹 Enable export to CSV or automated email reports
