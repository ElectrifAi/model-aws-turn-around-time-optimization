# Input/Output specifications:
- Input: A **zip file** with 5 comma separated csv. Reference file: sample.zip
- Details for each csv file:
    - agent.csv
        - Required columns:
            - agent_id: unique id of agent
            - agent_experience: number of cases owned by agent
            - agent_location: location of agent

    - commodity.csv
        - Required columns:
            - commodity_id: unique id of commodity
            - comm_category_name: category name
            - special_commodity_ind: flag select commodity which historically had higher tendency for contracting
            - special_commodity_ind_change: indictor whether the commodity has changed

    - supplier.csv
        - Required columns:
            - supplier_id: unique id of supplier
            - supplier_unknown_ind: flag if supplier is known or unknown
            - new_supplier_ind: flag if supplier is a new supplier
            - contract_supplier: flags if the supplier has existing contract
            
    - user_profile.csv
        - Required columns:
            - user_id: unique id of user_profile 
            - user_experience: number of requests opend by user 

    - request.csv
        - Required columns:
            - commodity_id: Unique identifier assigned to each commodity type
            - agent_id: Unique identifier assigned to each agent
            - user_id: Unique identifier assigned to each user (case preparer)
            - case_age_days: age of the case in days
            - case_age_hours: Total time the case was open
            - case_category: category of the case
            - case_open_dow: day of week of the case open
            - case_owner: Name of employee who owns the case
            - case_status: case status
            - cast_last_modified_by: Name of employee who has most recently updated the case
            - num_close_tot: number of cases closed till date 
            - num_open_tot: number of cases opened till date
            - num_uniqueid: number of times particular uniqueID received in datasnapshot till date
            - req_financial_account: Financial account from which the purchase will be budgeted
            - req_order_status: Identifies status of the order: whether it's been ordered, approved, cancelled, has been received by the user, etc.
            - req_purchasing_unit: Pruchase Unit in which the requester works
            - req_ship_to_location_country: Country to which commodity will be shipped
            - req_ship_to_location_state_region: State/region to which commodity will be shipped
            - req_sum_spend: Total spend amount for the purchase request
            - req_sum_spend_change: indicator whether the total spend has changed
            - req_work_type: work type of request
            - resolution_note_available: flag if the free text resolution note for PR is populated
            - resolution_note_available_change: flag if resolution note changed
            - time_from_first_view: time between today and uniqueID appears for 1st time
            - today_day_of_week: day of week of data snapshot
            - supplier_id: Unique identifier assigned to each supplier
            - approval_days: time taken to get approval
            - case_last_modified_date_days: days from last modified date till snapshot date
            - req_initial_submit_date_days: days from initial submit date till snapshot date
            - req_need_by_date_days: days from the request open date till snapshot date
            - next_working_date_days: days from next working date till snapshot date
            - case_opened_datetime_days: days from the request open date till snapshot date
            - requestID: unique id of input data
        - Optional columns:
            - pu_sector: sector of purchase request calculated
            - TAT_day(target): turn around time of case in # days, If end user do not have this optional column, a column with all missing values shoud be placed.
            - TAT_bucket(target): turn around time bucket of case
- Output: A list of JSON objects containing 'requestID' and 'Score' fields . 'Score' contains model's prediction of turn-around-time bucket for the request. Reference file: sample.zip.out
