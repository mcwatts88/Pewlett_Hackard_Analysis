# Pewlett Hackard Analysis

## Overview of Project

Pewlett Hackard is facing a large number of upcoming retirements of current employees. In order to mitigate this loss of talent from the workforce the company has decided to implement a mentorship program between the employees approaching retirement and employees pick to replace the roles that will soon be empty. The objective of this project was to get a list of employees that will be approaching retirement along with their current title and a mentorship eligibility list for current employees.

## Results

* The engineering department is being hit the hardest by this retirement wave. See the below table for a breakdown of retirement by title.

![retiring_titles.PNG](https://github.com/mcwatts88/Pewlett_Hackard_Analysis/blob/main/retiring_titles.PNG)

* Management only has 2 roles needing to be filled, leaving engineering and staff as the most affected

* There are 1549 employees eligible for the mentorship program

![mentorship_eligibility.PNG](https://github.com/mcwatts88/Pewlett_Hackard_Analysis/blob/main/mentorship_eligibility.PNG)

* There are only 579 engineering employees eligible for mentoring to cover the over 35,000 engineering employees that are departing.

## Summary

There are two questions asked of this data analysis:

* How many roles will need to be filled as the "silver tsunami" begins to make an impact?

This can be determined by using the below query

```
SELECT SUM(count)
FROM retiring_titles;
```

Running this query indicates that 72458 roles will need to be filled.

* Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

Running the query

```
SELECT count(emp_no)
FROM mentorship_eligibility;
```

There are not enough mentees to cover the "silver tsunami." There are only 1549 mentees eligible to cover 72458 roles.

The role counts of the eligible employees can be found by using the query

```
SELECT COUNT(title) AS "count", title
FROM mentorship_eligibility
GROUP BY title
ORDER BY "count" DESC;
```
