1. Show all records from the `language` table from the `dvd_rentals` schema

```sql
SELECT *
FROM dvd_rentals.language;
```
**Output:**

|language_id|name|last_update|
|:----|:----|:----|
|1|English             |2006-02-15T05:02:19.000Z|
|2|Italian             |2006-02-15T05:02:19.000Z|
|3|Japanese            |2006-02-15T05:02:19.000Z|
|4|Mandarin            |2006-02-15T05:02:19.000Z|
|5|French              |2006-02-15T05:02:19.000Z|
|6|German              |2006-02-15T05:02:19.000Z|

2. Show only the `language_id` and `name` columns from the `language` table
```sql
SELECT
    language_id,
    name
FROM dvd_rentals.language
```
**Output:**

|language_id|name|
|:----|:----|
|1|English             |
|2|Italian             |
|3|Japanese            |
|4|Mandarin            |
|5|French              |
|6|German|

3. Show the first 10 rows from the `actor` tables
```sql
SELECT *
FROM dvd_rentals.actor
LIMIT 10;
```
**Output:**

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

4. What are the first 5 values in the `country` column from the `country` table by alphabetical order?
```sql
SELECT country
FROM dvd-rentals.country
ORDER BY country
LIMIT 5;
```
**Output:**

|country|
|:----|
|Afghanistan|
|Algeria|
|American Samoa|
|Angola|
|Anguilla|

5. What are the 5 lowest `total_sales` values in the `sales_by_film_category` table?
```sql
SELECT
    total_sales
FROM dvd_rentals.sales_by_film_category
ORDER BY 1
LIMIT 5;
```
**Output :**

|total_sales|
|:----|
|3417.72|
|3549.64|
|3639.59|
|3655.55|
|3722.54|

6. What are the first 5 values in reverse alphabetical order in the `country`column from `country` table

```sql
SELECT
    country
FROM dvd_rentals.country
ORDER BY country DESC
LIMIT 5;
```

**Output:**

|country|
|:----|
|Zambia|
|Yugoslavia|
|Yemen|
|Virgin Islands| U.S.|
|Vietnam|

7. Which `category` had the lowest `total_sales` value according to the `sales_by_film_category` table? what was the total_sales value?
```sql
SELECT
    category,
    total_sales
FROM dvd_rentals.sales_by_film_category
ORDER BY total_sales
LIMIT 1;
```
**Output:**

|category|total_sales|
|:----|:----|
|Music|3417.72|

8. What was the latest `payment_date` of all dvd rentals in the `payment` table?

**Output:**

|payment_date|
|:----|
|2006-02-14T15:16:03.000Z|


9. Which customer_id had the latest `rental_date` for `inventory_id`=1 and 2?

```sql
SELECT 
  customer_id,
  inventory_id,
  rental_date
FROM dvd_rentals.rental
ORDER BY inventory_id, rental_date DESC
LIMIT 8;
```
**Output:**

|customer_id|inventory_id|rental_date|
|:----|:----|:----|
|279|1|2005-08-21T21:27:43.000Z|
|518|1|2005-08-02T20:13:10.000Z|
|431|1|2005-07-08T19:03:15.000Z|
|359|2|2005-08-23T01:01:01.000Z|
|581|2|2005-07-30T22:02:34.000Z|
|161|2|2005-07-07T10:41:31.000Z|
|170|2|2005-06-17T20:24:00.000Z|
|411|2|2005-05-30T20:21:07.000Z|

10. What is the name of the `category` with the highest `category_id` in the `dvd_rentals.category` table?

```sql
SELECT 
  category_id,
  name
FROM dvd_rentals.category
ORDER BY category_id DESC
LIMIT 1;
```
**Output**
|category_id|name|
|:----|:----|
|16|Travel|
|15|Sports|
|14|Sci-Fi|
|13|New|
|12|Music|
|11|Horror|
|10|Games|
|9|Foreign|
|8|Family|
|7|Drama|
|6|Documentary|
|5|Comedy|
|4|Classics|
|3|Children|
|2|Animation|
|1|Action|

11. For the films with the longest length, what is the title of the "R" rated film with the lowest `replacement_cost` in `dvd_rentals.film` table?

```sql
SELECT 
  title,
  length,
  replacement_cost,
  rating
FROM dvd_rentals.film
ORDER BY length DESC,replacement_cost
LIMIT 10;
```
**Output**
|title|length|replacement_cost|rating|
|:----|:----|:----|:----|
|CONTROL ANTHEM|185|9.99|G|
|CHICAGO NORTH|185|11.99|PG-13|
|DARN FORRESTER|185|14.99|G|
|**HOME PITY**|185|15.99|R|
|MUSCLE BRIGHT|185|23.99|G|
|POND SEATTLE|185|25.99|PG-13|
|WORST BANGER|185|26.99|PG|
|SWEET BROTHERHOOD|185|27.99|R|
|GANGS PRIDE|185|27.99|PG-13|
|SOLDIERS EVOLUTION|185|27.99|R|

12. Who was the `manager` of the store with the highest `total_sales` in the `dvd_rentals.sales_by_store` table?

```sql
SELECT 
  manager,
  total_sales
FROM dvd_rentals.sales_by_store
ORDER BY total_sales DESC;
```
**Output**
|manager|total_sales|
|:----|:----|
|`**Jon Stephens**`|33726.77|
|Mike Hillyer|33689.74|

13. What is the `postal_code` of the city with the 5th highest `city_id` in the `dvd_rentals.address` table?

```sql
SELECT 
  city_id,
  postal_code
FROM dvd_rentals.address
ORDER BY city_id DESC
LIMIT 5;
```

**Output**
|city_id|postal_code|
|:----|:----|
|600|75559|
|599|39976|
|598|95093|
|597|40792|
|**596**|**31390**|

## RECORD COUNTS & DISTINCT VALUES

14. How many row are there in the film_list table?

```sql
SELECT 
  COUNT(*) AS row_count
FROM dvd_rentals.film_list
```
**Output**
|row_count|
|:----|
|997|

15. What are the unique values for the rating column in the film table?

```sql
SELECT DISTINCT
  rating
FROM dvd_rentals.film_list
```
**Output**
|rating|
|:----|
|NC-17|
|R|
|PG-13|
|PG|
|G|

16. How many unique category values are there in the film_list table?

```sql
SELECT 
COUNT(DISTINCT category) AS unique_category_count
FROM dvd_rentals.film_list;
```
**Output**
|unique_category_count|
|:----|
|16|

17. What is the Frequency of values in the rating column in the `film_list` table?

```sql
SELECT
  rating,
  COUNT(*) AS frequency
FROM dvd_rentals.film_list
GROUP BY rating
ORDER ;
```

**Output:**

|rating|record_count|
|:----|:----|
|NC-17|210|
|R|193|
|PG-13|223|
|PG|194|
|G|177|

18. What is the percentage of values in the rating column in the `film_list` table?
```sql
SELECT
  rating,
  COUNT(*) AS frequency,
  ROUND(
    100 * COUNT(*)::NUMERIC / SUM(COUNT(*)) OVER (),
    2
  ) AS percentage
FROM dvd_rentals.film_list
GROUP BY rating
ORDER BY frequency DESC;
```
**Output**
|rating|frequency|percentage|
|:----|:----|:----|
|PG-13|223|22.37|
|NC-17|210|21.06|
|PG|194|19.46|
|R|193|19.36|
|G|177|17.75|
