RETAIL-BANK-TRANSACTION-AND-CUSTOMER-ANALYSIS
1. BACKGROUND
- This project simulates a real-world scenario for a US-based retail bank (Aurora Bank). The bank processes thousands of transactions daily across multiple states. However, the Risk Management and Operations teams flagged concerns regarding a high volume of transaction failures and a growing segment of over-leveraged customers.

2. OBJECTIVES
- This dashboard serves a dual purpose: acting as an Operational Tracker to monitor daily transaction volumes, customer engagement, and geographic performance, and a Diagnostic Instrument to investigate the root causes of transaction errors and assess credit risk (Debt-to-Income ratios) to support targeted mitigation strategies.

3. WORKFLOW
- The project execution followed a structured end-to-end BI development lifecycle:

Phase 1: Requirement Analysis & Design

Problem Definition: Identified core business objectives — tracking transaction health, profiling customer demographics, and diagnosing operational risks (failed transactions & DTI exposure).

Dashboard Prototyping: Planned the layout using a dark navy-blue financial theme, defining specific KPIs and charts across 3 distinct pages: Executive Overview, Customer, and Risk & Operations.

Phase 2: Data Pre-processing (Excel)

Initial Sanitation: Conducted preliminary checks on the raw dataset (2K+ customers, 157K+ transactions) to handle missing values and correct data types.

Standardization: Formatted Date columns, normalized Currency fields (USD), and cleaned categorical data (e.g., standardizing card types and transaction methods).

Phase 3: ETL & Data Modeling (Power Query - Power BI)

Data Transformation: Used Power Query to filter out irrelevant columns and anomalies (e.g., handling outlier minimum income values).

Schema Design: Built a relational data model connecting Customer Demographics, Transaction Logs, and Credit Information.

Phase 4: Analytics Engine (DAX - Power BI)

Measure Creation: Wrote complex DAX formulas to calculate dynamic business metrics.

Key Measures: Total Transactions, Total Transaction Amount, Average Transaction Value.

Risk/Logic Measures: Error Rate %, Average Debt-to-Income (DTI) Ratio, Active/Inactive Customer Rate.

Phase 5: Visualization & Storytelling (Power BI)

Visual Implementation: Built interactive charts (Sparklines, Scatter Plots, Treemaps, Matrices) tailored for financial analysis.

UX/UI Design: Implemented a consistent left-side navigation pane, sticky slicers (Card Type, Brand, Method), and interactive tooltips to enhance executive user experience.

4. INSIGHTS
Page 1: Executive Overview (Transaction Dynamics)

<img width="2845" height="1619" alt="Ảnh chụp màn hình 2026-02-23 145758" src="https://github.com/user-attachments/assets/1cae98fa-adea-4e26-be2c-6efac9184a84" />


Digital Channel Dominance: The breakdown of transaction methods reveals a massive reliance on digital banking. Online Transactions account for the absolute majority at 67.53% ($4.64M), dwarfing Swipe (17.12%) and Chip (15.35%) transactions.

Geographic Concentration: The state-level heatmap indicates that major economic hubs—specifically Texas, California, New York, and Florida—are the primary drivers of transaction volume.

-> Insight: The bank has successfully transitioned its user base to digital platforms. However, this heavy reliance means the digital infrastructure must have 99.9% uptime.

-> Strategic Action: IT infrastructure budget should be prioritized for the mobile/web banking app to handle peak online loads. Marketing teams should allocate higher budgets for localized campaigns in the top-performing states (TX, CA, NY, FL) to capture further market share.

Page 2: Customer Intelligence (Demographics & Behavior)

<img width="2874" height="1621" alt="Ảnh chụp màn hình 2026-02-23 145822" src="https://github.com/user-attachments/assets/006e21be-2ee1-48bb-ab51-9925ab160dcf" />


The "Dormant" Segment: While the bank has an even gender split and a healthy average credit score (709.73), the Transaction Participation Rate chart reveals that 84,85% (about 1700 users) are completely Inactive Customers.

Income-Spending Correlation: The scatter plot demonstrates a positive correlation between Yearly Income and Transaction Amount. However, the majority of customers are clustered in the <$100K income bracket with conservative spending habits.

-> Insight: The bank is efficiently acquiring users but struggling with full retention/activation. Furthermore, the high-income segments are under-utilized.

-> Actionable Strategy: Implement automated "Win-back" or re-engagement email campaigns offering cash-back incentives for the 85% inactive users' first transaction. For the high-income outliers shown on the scatter plot, Wealth Management teams should cross-sell premium tier credit cards (e.g., Visa Infinite/Mastercard World Elite) to stimulate higher transaction amounts.

Page 3: Risk & Operations (Fraud & Failures)

<img width="2878" height="1616" alt="Ảnh chụp màn hình 2026-02-23 145835" src="https://github.com/user-attachments/assets/0cc3ab02-0cb5-4ba6-a17e-955b1aa478ad" />

The Over-leverage Crisis (DTI): The dashboard uncovers a critical financial risk: 1.34K customers are flagged as "Critical Risk", driving the Average Debt-to-Income Ratio to an alarming 138.17%. This segment accounts for a massive 67.05% of the DTI Risk Group Breakdown.

-> Insight: A large portion of the customer base is holding debt that exceeds their yearly income. This presents a severe vulnerability to default (bad debt) if economic conditions worsen.

-> Risk Mitigation Action: Immediately freeze proactive credit limit increases for the "Critical Risk" segment. The bank should launch financial wellness programs or offer debt consolidation loans to help these customers restructure their debt safely.

Operational Bottlenecks (Error Rates): Out of 157.2K transactions, 2.74K failed (1.74% Error Rate). The Treemap explicitly isolates "Insufficient Balance" and "Bad PIN" as the dominant root causes. The Matrix further shows that Online Credit/Debit transactions suffer the highest error rates (up to 2.6%).

-> Root Cause Discovery: The failures are not driven by banking system outages but by user-end friction (forgetting passwords/PINs or poor personal fund management).

-> Operational Shift: To recover lost transaction volume, the product team must optimize the app UX. Recommend implementing Biometric Authentication (FaceID/Fingerprint) for online checkouts to eliminate "Bad PIN" errors. Additionally, set up proactive "Low Balance Warning" push notifications before users attempt transactions that will bounce.
