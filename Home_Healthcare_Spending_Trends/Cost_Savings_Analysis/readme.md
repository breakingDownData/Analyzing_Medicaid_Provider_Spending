# Question: What if HCPC Prices Remained the Same?
## OR at minimum, saw a moderate increase in paid/claim YoY
- I will be investigating HCPC codes that saw a significant increase in paid/claim
    - some (T1019) saw as high as 200% increase across 6 years
    - what if these increases weren't the case?
        - what if the costs stayed (relatively) level compared to 2018?
        - shouldn't the government have more say into what they pay providers for services?
    - what would the difference in paid be?
        - which practices see significant savings amounts?
- flip-side, which codes have remained the same (or similar)? 

# Methods:
- Calculate a monthly increase percentage that equates to the year-end payment increase
- Find the first month in which a provider is paid for a certain HCPC, grab the paid/claim
  - for a specific servicing + billing NPI + HCPC
- Calculate the paid/claim using the monthly payment increase for each subsequent month the same Servicing + Billing provider are paid for the same claim
- The difference in calculated paid/claim and actual claim * claim volume = savings
  - e.g. With an 8% annual increase in paid/claim:
    - HCPC T1019 was paid at $45/claim for provider 123456789 (not a specific NPI) as of 2018-01 
    - In 2023-01 T1019 should be paid at $66.12/claim (8% increase for 5 years), actual is 98/claim
    - With 1,000 claims, this payment regulation would amount to $31,880 (98-66.12)*1000

# Assumptions: 
- 8% increase YoY for each code's paid per claim
- Analysis doesn't account for risk adjustment
  - don't have the data
- Starting paid/claim could come from a month with non-adequate claims volume
- HCPC payment methods could've changed
  - i.e. payments are based on a multiple of the units in 2018, in 2024 they're paid out at a higher rate with no accounting for units

# Background Info
#### Data source: https://opendata.hhs.gov/datasets/medicaid-provider-spending/
#### Accompaniment: https://www.youtube.com/watch?v=ocAf1rK3fxE&list=RDZgruBu-puKE&index=3