![image](https://github.com/user-attachments/assets/ab2e8e97-d645-4552-a4f6-74bd0445ce01)# Wunmi's portfolio

## Table of Content
- [30days Excel Challenge](#30days-excel-challenge)
- [Links to the Datasets](#links-to-the-datasets)
- [Tool](#tool)
- [Questions and Output](#questions-and-output)

## 30days Excel Challenge
---

This challenge was organized by Techavilly to help upcoming data Analyst in their Data analytics journey. We worked with different datasets which will be shared below with their respective questions and output.

### Link to the Datasets
- [Data](https://1drv.ms/x/s!Aum1pK9wiIgycuwfzy4fWPOIxZs?e=zZtmbD)

### Tool
Microsoft 2016 [Download here](https://support.microsoft.com/en-us/office/download-and-install-or-reinstall-office-2019-office-2016-or-office-2013-7c695b06-6d1a-4917-809c-98ce43f86479)

### Questions and Queries

**Day 1 Question**
![image](https://github.com/user-attachments/assets/8586555c-a595-438e-af8a-fc5ec571a4e1)

#### Output
![image](https://github.com/user-attachments/assets/23f0016a-71d6-44b3-b8c5-156c35facfa8)

**Day 2 Question**
![image](https://github.com/user-attachments/assets/e6361f0a-e4fb-4a25-9024-ad7de79ad336)

#### Output
![image](https://github.com/user-attachments/assets/dee49b53-4de4-433c-9865-8ad0a008c147)

**Day 3 Question**
![image](https://github.com/user-attachments/assets/c57fc606-6905-438f-bc2e-701f410c505b)

#### Output
![image](https://github.com/user-attachments/assets/ea8c44b2-cfcf-4138-bb13-c1fb0b9a7e2e)

**Day 4 Question**

**Day 5 Question**

**Day 6 Question**

**Day 8 Question**

**Day 9 Question**
**Day 10 Question**

**Day 11 Question**

**Day 12 Question**

**Day 13 Question**: As we conclude the analysis for The Briggs Company, they got some reviews on their website regarding their new product. Please use the Bonus table to write a query that returns only the meaningful reviews. These are reviews that are readable in English. There are two columns in the table, let your output return only the review column.
#### Query
```sql
--select review
select Review

--from the bonus table
from BonusTable1

--filter translation as null
where translation is null
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/e8f4b905-6f34-4986-83ad-5ca52268103d)

**Day 15 Question**: Your company started consulting for Micro Bank who needs to analyze their marketing data to understand their customers better. This will help them plan their next marketing campaign. You are brought on board as the analyst for this job. They have an offer for customers who are divorced but they need data to back up the campaign. Using the marketing data, write a query to show the percentage of customers who are divorced and have balances greater than 2000
#### Query
```sql
--select the percentage of total customers and alias as perc_divorced_with_high_bal
select (count(*) * 100/(select count(*) from [Marketing Data])) as perc_divorced_with_high_bal

--from the marketing dataset
from [Marketing Data]

--filter marital for divorced and balances > 2000
where marital = 'divorced' and balance > 2000;
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/06b5d433-3545-4c5c-ad23-b167ecdd6e1a)

**Day 16 Question**: Micro Bank wants to be sure they have enough data for this campaign and would like to see the total count of each job as contained in the dataset. Using the marketing data, write a query to show the count of each job, arrange the total count in Desc order.
#### Query
```sql
--select job and its count
select job, count(*) as job_count

--from the required dataset
from [Marketing Data]

--group by job
group by job

--order by the count of job
order by job_count desc; 
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/74bd4afa-21f4-4aba-8b49-e11eb008b208)

**Day 17 Question**: Just for clarity purposes, your company wants to see which education level got to the management job the most. Using the marketing data, write a query to show the education level that gets the management position the most. Let your output show the education, job and the count of jobs columns.
#### Query
```sql
--select the top 1 educational level, job and job count
select top 1 education, job, count(job) as job_count

--from the required dataset
from [Marketing Data]

--filter management from the job column
where job='management'

--group by education and job
group by education,job

--order by job count
order by job_count desc;
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/14ab68f9-f078-4b1a-975b-a153ba5f899a)

**Day 18 Question**: Write a query to show the average duration of customers' employment in management positions. The duration should be calculated in years.
#### Query
```sql
--select the average of dration dividing by 52 weeks
select avg(duration)/52 as avg_employment_duration

--from the marketing dataset
from [Marketing Data]

--filter management on the job column
where job = 'management'
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/30d03436-319d-4fc0-836e-4591fbda1a63)

**Day 19 Question**: What's the total number of customers that have housing, loan and are single?
#### Query
```sql
--select loan, housing, marital and total count of customers
select loan, housing, marital, count(*) as total_count

--from the marketing data
from [Marketing Data]

--filter loan and housing as yes and marital status as single
where loan = 'yes' 
		and housing ='yes'
		and marital ='single'

--group by loan, housing and marital status
group by loan, housing, marital;
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/63c6b189-2458-4e56-9637-2903b6bb701a)

**Day 20 Question**: Using the Movie data, write a query to show the movie title with runtime of at least 250. Show the title and runtime columns in your output.
#### Query
```sql
--select title and runtime
select title, runtime

--from the movie dataset
from Movie_data

--filter runtime to be greater or equal to 250
where runtime  >= 250

--order in desc
order by runtime desc
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/ecd3de57-7faa-4f15-b59c-ef1ba9cddec3)

**Day 22 Question**: Using the Employee Table dataset, write a query to show all the employees first name and last name and their respective salaries. Also, show the overall average salary of the company and calculate the difference between each employee's salary and the company average salary.
#### Query
```sql
--write a query to show first name, last name, salary, overall avg salary of the company and 
--diff btw each employee and company avg salary
select first_name, last_name, salary, avg(salary) over() as com_avg_salary, salary-avg(salary) over() as salary_diff
from Employee_Table
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/c114596c-31d6-4efa-b633-cee4a9f459a1)

**Day 23 Question**: Using the Share Price dataset, write a query to show a table that displays the highest daily decrease and the highest daily increase in share price.
#### Query
```sql
--write a query to show a table that displays the highest daily decrease and the highest daily increase
select round(min([close]-[open]),2) as highest_daily_decrease, 
	round(max([close]-[open]), 2) as highest_daily_increase
from SharePrice
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/c86ab052-25e3-47a1-8c32-4a960df45851)

**Day 24 Question**: Our client is planning their logistics for 2024, they want to know the average number of days it takes to ship to the top 10 states. Using the sample superstore dataset, write a query to show the state and the average number of days between the order date and the ship date to the top 10 states
#### Query
```sql
--select state and calculate the average delivery days
select top 10 [State], avg(datediff(day, Order_Date, Ship_Date)) as AvgDaysBtwOrderAndShip

--from the Sample superstore dataset
from Sample_Superstore_Complete

--group by state
group by [state]

--order by the average delivery days 
order by avg(datediff(day, Order_Date, Ship_Date))
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/fddd50de-d894-499e-8a8c-7cc00bf6314e)

**Day 25 Question**: Your company received a lot of bad reviews about some of your products lately and the management wants to see which products they are and how many have been returned so far. Using the Orders and returns table, write a query to see the top 5 most returned products from the company.
#### Query
```sql
--select the first 5 product name, id and total count aliasing as product count
select top 5 Product_Name, Product_ID, count(*) as product_count

--from the order dataset aliasing as o to enable joining
from SampleSuperstoreComplete_Order as o

--join the order dataset with the return dataset aliasing as s
join Sample_Superstore_Complete as s

--create a join using the order ids of both datasets
on o.Order_ID = s.Order_ID

--filter returned as yes
where returned = 'yes'

--group by product name and id
group by Product_Name, Product_ID

--order by product count in descending order
order by  product_count desc;
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/b4d7a6ee-3b13-4aa4-9987-32f083dde52e)

**Day 26 Question**: Using the employee table dataset, write a query to show the ratio of the analyst job title to the entire job titles.
#### Query
```sql
--count the analyst job title and the total count of job title
select count(case when job_title ='Analyst' then 1 else NULL end) as AnalystCount,
		count(job_title) as AnalystToTotalCount

--from the employee dataset
from Employee_Table
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/00e6ca82-1a2f-472b-8fbe-94ddc525eefa)

**Day 27 Question**: Write a query to find the 3rd highest sales from the sample superstore data.
#### Query
```sql
select top 1 round(sales,2)
from(
select top 3 Sales
from Sample_Superstore_Complete
order by Sales desc
) as subquery
order by Sales asc;
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/a4056101-12e4-4714-b976-a9f8837e95b5)

**Day 29 Question**: Using the Employee dataset, please write a query to show the job title and department with the highest salary.
#### Query
```sql
select top 1 job_title, department
from Employee_Table
where salary = (select max(salary) from Employee_Table)
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/49f20986-d707-4a68-be7e-86d394cc36ce)

**Day 30 Question**: Using the Employee dataset, write a query to determine the rank of employees based on their salaries in each department. For each department, find the employee(s) with the highest salary and rank them in Desc order.
#### Query
```sql
with Rankedemployees as (
select first_name, last_name, department, salary, dense_rank() over (partition by department order by salary desc) as department_salary_rank
from Employee_Table
)

select first_name, last_name, department, salary, department_salary_rank
from Rankedemployees
```
![image](https://github.com/oenijesiku/Wunmi_portfolio/assets/87021092/6a4ebf20-92e0-4f84-993d-c9bf0a8c6aa8)

