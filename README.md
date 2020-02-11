# Employee-Retention

## Description
A Supervised Learning classifier to anticipate which employees are likely to leave based on features like job satisfaction, salary, performance, etc.

## Dataset
The dataset has **14249** observations for past/present employees, spanning over 12 different departments. Each observation includes the employee's current employment status.

### Target variable
  * `status` - Current employment status (Employed/Left)

### Features
  * `department` - Department employees belong(ed) to
  * `salary` - Salary level relative to rest of their department
  * `tenure` - Number of years at the company
  * `recently_promoted` - If the employee has been promoted within the last 3 years
  * `n_projects` - Number of projects an employee is/was involved in
  * ` avg_monthly_hours` - average number of hours worked per month
  * `satisfaction` - Score for employee's satisfaction with the company (higher the better)
  * `last_evaluation` - Score for the most recent evaluation of employee (higher the better)
  * `filed_complaint` - If the employee has filed a formal complaint within the last 3 years
