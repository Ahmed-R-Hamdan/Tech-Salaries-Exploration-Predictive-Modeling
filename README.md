# Tech-Salaries-Exploration-Predictive-Modeling

## The Data Talent Race: Insights to Attract & Retain Top Professionals

The rapid expansion of the tech industry has intensified competition for top data professionals, making it more challenging for companies to attract and retain the right talent. Roles such as Data Scientists, Machine Learning Engineers, and AI Specialists are pivotal in driving innovation and fueling data-driven decision-making. Yet, evolving skill demands, shifting work preferences, and rising compensation expectations add complexity to hiring strategies.

This report analyzes global salary data to uncover key compensation trends based on job roles, experience levels, work models, and company sizes. Armed with these insights, businesses can refine their hiring strategies, optimize salary structures, and position themselves as leading employers in the competitive data job market.

Developing a predictive model to estimate an employee’s salary (in USD) using current features which are are strongest predictors of salary?
Expanding the model by incorporating additional features to improve our model.

### 📌 Key Insights at a Glance

📊 **Survey Insights**
- 57,194 tech professionals surveyed
- 93.6% work for UK-based companies, with 93.5% of employees residing in the UK

📈 **Tech Job Market Boom**
- 448% increase in tech job openings from 2023 to 2024
- Data Scientists (19%) and Data Analysts (17.4%) dominate the job market

💰 **Salary Growth & Compensation Trends**
- Average annual salary jumped by 34.3% in 2022 to 134K, continuing its rise in 2023 & 2024.
- 7 of the top 10 highest-paying roles in 2024 belong to Machine Learning, with 5 of them in managerial positions.
- Machine Learning roles lead as the highest-paying category, averaging 192K per year
- 2024 salary distribution is more balanced, with a smaller gap between the highest and lowest-paying regions

🏢 **Impact of Company Size on Salaries**
- Larger companies consistently offer higher, more stable salaries
- Moving from entry-level in a small company to mid-level in a medium-sized company can double salary earnings

👨‍💻 **Employment Type & Work Model Preferences**
- Full-time roles dominate 99.6% of job opportunities and offer the highest salaries
- Onsite jobs pay slightly higher than remote roles, but the gap is minimal and offset by work flexibility

🌍 **Regional Salary Trends**
- The UK is the only country consistently appearing in the top 10 salary-paying locations across 5 years
- 2023 saw a record-breaking salary peak—for the first time, salaries crossed 300K.
- Whereas in previous years, no location exceeded 200K

## Model Performance

Using curretn data only best model achieve score 0.30 and MSE 0.15 which is low. Due to the lack of continuous numerical features, the dataset primarily consists of discrete values after converting categorical variables into numerical form. This limitation affects the model's ability to capture underlying patterns, leading to a low performance score.

We can enhance our model using below techniques 

- Feature Engineering

    Creating new feature `vacancy_param` combine job details

    `vacancy_param` = `experience_level` + `employment_type` + `company_size`

- Target Encoding

    Replacing categorical values with the mean of the target variable for each category, this is useful when a categorical feature has many unique values

    We will use this encoding with job_title and company_location instead of lebel encoding

  The model's performance improved from **R² = 0.30 to 0.38** due to target encoding and feature engineering, These optimizations enhanced the model's ability to capture complex relationships, resulting in a **7%** increase in R² score.



## 💾 The data

The data comes from a survey hosted by an HR consultancy, available in `'salaries.csv'`.

#### Each row represents a single employee's salary record for a given year:
- **`work_year`** - The year the salary was paid.  
- **`experience_level`** - Employee experience level:  
  - **`EN`**: Entry-level / Junior  
  - **`MI`**: Mid-level / Intermediate  
  - **`SE`**: Senior / Expert  
  - **`EX`**: Executive / Director  
- **`employment_type`** - Employment type:  
  - **`PT`**: Part-time  
  - **`FT`**: Full-time  
  - **`CT`**: Contract  
  - **`FL`**: Freelance  
- **`job_title`** - The job title during the year.  
- **`salary`** - Gross salary paid (in local currency).  
- **`salary_currency`** - Salary currency (ISO 4217 code).  
- **`salary_in_usd`** - Salary converted to USD using average yearly FX rate.  
- **`employee_residence`** - Employee's primary country of residence (ISO 3166 code).  
- **`remote_ratio`** - Percentage of remote work:  
  - **`0`**: No remote work (<20%)  
  - **`50`**: Hybrid (50%)  
  - **`100`**: Fully remote (>80%)  
- **`company_location`** - Employer's main office location (ISO 3166 code).  
- **`company_size`** - Company size:  
  - **`S`**: Small (<50 employees)  
  - **`M`**: Medium (50–250 employees)  
  - **`L`**: Large (>250 employees)  
