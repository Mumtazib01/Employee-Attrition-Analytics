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

* Outline the high-level steps taken for the analysis.
* How was the data managed throughout the collection, processing, analysis and interpretation steps?
* Why did you choose the research methodologies you used?

## The rationale to map the business requirements to the Data Visualisations

* List your business requirements and a rationale for mapping them to the Data Visualisations

## Analysis techniques used

* List the data analysis methods used and explain limitations or alternative approaches.
* How did you structure the data analysis techniques? Justify your response.
* Did the data limit you, and did you use an alternative approach to meet these challenges?
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?

## Ethical considerations (optional)

* Feel free to delete this section if this is a data visualisation only (unit 1 or 2) project submission.
* Were there any data privacy, bias or fairness issues with the data?
* How did you overcome any legal or societal issues?

## Dashboard Design (optional)

* Feel free to delete this section if this is a data visualisation only (unit 1 or 2) project submission.
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.
* Later, during project development, you may revisit your dashboard plan to update a feature (for example, at the beginning of the project, you were confident you would use a given plot to display an insight, but later you used another plot type).
* How were data insights communicated to technical and non-technical audiences?
* Explain how the dashboard was designed to communicate complex data insights to different audiences. 

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