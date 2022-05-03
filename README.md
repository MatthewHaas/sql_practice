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
