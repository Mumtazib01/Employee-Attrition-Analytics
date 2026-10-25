# Employee Attrition Analytics

**Employee Attrition Analytics** is a data analytics project that utilises the IBM HR Analytics Employee Attrition & Performance dataset to investigate patterns in employee departures.

This project aims to support Human Resources (HR) decision-making by examining employee attrition across various factors, including department, job role, overtime status, job satisfaction and length of service.

The analysis was conducted in Jupyter Notebook using Python and Pandas to perform data preparation, exploratory data analysis (EDA) and statistical hypothesis testing. The findings are presented through two interactive Tableau dashboards: **Workforce Overview** and **Attrition Drivers**.

The dashboards enable users to examine key workforce metrics, compare attrition rates and navigate between an overall summary and a more detailed analysis.

The dataset contains 1,470 synthetic employee records. Therefore, rather than representing employee behaviour in an actual organisation, the findings demonstrate analytical methods.

The associations observed in the analysis should not be interpreted as evidence of causation.

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

## Dataset Content

This project used **IBM HR Analytics Employee Attrition & Performance** dataset, which is publicly available on [Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset).

The dataset encompasses **1,470 employee records across 35 original columns**, detailing employee demographics, job specifications, workplace environments and employee attrition.

The dataset is entirely synthetic, which means that it consists of simulated employee data rather than genuine employee records. This ensures that HR analytics data can be demonstrated safely without exposing real workers' personal information.

### Dataset Structure

Each row corresponds to one employee, and the `Attrition` column indicates whether that employee has left the organisation (`Yes`) or stayed (`No`).

The primary variables investigated in this analysis are as followed:

| Variable | Description |
|---|---|
| `Attrition` | Whether an employee left the organisation |
| `Department` | Department in which the employee works |
| `JobRole` | The specific job title of the employee |
| `OverTime` | Whether the employee engages in overtime work |
| `JobSatisfaction` | Job satisfaction rating from 1 (Low) to 4 (Very High) |
| `YearsAtCompany` | Number of years the worker has been at the company |
| `Age` | Employee's age in years |

### Data Preparation

The intial data cleaning and preprocessing of the original dataset was coducted using Python and Pandas in the `01_Data_Preparation_ETL.ipynb` notebook.

To support the analysis, additional variables were introduced:

- `Attrition_Flag`: Converts attrition into a numerical value, where 1 represents an employee who left and 0 denotes an employee who remained.
- `Age_Group`: Groups employees into various age brackets.
- `Tenure_Group`: Puts employees in groups according to their length of service.

The finalised and cleaned dataset was saved and exported as a CSV file and stored within a version-controlled folder to guarantee reproducibility and further investigation.

### Dataset Limitations

While this dataset provides useful insights into workforce patterns, it is not free of limitations:

- The records are synthetic and lack real-world employee records.
- It is resctricted to a single dataset rather than multiple organisations.
- It does not establish the reasons for employee departures.
- The dataset lacks sufficient time-based information needed to compute a precise annual employee attrition rate.

These constraints are actively factored when it comes to the interpretation of the findings and the formulation of strategic HR recommendations.

## Business Requirements

* Describe your business requirements

## Hypothesis and how to validate?

* List here your project hypothesis(es) and how you envision validating it (them) 

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