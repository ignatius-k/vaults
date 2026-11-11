Product Variant Eligibility Workflow
- Clarification of product variant scoring responsibilities.
- Delegation of customer and product filtering to loan processors.
- Integration of eligibility criteria for product selection displays.

Standardization of Customer Risk and Loan Parameters
- Definition of minimum and maximum age, salary, and loan thresholds.
- Mapping of KYC information and CSC credit risk outputs.
- Categorization of customers based on risk flags and financial profiles.

Customer Classification and Data Integration
- Requirement for distinguishing between agents and standard customers.
- Integration of specific flags within the customer model.
- Utilization of customer identification for loan product analysis.

		- Customer classification will be done using the feature of custom fields, and then the required field can be used on the product filtering, to make a certain customer section eligible for a particular loan product variant

Loan Processing Segmentation Strategy
- Implementation of customer and agent loan categorization.
- Integration of type-based discrimination within the processing module.
- Addition of custom fields for KYC module data identification.
		- This is about loan processor we dont need to add it now

Product Filtering and Risk Categorization Protocols
- Implementation of customer-type specific product visibility.
- Definition of loan product characteristics and financial thresholds.
- Establishment of risk category requirements for user access.

		- Risk category is part of the scoring attributes, so in product filtering it should be possible to add a filter based on the risk category

Financial Eligibility and Loan Caps
- High-profile executive eligibility for substantial financial limits.
- Strict adherence to individual credit and risk profiles.
- Maximum loan amount determined by the lower of personal eligibility or product constraints.



Financial Fee and Interest Rate Structuring
- Identification of diverse product charge categories.
- Implementation of interest rates, setup fees, and penalty assessments.
- Development of dynamic and simplified financial calculation methods.

Loan Lifecycle and Financial Processing
- Unified group discussion on business and technical perspectives.
- Loan origination and proposal submission process.
- Application of disbursement charges during the initial loan phase.

Debt Collection Lifecycle Dynamics
- Initial accumulation of interest on outstanding loans.
- Application of penalties following missed payment deadlines.
- Escalation of charges during prolonged collection efforts.

Configuring Loan Charge Structures
- Event-based charge application
- Tenure-dependent penalty triggers
- Implementation of maximum charge limitations

Financial Configuration Dynamics
- Implementation of maximum application limits for service charges.
- Lifecycle event triggers for flexible charge configuration.
- Distinction between interest accrual methods and fee structures.

Configurable Product Charge Architecture
- Implementation of independent and configurable charge structures.
- Integration of charge components into product valuation.
- Requirement for systematic charge pool creation for product competitiveness.

Loan Product Charge Configuration
- Classification of short-term and long-term loan goals.
- Definition of interest-based charge types and contribution percentages.
- Establishment of applicable timeframes for financial assessments.

Configurable Product Charge Framework
- Implementation of customizable charge sets for financial products.
- Integration of interest and penalty fee pools within product structures.
- Definition of collection timing and disbursement protocols for automated deductions.

Product Charge Configuration Framework
- Definition of standardized charge models for product assignment.
- Configuration of calculation methods including fixed values and percentage-based rates.
- Implementation of pre-collection and post-collection timing parameters.

Configurable Charge Parameter Framework
- Implementation of ten flexible charge parameters.
- Requirement for selection and contribution logic in product creation.
- Inquiry regarding pre- and post-correction fund allocation.
- Configurable Charge

-------------------------------------------

Product Information/ Data is not to be shared with the Scoring Engine for determining the customer's eligibility
The customer's score ie risk category, and financial eligibility are sent to the loan processor, then using the product configuration and scoring attributes, the loan processor will determine if customer is eligible for product variant

This eligibility will be calculated on the fly, since storing computed requires reading the whole customer profiles to make updates


Product Filtering Criteria
Criteria to determine which customer is eligible for the variant
This is meant to use the customer attributes; including the custom fields, and also the scoring attributes

For products, add variant
- ability or feature to show the business case or the value of this new variant
	- number of customers eligible
	- number of customers eligible with active score
	- percentage of customers eligible
	- overall min and overall max

