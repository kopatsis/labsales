Sales Data Integration & Reporting System
Overview
This system is a high-performance, locally hosted analytics and reporting solution designed to ingest, normalize, store, and report on detailed sales and customer data. At its core is a PostgreSQL database that consolidates transactional data from multiple e-commerce channels and ad hoc data sources.

Developed for operational and compliance needs, this system ensures accurate, timely, and structured financial insights, with reporting tailored to internal analytics, strategic planning, and external tax documentation.

System Architecture
Data Sources
Shopify

One primary storefront

One ancillary storefront

WordPress (WooCommerce)

Three separate ancillary sites

CSV Import

Bulk upload capability for historical or supplemental datasets

Data Ingestion
A Go-based application manages all data acquisition and integration processes. This application:

Interfaces directly with platform APIs or ingests structured CSVs

Extracts and harmonizes multi-channel data

Performs conditional insert and update logic to ensure database consistency

Uses GORM for ORM-level interaction with PostgreSQL

Data Model
The PostgreSQL schema is designed to support a comprehensive sales dataset, including but not limited to:

Order-Level Data

Subtotals, shipping, taxes, tips, total discounts

Order timestamps and metadata

Line-Item Details

SKU, product ID, quantity, unit price, item-level discounts

Customer Information

Contact and shipping information

Account type segmentation (e.g., wholesale vs. retail)

Reporting Capabilities
All reports are generated in Excel (.xlsx) format using the Excelize library. Data extraction and transformation is executed via hundreds of structured queries orchestrated by Go code. Report generation includes dynamic formatting and embedded data visualization where applicable.

Monthly Reports (Rolling Year)
Segmented by customer type

Metrics include:

Monthly and trailing 12-month sales totals

Order volumes

Average sales per order

Year-to-date aggregates

Four-year month-over-month historical comparison

Includes top-performing wholesale customers with individualized reporting

Quarterly Tax Report
Daily aggregates by line item:

Subtotals, discounts, shipping, tips, taxes

Quarterly roll-up summaries

Optimized format for direct inclusion in accounting systems or tax filings

Ad Hoc Wholesale Customer Reports
Generated on request (typically Q1)

Customer-specific summaries of:

Total sales

Tax paid

Discounts received

Shipping fees

Designed to support downstream tax and financial reporting at the customer organization level

Deployment & Execution
This application is designed for local execution due to the high volume and sensitivity of data involved.

CLI interface for manual operation and report generation

Optional scheduled execution via Go-native scheduling routines

Hosted on secure, on-premises infrastructure

Code Availability
This repository serves as documentation and deployment metadata only. Application code is proprietary and not available in this repository.

For further information or to request access (where permissible), please contact the repository administrator.
