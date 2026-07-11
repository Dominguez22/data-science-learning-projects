# Megaline Prepaid Plans Analysis

## Project Description

This project analyzes customer behavior and revenue for two prepaid plans offered by Megaline: Surf and Ultimate. The goal is to understand how customers use each plan and determine which one generates more revenue on average. Using data for 500 customers, the analysis examines call activity, text message usage, internet consumption, and monthly revenue patterns.

The work includes data cleaning, exploratory analysis, and hypothesis testing to provide a data-driven recommendation for the marketing team. The results are intended to support better decisions about advertising spend and plan positioning.

## Plan Description

Megaline rounds seconds to minutes and megabytes to gigabytes. For calls, each individual call is rounded up so that even a one-second call counts as one minute. For web traffic, the monthly total is rounded up, so usage of 1025 MB in a month is billed as 2 GB.

### Surf

- Monthly fee: $20
- Includes: 500 minutes, 50 SMS, and 15 GB of data
- Overage rates:
  - 1 minute: $0.03
  - 1 SMS: $0.03
  - 1 GB: $10

### Ultimate

- Monthly fee: $70
- Includes: 3000 minutes, 1000 SMS, and 30 GB of data
- Overage rates:
  - 1 minute: $0.01
  - 1 SMS: $0.01
  - 1 GB: $7

## Data Dictionary

The project uses five datasets:

### users
- user_id: unique user identifier
- first_name: user first name
- last_name: user last name
- age: user age in years
- reg_date: subscription date
- churn_date: date the user stopped using the service (missing values indicate the user was still active when the data was collected)
- city: user city of residence
- plan: selected tariff plan

### calls
- id: unique call identifier
- call_date: date of the call
- duration: call duration in minutes
- user_id: identifier of the user who made the call

### messages
- id: unique message identifier
- message_date: date of the message
- user_id: identifier of the user who sent the message

### internet
- id: unique session identifier
- mb_used: amount of data used in megabytes
- session_date: date of the session
- user_id: user identifier

### plans
- plan_name: name of the tariff plan
- usd_monthly_fee: monthly fee in US dollars
- minutes_included: included minutes per month
- messages_included: included SMS per month
- mb_per_month_included: included data in megabytes
- usd_per_minute: price per minute after the included limit is exceeded
- usd_per_message: price per SMS after the included limit is exceeded
- usd_per_gb: price per GB after the included limit is exceeded

## Project Workflow

1. Load and inspect the data files.
2. Prepare the data by converting to appropriate types and cleaning errors.
3. Aggregate usage metrics by user and month.
4. Estimate monthly revenue for each user based on plan rules.
5. Analyze customer behavior by plan.
6. Perform hypothesis testing to compare average revenue between plans and regions.

## Key Findings

- Ultimate users tend to use more calls, messages, and internet data than Surf users.
- The Ultimate plan generates higher average monthly revenue per user in this sample.
- Statistical testing shows a significant difference in average revenue between the two plans.
- Revenue also differs significantly between users in the NY-NJ region and users in other regions.

## Conclusion

The analysis suggests that the Ultimate plan is the stronger revenue-generating option for Megaline in this dataset. Its higher base fee and greater average usage levels make it more profitable on average, although regional differences also appear to influence customer spending patterns.

