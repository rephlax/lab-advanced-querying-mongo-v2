![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

## Iteration 2

**1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.**

{name: "Babelgum"} in query
{name: 1, _id: 0} in project

<br>

**2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by *number of employees*.**

{number_of_employees: {$gt: 5000}} in query
20 in limit

<br>

**3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fields.**

{$and: [{founded_year: {$gte: 2000}}, {founded_year: {$lte: 2005}}]} in query
{name: 1, _id: 0, founded_year: 1} in project

<br>

**4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.**

{$and: [{"ipo.valuation_amount": {$gte: 100000000}}, {founded_year: {$lte: 2010}}]} in query
{name: 1, _id: 0, ipo: 1} in project

<br>

**5. All the companies that don't include the `partners` field.**

{partners: {$exists: false}} in query

<br>

**6. All the companies that have a null value on the `category_code` field.**

{category_code: {$type: "null"}} in query

<br>

**7. Order all the companies by their IPO price in a descending order.**

{"ipo.valuation_amount": -1} in sort

<br>

**8. Retrieve the 10 companies with most employees, order by the `number of employees`.**

{number_of_employees: {$exists: true}} in query
{number_of_employees: -1} in sort
10 in limit

<br>

**9. All the companies founded on the second semester of the year (July to December). Limit your search to 1000 companies.**

{founded_month: {$gte: 7}} in query
1000 in limit

<br>

**10. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.**

{founded_day: {$lte: 7}} in query
{"acquisition.price_amount": -1} in sort
10 in limit

<br>

## Iteration 3 (Bonus)

**1. All the companies that have been acquired after 2010, order by the acquisition amount, and retrieve only their `name` and `acquisition` field.**

<!-- Your Query Goes Here -->

<br>

**2. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.**

<!-- Your Query Goes Here -->

<br>

**3. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.**

<!-- Your Query Goes Here -->

<br>

**4. All the companies whose acquisition amount is more than 10.000.000, and currency is 'EUR'.**

<!-- Your Query Goes Here -->

<br>

**5. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.**

<!-- Your Query Goes Here -->

<br>
