
# 📝 Question 1
You have set up an incremental refresh policy for a massive sales semantic model containing several years of data. You want to make sure the incremental refresh policy runs smoothly and efficiently without causing performance issues or pulling down unnecessary historical data multiple times.

## Question: What critical requirement must be met by the data source and queries for incremental refresh to work properly in Power BI?

A) The data source must be connected via a Personal mode on-premises gateway.

B) The data source and queries must support query folding.

C) The semantic model must have query caching explicitly turned on.

D) The data source must use OAuth 2.0 authentication.

Description: Incremental refresh relies on query folding—the process where Power Query translates transformations and date filters into native queries executed directly by the data source. If query folding is not supported, Power BI would have to pull all historical data into memory every time, completely defeating the purpose of incremental refresh and causing poor performance.

(Answer : B)
---
# 📝 Question 2
You have created a massive semantic model in your company's workspace that takes a long time to refresh. To optimize performance and reduce memory consumption, you configure an incremental refresh policy. You define two specific date/time parameters in Power Query Editor to manage the sliding window for data loads.

## Question: What are the exact mandatory names you must give to these two date/time parameters in Power Query so that Power BI recognizes them for an incremental refresh policy?

A) StartDate and EndDate

B) RangeStart and RangeEnd

C) IncrementalStart and IncrementalEnd

D) FilterFrom and FilterTo
## Description 
Power BI has a strict naming convention for incremental refresh. It specifically looks for two parameters named RangeStart and RangeEnd (case-sensitive!). If you name them anything else like StartDate and EndDate, Power BI's incremental refresh engine won't recognize them and won't know how to slice the data into partitions.

(Answer B)
---
# 📝 Question 3
You have created a report and semantic model, and you want to set up an automated refresh schedule in the Power BI Service so your team doesn't have to refresh it manually. Your workspace is currently hosted on standard shared capacity (not Premium or Fabric).

## Question: What is the maximum number of daily refresh time slots you can configure for a semantic model on shared capacity?

A) 4 daily time slots

B) 8 daily time slots

C) 24 daily time slots

D) 48 daily time slots

## Description
On standard Shared Capacity, Power BI allows you to configure up to 8 daily time slots for scheduled refreshes.

If your workspace is backed by Premium or Fabric Capacity, that limit increases significantly up to 48 daily time slots (every half hour).
(Answer B)
---
# 📝 Question 4

You set up an automated refresh schedule for a critical sales semantic model connecting to an on-premises database via a gateway. A few weeks later, users report that the data is stale. When you check the settings, you discover that Power BI has automatically disabled the refresh schedule because of repeated synchronization problems.

## Question: After how many consecutive failed refresh attempts does Power BI automatically disable a refresh schedule?

A) 2 consecutive failures

B) 3 consecutive failures

C) 4 consecutive failures

D) 10 consecutive failures

## Description: Power BI will automatically disable a refresh schedule after 4 consecutive failures (or if no user views the report/dashboard for 2 months of inactivity). This is a classic exam gotcha, and you nailed it!
(Answer C)
---
# 📝 Question 5
You are planning to modify a core product table in a shared semantic model. Because this semantic model is reused across multiple reports and different workspaces in your organization, you want to see which downstream reports and dashboards will break before you make your changes.

## Question: Which built-in Power BI feature should you use to assess these downstream dependencies and identify which reports rely on your semantic model?

A) Query Caching

B) Lineage and Impact Analysis

C) Personal Gateway Configuration

D) Certified Endorsement Badge

## Description: Lineage and Impact Analysis is your absolute best friend when modifying shared assets. It visually maps out all downstream dependencies—even across different workspaces—so you can see exactly which reports and dashboards will break before you touch a single table or column.
(Answer B)
---
## 1. On-Premises Data Gateways (The Bridge)
When your data lives inside your company's physical office servers (like an on-premises SQL Server) and Power BI lives in the cloud, they can't talk to each other directly. You need a Gateway.

Standard Mode: Built for multiple users and complex enterprise scenarios. Multiple people can share connections through it.

Personal Mode: Built for a single user (just you). It can only be used with Power BI, cannot be shared with teammates, and requires your personal computer to stay turned on and online for refreshes to work.

## 2. Refresh Schedules & Limits
Instead of manually clicking refresh every time data changes, Power BI automates it.

Frequency Limits: You can schedule up to 8 daily time slots on Shared Capacity, or up to 48 time slots on Premium/Fabric Capacity.

The Big Gotcha (Failures & Inactivity):

If a semantic model's refresh fails 4 consecutive times, Power BI automatically disables the refresh schedule.

If no user visits the report or dashboard for 2 months (60 days), Power BI also disables the refresh schedule to save resources.

## 3. Incremental Refresh (The Efficiency King)
If you have billions of rows of historical data, refreshing everything every single day takes forever and crashes your system. Incremental refresh only updates what changed (e.g., the last 10 days) while keeping historical data safe.

The Magic Rule: You must create two exact date/time parameters named RangeStart and RangeEnd in Power Query Editor.

The Prerequisite: The data source and queries must support query folding (translating Power Query steps into native SQL queries run directly by the database). Without query folding, incremental refresh breaks.

## 4. Endorsement (Trusting Your Data)
When an organization has hundreds of reports, users get confused about which numbers are correct. Endorsement fixes this:

Promoted: Highlights content you think is valuable, worthwhile, and ready for others to use (anyone with write permissions can promote).

Certified: A strict, highly selective badge reserved for authoritative, single-source-of-truth models. Usually requires admin approval or special permissions.

## 5. Query Caching & Impact Analysis
Query Caching: Available on Premium/Fabric capacities. It saves the results of the initial landing page query so reports load instantly for frequent users without overloading the dataset.

Lineage & Impact Analysis: Allows you to see downstream dependencies. If you change a table column or shut down a data source, impact analysis shows you every single report and workspace across the entire company that will break.
