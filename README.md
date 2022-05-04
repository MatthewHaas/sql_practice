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

**Prompt:** Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
The STATION table is described as follows:
| Field | Type |
| :---- | :--- |
| ID | NUMBER |
| CITY | VARCHAR2 (21) |
| STATE | VARCHAR2 (2) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

This query requires two new concepts to achieve the goal of the prompt. The keyword `DISTINCT` is necessary in the `SELECT` statement and I need to use a modulo (`MOD(column_name, 2) = 0`) is necessary to test if the ID number is even (divisible by 2).
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE MOD(ID,2) = 0
```

**Prompt:** Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically. 
```sql
SELECT CITY, LENGTH(CITY) FROM STATION ORDER BY Length(CITY) ASC, CITY limit 1;
SELECT CITY, LENGTH(CITY) FROM STATION ORDER BY Length(CITY) DESC, CITY limit 1;
```

**Prompt:** Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%';
```

**Prompt:** Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

```sql
SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%a' OR CITY LIKE '%e' OR CITY LIKE '%i' OR CITY LIKE '%o' OR CITY LIKE '%u';
```

**Prompt:** Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

```sql
SELECT DISTINCT CITY FROM STATION WHERE SUBSTR(CITY,1,1) NOT IN ('A', 'E', 'I', 'O', 'U') OR SUBSTR(CITY,LENGTH(CITY),1) NOT IN ('a', 'e', 'i', 'o', 'u');
```
