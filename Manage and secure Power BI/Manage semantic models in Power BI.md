
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
# 📝 Question 6
You are the sole report creator for your department, and you need to connect your Power BI Service workspace to a local, on-premises SQL Server database that sits behind your company's firewall. Because you are the only one managing this data and you want a quick setup without involving enterprise IT administrators, you decide to install a gateway on your own local workstation.

## Question: Which type of gateway installation should you choose, keeping in mind your requirement?

A) Standard mode gateway

B) Personal mode gateway

C) Virtual Network (VNet) data gateway

D) On-premises data gateway (Enterprise cluster)

## Description: Because you are the sole report creator in your organization and want to manage the gateway locally on your own desktop without enterprise IT overhead, Personal mode is precisely designed for this exact use case. Remember, Personal mode can only be used by a single user, supports Power BI exclusively, and doesn't require sharing connections with a wider team.
(Answer B)
---
# 📝 Question 7
You have configured an on-premises data gateway in standard mode to allow multiple members of your department to connect to a shared SQL Server database. One morning, team members report that their scheduled report refreshes are failing. Upon investigating the query path and architecture, you need to explain how the cloud service communicates with your on-premises server through the firewall.

## Question: Which Azure service acts as the secure cloud message queue and waiting room that bridges Power BI Service and your local on-premises gateway?

A) Azure Blob Storage

B) Azure Service Bus

C) Azure Active Directory (Entra ID)

D) Azure Event Hubs

## Description: Azure Service Bus acts as the secure cloud message broker (the waiting room) that allows the Power BI cloud service and your on-premises data gateway to securely pass queries and responses back and forth without either side needing to breach the company's inbound firewall.
(ANSWER B)
---
# 📝 Question 8
You have successfully set up your on-premises data gateway and want to configure automated refreshes for a critical semantic model that lives in your shared workspace on the Power BI service.

## Question: Assuming your workspace is on standard shared capacity, what is the maximum number of daily refresh time slots you are allowed to configure for that semantic model?

A) 4 daily time slots

B) 8 daily time slots

C) 24 daily time slots

D) 48 daily time slots

## Description: On standard shared capacity, Power BI caps your automated scheduled refreshes at 8 daily time slots. If you need up to 48 daily time slots (every 30 minutes), your workspace must be backed by Premium or Fabric capacity.
(Answer B)
---
# 📝 Question 9
You are managing a massive enterprise semantic model containing billions of rows of transaction data. To maintain high performance without overwhelming your source database, you set up a hybrid model where some dimension tables are cached in memory, while heavy fact tables query the data source live. You want certain tables to act as both Import and DirectQuery simultaneously depending on how a user interacts with the report.

## Question: What is the name of this specific hybrid table storage mode in Power BI?

A) Combined Mode

B) Dual Mode

C) Blended Mode

D) Virtual Mode
## Description: In Power BI composite models, tables can be set to one of three storage modes: Import, DirectQuery, or Dual. Tables set to Dual can act as both Import and DirectQuery simultaneously. Power BI dynamically decides whether to pull from memory (Import) or send a live query to the source (DirectQuery) depending on the needs of each specific visual or relationship, which is heavily used when working with Aggregations.

(Answer B)
---
# 📝 Question 10
You have built a core corporate sales semantic model that serves as the definitive single source of truth for the entire company. Executive leadership wants to ensure that all business units know this model is strictly vetted, authoritative, and officially approved for enterprise-wide decision-making, distinguishing it from standard user-created reports.

## Question: Which official endorsement badge should you apply to this semantic model?

A) Promoted

B) Certified

C) Verified

D) Approved
## Description: Certified is the highest, most rigorous endorsement level in Power BI. It signifies that the semantic model is an authoritative, trusted single source of truth that meets strict organizational quality standards (often requiring tenant or workspace admin approval).

Promoted, on the other hand, is used to highlight content that is valuable and ready for use, but doesn't carry the strict "authoritative single source of truth" weight of certification.

(Answer B)
---



---
# 1. On-Premises Data Gateways
Gateways act as a secure bridge between on-premises corporate firewalls (e.g., local SQL servers) and the Power BI cloud service.

## Standard Mode:

Multi-user enterprise setup.

Supports multiple data sources and multiple users.

Works with Power BI, Power Apps, Power Automate, etc.

Installed on a dedicated server running 24/7.

## Personal Mode:

Single-user setup (restricted to your account).

Power BI only. Cannot be shared.

Installed on your local desktop (must stay online for refreshes).

### 🔄 The Query Gateway Flow (Under the Hood)
Cloud Request: Power BI Service creates a query and encrypts credentials, placing them in the gateway queue.

Azure Service Bus: The gateway cloud service pushes the request to Azure Service Bus (secure cloud waiting room).

Pickup: The on-premises gateway pings Azure Service Bus and pulls the request down through outbound ports.

Decryption & Connection: The gateway decrypts credentials and connects to the local data source.

Execution: The local database runs the query.

Return Trip: Results are sent back through the gateway up to the Power BI Service.

# 2. Refresh Schedules & Limits
Frequency Limits:

Shared Capacity: Up to 8 daily time slots.

Premium / Fabric Capacity: Up to 48 daily time slots (every 30 mins).

Automatic Disabling Rules:

Power BI disables a refresh schedule after 4 consecutive failures.

Power BI disables a refresh schedule after 2 months (60 days) of total user inactivity (no one views the report/dashboard).

# 3. Incremental Refresh
Allows fast refreshing of large datasets by only updating recent changes instead of reloading historical data.

Mandatory Requirements:

Must create two exact, case-sensitive Date/Time parameters named RangeStart and RangeEnd.

The data source and queries must support query folding (translating steps into native database queries).

# 4. Endorsement, Caching, & Lineage
Endorsement Tiers:

Promoted: Highlights valuable, ready-to-use content (any workspace write-user can apply).

Certified: Strict, highly selective single-source-of-truth badge requiring organizational approval.

Query Caching (Premium/Fabric only): Saves initial landing page query results to speed up report load times and reduce capacity load.

Lineage & Impact Analysis: Visually maps downstream dependencies across workspaces so you know which reports will break before modifying tables or data sources.
