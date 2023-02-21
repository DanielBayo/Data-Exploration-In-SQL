1. Show all records from the language table from the dvd_rentals schema

```sql
SELECT *
FROM dvd_rentals.language;
```
* Output:
|language_id|name|last_update|
|:----|:----|:----|
|1|English             |2006-02-15T05:02:19.000Z|
|2|Italian             |2006-02-15T05:02:19.000Z|
|3|Japanese            |2006-02-15T05:02:19.000Z|
|4|Mandarin            |2006-02-15T05:02:19.000Z|
|5|French              |2006-02-15T05:02:19.000Z|
|6|German              |2006-02-15T05:02:19.000Z|

2. Show only the language_id and name columns from the language table
```sql
SELECT
    language_id,
    name
FROM dvd_rentals.language
```
* Output:
|language_id|name|
|:----|:----|
|1|English             |
|2|Italian             |
|3|Japanese            |
|4|Mandarin            |
|5|French              |
|6|German|

3. Show the first 10 rows from the actor tables
```sql
SELECT *
FROM dvd_rentals.actor
LIMIT 10;
```
* Output:
|actor_id|first_name|last_name|last_update|
|:----|:----|:----|:----|
|1|PENELOPE|GUINESS|2006-02-15T04:34:33.000Z|
|2|NICK|WAHLBERG|2006-02-15T04:34:33.000Z|
|3|ED|CHASE|2006-02-15T04:34:33.000Z|
|4|JENNIFER|DAVIS|2006-02-15T04:34:33.000Z|
|5|JOHNNY|LOLLOBRIGIDA|2006-02-15T04:34:33.000Z|
|6|BETTE|NICHOLSON|2006-02-15T04:34:33.000Z|
|7|GRACE|MOSTEL|2006-02-15T04:34:33.000Z|
|8|MATTHEW|JOHANSSON|2006-02-15T04:34:33.000Z|
|9|JOE|SWANK|2006-02-15T04:34:33.000Z|
|10|CHRISTIAN|GABLE|2006-02-15T04:34:33.000Z|

4. What are the first 5 values in the country column from the country table by alphabetical order?
```sql
SELECT country
FROM dvd-rentals.country
ORDER BY country
LIMIT 5;
```
* Output:
|country|
|:----|
|Afghanistan|
|Algeria|
|American Samoa|
|Angola|
|Anguilla|

5. What are the 5 lowest total_sales values in the sales_by_film_category table?
```sql
SELECT
    total_sales
FROM dvd_rentals.sales_by_film_category
ORDER BY 1