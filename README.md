# Employee Attrition Analytics

**Employee Attrition Analytics** is a data analytics project that utilises the IBM HR Analytics Employee Attrition & Performance dataset to investigate patterns in employee departures.

This project aims to support Human Resources (HR) decision-making by examining employee attrition across various factors, including department, job role, overtime status, job satisfaction, and length of service.

The analysis was conducted in Jupyter Notebook using Python and pandas for data preparation, exploratory data analysis (EDA), and statistical hypothesis testing. The findings are presented in two interactive Tableau dashboards: **Workforce Overview** and **Attrition Drivers**.

The dashboards enable users to examine key workforce metrics, compare attrition rates, and navigate between an overall summary and more detailed analyses.

The dataset contains 1,470 synthetic employee records. Therefore, the findings demonstrate analytical methods rather than describe employee behaviour in an actual organisation.

The associations observed in the analysis should not be interpreted as evidence of causation.

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

## Dataset Content

This project uses the **IBM HR Analytics Employee Attrition & Performance** dataset, which is publicly available on [Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset).

The dataset contains **1,470 employee records across 35 original columns**, covering employee demographics, job details, workplace environments, and attrition.

The dataset is entirely synthetic, consisting of simulated rather than genuine employee records. This allows HR analytics methods to be demonstrated without exposing real employees' personal information.

### Dataset Structure

Each row corresponds to one employee, and the `Attrition` column indicates whether that employee has left the organisation (`Yes`) or stayed (`No`).

The primary variables examined in this analysis are as follows:

| Variable | Description |
|---|---|
| `Attrition` | Whether an employee left the organisation |
| `Department` | Department in which the employee works |
| `JobRole` | The employee's job role |
| `OverTime` | Whether the employee engages in overtime work |
| `JobSatisfaction` | Job satisfaction rating from 1 (Low) to 4 (Very High) |
| `YearsAtCompany` | Number of years the employee has worked at the company |
| `Age` | The employee's age in years |

### Data Preparation

Initial data cleaning and preprocessing of the original dataset were conducted using Python and pandas in the `01_Data_Preparation_ETL.ipynb` notebook.

To support the analysis, additional variables were introduced:

- `Attrition_Flag`: Converts attrition into a numerical value, where 1 represents an employee who left and 0 represents an employee who stayed.
- `Age_Group`: Groups employees into various age brackets.
- `Tenure_Group`: Groups employees according to their length of service.

The cleaned dataset was exported as a CSV file and stored in a version-controlled folder to support reproducibility and future analysis.

### Dataset Limitations

While this dataset provides useful insights into workforce patterns, it has several limitations:

- The records are synthetic and do not represent real employees.
- The analysis is limited to a single dataset rather than data from multiple organisations.
- The dataset does not explain the reasons for employee departures.
- It lacks the time-based information needed to calculate a precise annual attrition rate.

These limitations are considered when interpreting the findings and developing strategic HR recommendations.

## Business Requirements

### Business Problem

Employee attrition can create significant challenges for organisations, including recruitment costs, the loss of experienced employees, and disruption to workforce continuity.

This project focuses on the Human Resources (HR) team's need to analyse employee departure patterns and identify workforce groups that warrant further examination.

The primary goal of this analysis is to provide data-driven insights that help HR stakeholders make informed decisions about improving employee retention and optimising workforce management.

### Target Audience

The target audience for this project comprises:

- **HR Managers:** Identify workforce groups experiencing higher attrition rates and assess potential retention risks.
- **Department Managers:** Understand departure patterns across departments and job roles.
- **Senior Management:** Review high-level workforce indicators to inform strategic workforce planning.
- **Data Analysts:** Examine the analytical methods, statistical tests, and supporting evidence.

### Business Requirements

The project is structured around five key business requirements:

**BR1 — Department Attrition**

Determine which departments have the highest employee attrition rates, helping HR teams identify where employee departures are most prevalent.

**BR2 — Job Role Attrition**

Compare attrition metrics across job roles to highlight those that may warrant further investigation or targeted retention support.

**BR3 — Overtime and Attrition**

Assess whether overtime is associated with attrition by comparing employees who work overtime with those who do not. Statistical hypothesis testing will be used to evaluate whether an association exists.

**BR4 — Job Satisfaction and Attrition**

Analyse how attrition rates vary across job satisfaction levels and use statistical hypothesis testing to assess whether an association exists.

**BR5 — Employee Tenure and Attrition**

Assess attrition by length of service to determine whether departure rates differ across tenure groups.

### Business Success Criteria

The project will be considered successful if it fulfils the following criteria:

1. Provides evidence-based answers to all five business requirements using the available dataset.
2. Accurately calculates and presents attrition rates.
3. Applies appropriate statistical methods to analyse the selected relationships.
4. Presents the findings in intuitive, interactive, and accessible Tableau dashboards.
5. Offers evidence-informed recommendations while clearly acknowledging the dataset's synthetic nature and limitations.
6. Demonstrates a commitment to handling and interpreting employee-related data responsibly.

The findings are intended to support further research and inform decision-making, rather than dictate HR actions or explain the reasons for employee departures.

## Hypothesis and how to validate?

This research explores two core hypotheses regarding employee attrition: the relationship between overtime and attrition, and the connection between job satisfaction and attrition.

Both hypotheses were evaluated using the **Chi-square test of independence**, in Python. This statistical test determines whether a measurable connection exists between the two categorical variables.

A significance level of **0.05 (5%)** was used for both assessments. A p-value dropping below 0.05 signals a statistically significant association, providing enough evidence to reject the null hypothesis.

### Hypothesis 1 — Overtime and Employee Attrition

**Null hypothesis (H0):** There is no statistically significant association between overtime status and employee attrition.

**Alternative hypothesis (H1):** A statistically significant association exists between overtime status and employee attrition.

**Validation Method:**

- Compare attrition rates between overtime workers and employees who do not.
- Construct a contingency table illustrating overtime status against attrition.
- Execute the Chi-square test of independence.
- Make a comparison between the resulting p-value and the significance level of 0.05.

**Results:**

- Employees working overtime: **30.53% attrition rate**.
- Employees not working overtime: **10.44% attrition rate**.
- Chi-square statistic: **87.5643**.
- p-value: **less than 0.000001**.

**Conclusion:**

Because the p-value is below 0.05, that means the null hypothesis is rejected. This indicating a statistically significant association between overtime status and employee attrition.

Staff engaged overtime work exhibited rate of company departure within this dataset, nonetheless this does not prove that overtime work forces employees to leave the company.

### Hypothesis 2 — Job Satisfaction and Employee Attrition

**Null hypothesis (H0):** There is no statistically significant association between job satisfaction level and employee attrition.

**Alternative hypothesis (H1):** There is a statistically significant association between job satisfaction level and employee attrition.

**Validation Method:**

- Compute turnover rates across the four levels of job satisfaction.
- Create a contingency table maping job satisfaction against attrition.
- Conduct the Chi-square test of independence.
- Assess the resulting p-value against the significance level of 0.05.

**Results:**

| Job Satisfaction Level | Attrition Rate |
|---|---:|
| 1 — Low | 22.84% |
| 2 — Medium | 16.43% |
| 3 — High | 16.52% |
| 4 — Very High | 11.33% |

- Chi-square statistic: **17.5051**.
- p-value: **0.000556**.

**Conclusion:**

The p-value for this hypothesis is also below 0.05, leading to the null hypothesis being rejected. The data delivers statistically significant proof of a correlation between job satisfaction and employee attrition.

Employees who were not satisfied in their job had the highest attrition rate, whereas those indicating very high job satisfaction recorded the lowest. Despite these findings, there in no evidence of what causes attrition rates. 

### Statistical Limitations

Although both evaluations uncovered statistically significant associations, the results warrant careful interpretation.

The dataset used is synthetic and does not mirror a real company. Furthermore, the Chi-square tests reveals associations but not cause-and-effect relationships. Other variables may also impact workforce attrition.

Consequently, these findings should be viewed as demonstrations of how statistical analysis can guide Human Resource investigations rather than conclusive evidence concerning real-world employee behaviour.

## Project Plan

### Project Management Approach

The project followed a structured data analytics workflow, progressing from defining business requirements through data preparation, conducting analysis, hypotheses testing and reporting the findings.

A Projects Kanban board in GitHub was used for task organisation, progress tracking, as well as monitor user stories throughout development.

The project was segmented into clear manageable stages to keep the analysis focused on the five business requirements.

### Project Development Stages

**1. Planning and Business Understanding**

The initial phase of the project involved defining the business problem, identifying the intended audience and establishing five concrete business criterias.

User stories were established to structure the requirements into manageable tasks. GitHub projects was used to track progress.

**2. Data Collection and Understanding**

The IBM HR Analytics Employee Attrition & Performance dataset was downloaded from Kaggle.

The dataset was evaluated beforehand to understand its underlying structure, active variables and inherent.

**3. Data Preparation and Processing**

Leveraging Python and Pandas in Jupyter Notebook, the dataset was inspected, cleaned and preparef for analysis. 

New variables, such as `Attrition_Flag`, `Age_Group` and `Tenure_Group`, were created to assist with the analysis. 

The refined dataset was saved into a dedicated version-controlled directory to maintain a consistent data source for later analysis and visualisation.

**4. Exploratory Data Analysis (EDA)**

Exploratory data analysis investigated turnover trends across organisational departments, job roles, overtime status, job satisfaction and employee service length.

Attrition rates were calculated and compared across different workforce segments. 

**5. Statistical Hypothesis Testing**

Two Chi-square tests of independence were employed to examine associations between employee attrition and factors like overtime and job satisfaction.

Outcomes were assessed using a significance level of 0.05, while keeping in mind that statistical correlation does not imply causation.

**6. Dashboard Development and Implementation**

Two interactive dashboards were created in Tableau:

- **Workforce Overview:** Displays macro workforce statistics alongside attrition rates categorised by department and job role.
- **Attrition Drivers:** Examines departure dynamics associated with overtime hours, job satisfaction levels and career tenure.

Navigation buttons were implemented to make it easier for users to move between the dashboards.

The finished Tableau workbook was stored inside the project repository and deployed to Tableau Public to ensure accessibility for stakeholders.

**7. Testing and Evaluation**

The project was evaluated against the initial business requirements. Including a review of the data preparation process, the varification of calculations and statistical outputs, as well as ensuring that the dashboards convey insights effectively. 

Dashboard navigation, chart titles and the presentation of key insights were also factored in.

**8. Documentation and Version Control**

Git and GitHub were used to track changes throughout the project.

The README documents thoroughly outlined the dataset, business requirements, methodology, tested hypotheses, dashboard architectures, findings, constrainst and development process.

Meaningful commits were used to perserve a transparent, auditable history of progress.

### Data Management

The project utilised separate folders for raw data, prcessed data, Jupyter notebooks and Tableau exports.

The cleaned dataset resides in a versioned folder, allowing for a consistent dataset while preserving original information. 

This framework promotes reproducibility, organisation and future enhancements.

### Maintenance and Future Updates

For future enhancements, though the current project is based on a fixed synthetic dataset, it could be updated with new data, if it becomes available. 

Future upkeep would entail validating the data structure, rerunning of data prep and analysis notebooks, verifying numerical results, refreshing the Tableau visualisations and refreshing the project documentation.

Potential future expansions may include Machine Learning and SQL anlyses. 

### Methodology Rationale

The chosen methodology underscores a structured workflow that effectively connects business questions, with data preparation, statitical examination and visual dashboard presentation.

The utilisation of Python and pandas were deemed appropriate for data handling and analysing, while Tableau was selected to translate the findings into intuitive visual formats for both technical and non-technical users.

Using GitHub Projects alongside version control further supported task organisation, documentation and project traceability through development.

## The rationale to map the business requirements to the Data Visualisations

The Tableau dashboards were engineered to transform the five business requirements into transparent, intuative visualisations.

Two distinct dashboards were created to differentiate between an overall workforce summary from a more detailed expolaration of factors behind employee attrition.

### Business Requirements and Visualisation Mapping

| Business Requirement | Visualisation | Dashboard | Rationale |
|---|---|---|---|
| BR1 — Department Attrition | Department attrition rate bar chart | Workforce Overview | Allows users to compare attrition percentages across departments and identify those with higher rates. |
| BR2 — Job Role Attrition | Job role attrition rate bar chart | Workforce Overview | Highlights differences between job roles and makes it easier to identify roles with relatively high attrition. |
| BR3 — Overtime and Attrition | Overtime attrition rate bar chart | Attrition Drivers | Compares employees who work overtime with those who do not, making the difference in attrition rates easy to understand. |
| BR4 — Job Satisfaction and Attrition | Job satisfaction attrition rate bar chart | Attrition Drivers | Shows how attrition rates vary across the four satisfaction levels. |
| BR5 — Employee Tenure and Attrition | Tenure group attrition rate bar chart | Attrition Drivers | Compares attrition rates across length-of-service groups to identify differences between newer and longer-serving employees. |

### Visualisation Design Decisions

**Bar charts** were chosen due to them allowing users to compare turnover rates across categories without needing specialised statistical knowledge.

The **Workforce Overview** dashboard incorporates three key performance indicators (KPIs):

- **Total Employees:** 1,470
- **Employees Who Left:** 237
- **Overall Attrition Rate:** 16.12%

These KPIs provide immediate context before delving into departmental and job role comparisons.

The **Attrition Drivers** dashboard centers on overtime, job satisfaction and tenure, giving stakeholders the ability to examine patterns that may require follow-up analysis.

### Dashboard Navigation and User Experience

Navigation buttons allow users to seamlessly move between the two dashboards without being forced into returning to the Tableau workbook menu.

The dashboard layout utilises descriptive titles, percentage-based metrics and supports explanations to further enhance comprehension for HR managers, senior managers and data analysts.

The graphics focus on attrition **rates rather than departure counts alone**, facilitating fairer comparisons among groups of different sizes.

### Communicating Findings Responsibly

The dashboards differentiate observed patterns from established causes.

For example, while a higher attrition rate among employees working overtime indicates an association in this dataset it does not imply that overtime causes employees to depart.

Turthermore, the dashboards clearly states that the records are syntethic to prevent users from believing that the findings come from real-world organisation.

## Analysis techniques used

This project relied on a mix of data preparation, exploratory data analysis (EDA), statistical hypothesis testing and data visualisation to uncover why employees leave.

The analysis was executed in two Jupyter notebooks using Python, with results communicated in interactive Tableau dashboards.

### 1. Data Preparation and ETL

The Journey began by preparing the dataset for analysis with the help pf Python and Pandas.

The Extract, Transform and Load (ETL) process looked like this:

- **Extract:** Pulling in the original employee dataset from a CSV file.
- **Transform:** Inspecting the dataset, checking data health and building helpful new variables to power the analysis.
- **Load:** Exporting the polished dataset into a versioned CSV file sp everything stayed consistent moving forward.

The `Attrition_Flag`, `Age_Group` and `Tenure_Group` variables were built to make comparisons and calculations much easier.

Every step of this process was logged inside `01_Data_Preparation_ETL.ipynb`.

### 2. Exploratory Data Analysis (EDA)

Exploratory data analysis was conducted to unearth patterns in employee departures.

The analysis examined:

- Overall employee attrition.
- Attrition broken down by department.
- Attrition rates by job role.
- Attrition rates by overtime status.
- Attrition rates by job satisfaction.
- Attrition rates by career tenure.

Pandas was used to make comparisons between groups and to determine the exact percentage of employees who left the company within each category.

The baseline turnover rate was calculated using this formula:

**Attrition Rate (%) = (Number of Employees Who Left / Total Number of Employees) × 100**

For instance, 237 of the 1,470 employees in the dataset had departed, giving an overall attrition rate of approximately **16.12%**.

Relying on percentages rather than departure counts alone made it easier to compare temans of vastly different sizes.

The exploratory analysis was logged inside `02_Exploratory_Data_Analysis.ipynb`.

### 3. Statistical Hypothesis Testing

The Chi-square test of independence was utilised to assess relationships between employee attrition and two categorical variables:

- Overtime status.
- Job satisfaction level.

The tests were evaluated using a standard significance threshold of 0.05.

Both tests returned p-values below 0.05, giving statistically significant evidence of associations existing between these factors.

Even so, the tests point to relationships rather than causation, meaning the results must be interpreted within the contraints of the synthetic dataset.

### 4. Data Visualisation

Tableau was utilised to craft two interactive dashboards.

The **Workforce Overview** dashboard highlights key workforce indicators and compares turnover rates across departments and job roles.

The **Attrition Drivers** dashboard focuses on attrition patterns by overtime status, job satisfaction and employee tenure.

Bar charts simplified the comparisons of the various categories and KPI indicators provided an instant snapshot of the workforce.

Navigation buttons were built in so users can go easily go from one dashboard to the other.

### 5. Methodological Limitations and Alternative Approaches

A few limitations influenced how this analysis was put together:

- **Synthetic data:** Because the data is simulated, generalisability of the data is restricted without further evidence.
- **No causal evidence:** Statistical associations show what worker left but not why.
- **Limited time information:** The dataset does not support calculation of an annual attrition rate.
- **Group-level comparisons:** Differences between groups may be influenced by outside variables that were not included in the dataset.

Logistic regression as well as other more advanced methods could be applied in the future to examine several variables together.However, for this project it was not needed.

Ultimately, The chosen techniques hit the sweet spot for uncovering initial turnover trends and presenting understandable findings to HR stakeholders.

### 6. Use of Generative AI

Generative AI tools played a supportive role throughout the development of this project. This includes brainstorming, giving explanations of of analytical concepts, assissting with code creation as well as improving documentation. 

ChatGPT was utilised as a trusty coding and learning assistant, while gemini was used to explain hard-to-understand concepts. 

All AI-generated suggestions were rigorously reviewed and tailored to meet the project's precise requirements. AI ws merely used as support for this project ans the project is my one work.

## Ethical considerations

Ethical considerations are important in HR analytics because employee-related information can be sensitive, and analytical findings may influence decisions affecting people.

Although this project uses a synthetic dataset, it is still important to handle and interpret the data responsibly

### Data Privacy and Protection

The IBM HR Analytics Employee Attrition & Performance dataset contains simulated employee records and than personal information collected from real workers.

As stated this project did not collect real employee records or access confidential HR systems.

If this analysis were used in a real organisation, personal data would need to be handled in line with relevant data protection laes, including the UK General Data Protection Regulation (UK GDPR) as well as the Data Protection Act 2018.

Key principles include:

- **Lawfulness, fairness and transparency:** Personal data should be processed for a lawful purpose, and employees should be clearly informed about how their data is used. 
- **Purpose limitation:** Employee information should only be used for specified and legitimate purposes.
- **Data minimisation:** Only the information needed for the analysis should be collected and processed.
- **Accuracy:** Employee records and analytical outputs should be checked for errors.
- **Storage limitation:** Personal data should only be kept for as long as recessary then deleted.
- **Integrity and confidentiality:** Suitable security measures should protect employee information against unauthorised access or loss.

These principles are described in guidance from the Information Commissioner's Office (ICO, n.d.).

### Data Governance

The project follows a structured data management approach by separating the raw data from the cleaned data which is kept in a versioned folder. 

Jupyter notebooks document the data preparation and analysis, while Git and GitHub record the changes.

For a real HR dataset, more governance measures would be needed such as, access controls, secure storage, defined retention periods and appropriate procedures for checking data quality.

Publishing individual-level employee data in a public repository would require careful assessment and publishing data that identifies individuals or contains confidential information would generally be deemed inappropriate.

### Bias and Fairness

HR analytics can lead to misleading conclusions if differences between employee groups are viewed without considering their wider context.

For example, a higher attrition rate in a department or job role does not necessarily mean that management practices caused employees to leave.

Other factors such as workforce composition, job responsibilities or working conditions could influence as well

To reduce the risk of misleading interpretation, this project:

- Compares attrition rates rather than relying only on departure counts.
- Clearly states the dataset as synthetic.
- Distinguishes statistical associations from causal relationships.
- Avoids making judgements about individual workers.
- Presents findings as topic for further investigation not as definitive explanations.

### Legal and Social Implications

In a real organisation, workforce analytics could influence recruitment, retention strategies, performance management and oppurtunities at work.

Using incomplete or biased information could lead to unfair treatment or discrimination.

Organisations should therefore consider relevant employment and equality legislation, including the Equality Act 2010, when using workforce data to inform decisions.

Statistical findings should not be used as the sole basis for decisions about individual employees. Human oversight, appropriate consultation and further investigation would also be needed.

### Responsible Communication of Results

The Tableau dashboards show group-level findings rather than profiles of individual employees.

The project explains the limitations of the dataset and avoids claiming that overtime, job satisfaction or tenure directly causes employee to leave.

These steps help stakeholders interpret the findings carefully and avoid placing too much confidence in the results. 

Overall, the project demonstrates how HR analytics can support evidence-informed discussions while recognising the importance of privacy, fairness, transparency and responsible decision-making.

## Dashboard Design

The project includes two interactive Tableau dashboards designed to communicate employee attrition findings to HR managers, department managers, senior management and data analysts.

The dashboards separate high-level workforce information from a more detailed analysis of attrition patterns. This allows users to begin with an overview before exploring specific factors.

### Dashboard 1 — Workforce Overview

The **Workforce Overview** dashboard presents a summary of the workforce and highlights differences in employee attrition across departments and job roles.

It includes three key performance indicators (KPIs):

- **Total Employees:** 1,470
- **Employees Who Left:** 237
- **Overall Attrition Rate:** 16.12%

It also includes:

- **Department Attrition Rate:** A chart comparing attrition percentages across departments.
- **Job Role Attrition Rate:** A chart comparing attrition percentages across job roles.

These visualisations help stakeholders identify workforce groups with relatively high attrition rates and decide where further investigation may be useful.

### Dashboard 2 — Attrition Drivers

The **Attrition Drivers** dashboard examines three factors associated with employee attrition:

- **Overtime:** Compares attrition rates between employees who work overtime and those who do not.
- **Job Satisfaction:** Compares attrition rates across four satisfaction levels.
- **Employee Tenure:** Shows differences in attrition rates across length-of-service groups.

These visualisations support a more detailed understanding of workforce patterns and provide context for the statistical analysis completed in Python.

### Navigation and User Experience

Navigation buttons were added to both dashboards to improve usability.

- **Workforce Overview:** Includes a button labelled "View Attrition Drivers →" that opens the second dashboard.
- **Attrition Drivers:** Includes a button labelled "← Workforce Overview" that returns users to the first dashboard.

The navigation buttons use a navy background and white text to make them visually distinguishable from the dashboard content.

The two-dashboard structure allows users to explore information progressively rather than displaying every visualisation on a single page.

### Accessibility and Communication

The dashboards were designed to communicate findings to both technical and non-technical audiences.

Design considerations include:

- Descriptive dashboard and chart titles.
- Clearly displayed attrition percentages.
- KPI indicators that summarise the workforce.
- Separate dashboard pages to reduce information overload.
- Visible navigation buttons.
- Supporting explanations that help users interpret the results.
- Clear identification of the dataset as synthetic.

The dashboards present statistical findings in an accessible format while the Jupyter notebooks provide the more detailed analytical methods for technical users.

### Design Limitations

The dashboards provide descriptive comparisons rather than predictions of future employee departures.

Although the visualisations highlight differences between employee groups, they cannot establish why employees leave.

The findings are based on synthetic data and should not be interpreted as evidence about an actual organisation.

## Testing and Validation

Testing and validation are important to ensure that the analysis is accurate, the findings are consistent and the dashboards meet the project's business requirements.

The project uses data quality checks, statistical validation and dashboard review to assess the reliability of its outputs.

### 1. Data Quality and Preparation

The data preparation process was documented in `01_Data_Preparation_ETL.ipynb`.

The following areas were considered during data preparation:

- Dataset structure, column names and data types.
- Missing values and duplicate records.
- Consistency of categorical variables.
- Creation of `Attrition_Flag`, `Age_Group` and `Tenure_Group`.
- Exporting the cleaned dataset to a versioned CSV file.

The cleaned dataset contains the information required for the subsequent analysis and dashboard development.

### 2. Validation of Attrition Calculations

Attrition rates were calculated using the number of employees who left divided by the total number of employees in each group.

The overall dataset contains:

- Total employees: **1,470**
- Employees who left: **237**
- Employees who stayed: **1,233**
- Overall attrition rate: **16.12%**

The overall attrition rate can be verified using:

**(237 / 1,470) × 100 = 16.12%**

Group-level attrition rates were used to compare departments, job roles, overtime status, job satisfaction and tenure.

### 3. Statistical Validation

Two Chi-square tests of independence were conducted in `02_Exploratory_Data_Analysis.ipynb`.

| Hypothesis | Chi-square Statistic | p-value | Result |
|---|---:|---:|---|
| Overtime and attrition | 87.5643 | < 0.000001 | Statistically significant association |
| Job satisfaction and attrition | 17.5051 | 0.000556 | Statistically significant association |

Both p-values were below the significance level of 0.05, providing evidence to reject the respective null hypotheses.

These results demonstrate statistical associations, not causal relationships.

### 4. Dashboard Testing

The Tableau dashboards were reviewed against the intended business requirements.

The review focused on:

- Whether the **Workforce Overview** dashboard presents the correct workforce KPIs.
- Whether the department and job role charts communicate attrition rates.
- Whether the **Attrition Drivers** dashboard presents overtime, job satisfaction and tenure comparisons.
- Whether chart titles, labels and percentages are understandable.
- Whether navigation buttons allow users to move between the two dashboards.
- Whether the synthetic nature of the dataset is communicated clearly.

The dashboards were designed to support both high-level business review and more detailed analysis.

### 5. Business Requirements Validation

| Business Requirement | Evidence |
|---|---|
| BR1 — Department Attrition | Department attrition analysis and Workforce Overview dashboard |
| BR2 — Job Role Attrition | Job role attrition analysis and Workforce Overview dashboard |
| BR3 — Overtime and Attrition | Overtime comparison, Chi-square test and Attrition Drivers dashboard |
| BR4 — Job Satisfaction and Attrition | Satisfaction comparison, Chi-square test and Attrition Drivers dashboard |
| BR5 — Employee Tenure and Attrition | Tenure group comparison and Attrition Drivers dashboard |

All five business requirements are addressed by the completed analysis and dashboard content.

### 6. Limitations of Validation

The dataset is synthetic, so the results cannot be independently verified against real organisational records.

Statistical significance does not establish causation, and the analysis does not account for every possible factor influencing employee departures.

The project therefore demonstrates a reproducible analytical approach rather than providing validated predictions or conclusions about a real workforce.

## Findings and Recommendations

This section summarises the main findings from the employee attrition analysis and outlines recommendations that HR stakeholders could consider when investigating employee retention.

### Key Findings

**1. Overall Employee Attrition**

Of the 1,470 employees in the dataset, 237 had left the organisation, representing an overall attrition rate of **16.12%**.

This figure describes the proportion of employees recorded as having left in the dataset. It should not be interpreted as an annual attrition rate.

**2. Department Attrition**

Attrition rates varied across departments:

| Department | Attrition Rate |
|---|---:|
| Sales | 20.63% |
| Human Resources | 19.05% |
| Research & Development | 13.84% |

Sales had the highest attrition rate, suggesting that this department would be a useful starting point for further investigation in the project's business scenario.

**3. Job Role Attrition**

The highest attrition rates were observed in the following roles:

| Job Role | Attrition Rate |
|---|---:|
| Sales Representative | 39.76% |
| Laboratory Technician | 23.94% |
| Human Resources | 23.08% |
| Sales Executive | 17.48% |
| Research Scientist | 16.10% |

Sales Representatives had the highest attrition rate among the job roles analysed.

However, the size of each employee group should also be considered when interpreting these percentages.

**4. Overtime and Attrition**

Employees who worked overtime had an attrition rate of **30.53%**, compared with **10.44%** among employees who did not work overtime.

The Chi-square test identified a statistically significant association between overtime status and attrition (p < 0.000001).

This finding suggests that overtime patterns may warrant further investigation, although the analysis does not demonstrate that overtime causes employees to leave.

**5. Job Satisfaction and Attrition**

Employees reporting low job satisfaction had an attrition rate of **22.84%**, compared with **11.33%** among employees reporting very high job satisfaction.

The Chi-square test found a statistically significant association between job satisfaction and attrition (p = 0.000556).

The findings suggest that job satisfaction could be an important area for further HR investigation.

**6. Employee Tenure and Attrition**

Attrition rates differed across tenure groups:

| Years at Company | Attrition Rate |
|---|---:|
| 0–2 years | 29.82% |
| 3–5 years | 13.82% |
| 6–10 years | 12.28% |
| 11–20 years | 6.67% |
| 21+ years | 12.12% |

Employees with 0–2 years of service had the highest attrition rate, suggesting that early employment experiences may be worth examining.

### Recommendations for HR Stakeholders

Based on these findings, the following actions could be considered in a real organisation:

1. **Investigate departments and job roles with higher attrition rates.** HR teams could review employee feedback, working conditions and retention patterns, particularly in Sales and Sales Representative roles.

2. **Review overtime practices.** Managers could examine workload distribution, overtime expectations and employee feedback to understand whether working arrangements contribute to retention concerns.

3. **Monitor employee satisfaction.** Regular, confidential employee surveys and feedback discussions could help identify workplace concerns requiring attention.

4. **Strengthen support for newer employees.** Organisations could review onboarding, training, mentoring and early-career support, particularly during the first two years of employment.

5. **Continue monitoring workforce trends.** HR teams could use regularly updated dashboards and additional data to evaluate whether retention initiatives are associated with improvements over time.

### Overall Conclusion

The analysis identified notable differences in attrition rates across departments, job roles, overtime status, job satisfaction and employee tenure.

The statistical tests also identified significant associations between attrition and both overtime status and job satisfaction.

These findings demonstrate how data analytics can support evidence-informed HR discussions. However, because the dataset is synthetic and the analysis is observational, the recommendations are illustrative and would require validation using real organisational data before implementation.

## Unfixed Bugs

* Please list any unfixed bugs and explain why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.

## Development Roadmap

* What challenges did you face, and what strategies were used to overcome these challenges?
* What new skills or tools do you plan to learn next based on your project experience? 

## Deployment (optional)

* If this is a Unit 3 Streamlit, Power BI or Tableau Public project, then you can include a link here and explain how you hosted the dashboard.

### Heroku (optional)

* This section is necessary only if you are deploying a Streamlit app to Heroku as part of your submission for units 2 and 3. 
* The App live link is: https://YOUR_APP_NAME.herokuapp.com/ 
* Set the `.python-version` Python version to a [Heroku-22](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version.
* The project was deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. From the Deploy tab, select GitHub as the deployment method.
3. Select your repository name and click Search. Once it is found, click Connect.
4. Select the branch you want to deploy, then click Deploy Branch.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click the button Open App at the top of the page to access your App.
6. If the slug size is too large, then add large files not required for the app to the `.slugignore` file.

## Main Data Analysis Libraries

* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.

## Credits

* In this section, you need to reference where you got your content, media and extra help from. It is common practice to use code from other repositories and tutorials; however, it is important to be very specific about these sources to avoid plagiarism. 
* You can break the credits section into Content and Media, depending on what you include in your project. 

### Content 

- The text for the Home page was taken from the Wikipedia Article A
- Instructions on how to implement form validation were taken from a [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)

### Media

- The photos used on the home and sign-up page are from This Open-Source site
- The images used for the gallery page were taken from this other open-source site



## Acknowledgements (optional)

* Thank the people who supported this project.