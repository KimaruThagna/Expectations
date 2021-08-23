# Expectations
Using the great expectations open source tool to validate data as a process within the general data engineering pipeline context

# Project Initialization
 To initialize a project, run the command `great_expectations --v3-api init`
# Connect to data source 
Run the following command and follow the prompts to connect the project to a new data source `great_expectations --v3-api datasource new`
# Create Expectations Suite

An Expectations suite is where you write machine verifiable assertions of your data. Run the command
`great_expectations --v3-api suite new`

# Edit custom expectation suite

Run the command `great_expectations --v3-api suite edit bank_transactions.transaction_expectations` In this case, the value **bank_transactions.transaction_expectations** is the suite name

For example, a custom assertion can be 
1. that bank transactions can only be from 2000 and above
2. A transaction action is only valid if it is WITHDRAWAL or ACTION
3. Transaction IDs have to start with the format `TX-#`

# Validation using a validation set
You can use the primary expectation suite to run validation on any new data in the format of the primary data that you used to create the primary expectation suite. For example in this case, I can have another CSV or SQL database source that has transactions data similar to `data/mock_transactions.csv` to do this, run the command `great_expectations --v3-api checkpoint new my_checkpoint`

# Further reading
The last part involves customized deployments whose documentation can be found [here](https://docs.greatexpectations.io/docs/tutorials/getting_started/customize_your_deployment)