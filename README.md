# Fraud Detection System

## Overview
This repository contains SQL logic designed to detect potentially fraudulent user activities based on discrepancies between user location, IP address, and mobile carrier information. If the information such as `location_name`, `sub_ip`, `user_ip_country`, `sub_carrier_country`, `user_carrier_country`, and `prefix` are not matching, users might be flagged as suspicious.

## Structure
The core logic is divided into two main parts:

1. `user_submission_data`: A Common Table Expression (CTE) that collates data on user submissions including IP addresses, mobile carriers, and determined actions based on discrepancies.
2. `carrier_check_data`: A CTE that verifies the mobile carrier data against the location data.

The final query joins these two CTEs to extract the necessary fields for the detection of potential fraud.

## Usage
1. Update the date placeholders `{{ date.start }}` and `{{ date.end }}` in the SQL script with the desired date range.
2. Ensure you have a connection to the relevant database.
3. Execute the SQL script to obtain the results which will list potentially fraudulent users based on the mentioned criteria.

## Dependencies
Ensure your database contains the following tables with respective fields:

- `submissions`: Stores data about user submissions.
- `users`: Information about users including their IP and mobile carrier.
- `locations`: Provides details about locations associated with submissions.
- `projects`: Project-related data.

## Contribution
Feel free to raise issues or PRs if you think some part of the logic can be improved or if there are any discrepancies in the results.
