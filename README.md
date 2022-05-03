# SQL practice
practice SQL queries

### The first queries are very simple.
**Prompt:** Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA. The CITY table is described as follows:
| Field | Type |
| :---- | :--- |
| ID | NUMBER |
| NAME | VARCHAR2 (17) |
| COUNTRYCODE | VARCHAR2 (3) |
| DISTRICT | VARCHAR2 (20) |
| POPULATION | NUMBER |

My query selects all columns (`SELECT *`) from the CITY table (`FROM CITY`) that meet the 2 conditions that the city is located in the USA (`WHERE COUNTRYCODE = "USA"`) and that the population is at least 100,000 (`AND POPULATION > 100000`).
```sql
SELECT *
FROM CITY
WHERE COUNTRYCODE = "USA"
AND POPULATION > 100000
```
**Prompt:** Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

This query is virtually identical to the first prompt with some minor modifications. My query returns only the NAME field (`SELECT NAME`) of American cities where the population is larger than 120,000 (`WHERE COUNTRYCODE = "USA" AND POPULATION > 120000`).
```sql
SELECT NAME
FROM CITY
WHERE COUNTRYCODE = "USA"
AND POPULATION > 120000
```
