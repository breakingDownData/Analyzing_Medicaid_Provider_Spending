# Analyzing Medicare Spending  
- HHS Recently Published a >200M+ row dataset, consisting of
  - Provider-level Medicaid spending data from T-MSIS, aggregated by billing or servicing provider, procedure code, and month. Covers fee-for-service, managed care, and CHIP claims from 2018-2024.
  - (As of) Feb 9, 2026 HCPC level payments between 2018 and 2024 
- [source] (https://opendata.hhs.gov/datasets/medicaid-provider-spending/)
  - schema is listed in the above link
  - feel free to download the set yourself, the dataset sizes are significant
    - The Parquet file is 3.3GB
      - My project will be written to read in parquet, i found this method more effective in getting the data loaded
    - CSV is 11GB (!!!)

# in this project i will
- Show how to start analyzing a dataset with significant rows
- Create guidelines for analysts in order to develop their investigative skills
  - or if you are a causal investigator, i provide guidelines that allow quick + easy access to investigating yourself!
- Comment code allowing those reading to easily follow along
- Provide production-level code ready to be fit into data pipelines
- Highlight QA opportunities intra-notebook in order to ensure no holes in data processing

# Jumping off points:
- What does the home health spending look like from 2018 - 2024?
  - is it as bad as people think?
- What provider(s) have seen a significant in/decrease in Medicaid payments?
  - where are these providers located? 
    - Find the government database with provider identifier  
- What Code(s) have seen a significant in/decrease in Medicaid payments?
  - need to bring in HCPC code categories in order to better group swaths of codes
    - e.g. 'Home health' related HCPCs are not all the same codes
    - your office visits w/your PCP are billed in range 99211-99215, depending on the type of visit
      - CPT code 99211: is a Level 1 Evaluation and Management (E/M) code for a face-to-face, low-level, established patient office visit
      - 99215: highest-level evaluation and management (E/M) code for established patient office or outpatient visits, requiring high-level medical decision-making (MDM) or 40–54 minutes of total time on the encounter date
        - source: google gemini '99215 HCPC'
    - grouping by HCPC category can allow you to see a shift from low-level severity to high-severity codes
      - typically, higher severity codes are paid out at a higher rate than lower severity
 
