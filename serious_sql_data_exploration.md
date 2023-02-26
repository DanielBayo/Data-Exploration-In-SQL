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

19. What are the 5 most frequent rating and category combinations in the film_list table?

```sql
SELECT
  rating,
  category,
  COUNT(*) AS frequency
FROM dvd_rentals.film_list
GROUP BY rating, category
ORDER BY frequency DESC
LIMIT 5;
```

**Output:**
||rating|category|frequency|
|:----|:----|:----|
|PG-13|Drama|22|
|NC-17|Music|20|
|PG-13|Foreign|19|
|PG-13|Animation|19|
|PG|Family|18|

20. Which `actor_id` has the most number of unique `film_id` records in the `dvd_rentals.film_actor` table?

```sql
SELECT
  actor_id,
  COUNT(DISTINCT film_id) AS frequency
FROM dvd_rentals.film_actor
GROUP BY actor_id
ORDER BY frequency DESC
LIMIT 10;
```
**Output:**
|actor_id|frequency|
|:----|:----|
|107|42|
|102|41|
|198|40|
|181|39|
|23|37|
|81|36|
|144|35|
|158|35|
|37|35|
|60|35|

21. How many distinct `fid` values are there for the 3rd most common `price` value in the `dvd_rentals.nicer_but_slower_film_list` table?

```sql
SELECT 
  price,
  COUNT( DISTINCT fid) AS distinct_count
FROM dvd_rentals.nicer_but_slower_film_list
GROUP BY price
ORDER BY distinct_count DESC;
```
**Output:**
|price|distinct_count|
|:----|:----|
|0.99|340|
|4.99|334|
|2.99|**323**|

22. How many unique `country_id` values exist in the `dvd_rentals.city` table?

```sql
SELECT 
  COUNT(DISTINCT country_id) As number_of_countries
FROM dvd_rentals.city;
```
**Output:**
|number_of_countries|
|:----|
|109|

23. What percentage of overall `total_sales` does the Sports `category` make up in the `dvd_rentals.sales_by_film_category` table?

```sql
SELECT 
  category,
  total_sales,
  ROUND(
  total_sales*100:: NUMERIC /SUM(total_sales) OVER()
  ,2) AS percentage_total
FROM dvd_rentals.sales_by_film_category
GROUP BY category,total_sales
ORDER BY percentage_total DESC;
```
**Output:**
|category|total_sales|percentage_total|
|:----|:----|:----|
|Sports|5314.21|7.88|
|Sci-Fi|4756.98|7.06|
|Animation|4656.30|6.91|
|Drama|4587.39|6.80|
|Comedy|4383.58|6.50|
|Action|4375.85|6.49|
|New|4352.61|6.46|
|Games|4281.33|6.35|
|Foreign|4270.67|6.33|
|Family|4235.03|6.28|
|Documentary|4217.52|6.26|
|Horror|3722.54|5.52|
|Children|3655.55|5.42|
|Classics|3639.59|5.40|
|Travel|3549.64|5.27|
|Music|3417.72|5.07|

24. What percentage of unique `fid` values are in the Children `category` in the `dvd_rentals.film_list` table?

```sql
SELECT
  category,
  ROUND(
  100*COUNT(DISTINCT fid):: NUMERIC / SUM(COUNT(DISTINCT fid)) OVER(),
  2
  ) AS percentage_of_unique
FROM dvd_rentals.film_list
GROUP BY category
ORDER BY category;
```
**Output:**
|category|percentage_of_unique|
|:----|:----|
|Action|6.42|
|Animation|6.62|
|Children|6.02|
|Classics|5.72|
|Comedy|5.82|
|Documentary|6.82|
|Drama|6.12|
|Family|6.92|
|Foreign|7.32|
|Games|6.12|
|Horror|5.62|
|Music|5.12|
|New|6.32|
|Sci-Fi|6.12|
|Sports|7.32|
|Travel|5.62|

## HEALTH DATA INSPECTION
```sql
SELECT *
FROM health.user_logs
LIMIT 10;
```

The snapshot of the first 10 rows showed that the `Health.user_logs` table has 6 columns. To know the total record count on this table, I ran the following query

```sql
SELECT COUNT(*)
FROM health.user_logs;
```
This showed that there are **43,891** records in the table. It will be okay to know the unique `id` values there are in this dataset. This will give us a feel of how many unique users there are whilst we continue getting a better picture of the dataset. We get this by running the following query,

```sql
SELECT COUNT(DISTINCT id)
FROM health.user_logs;
```
The query showed that there are **554** unique id values in the `Health.user_logs` table. Let inspect the `measure` column in the table and take a look at the most frequent values within this column. See the query below,

```sql
SELECT
  measure,
  COUNT(*) AS frequency,
  ROUND(
    100 * COUNT(*) / SUM(COUNT(*)) OVER (),
    2
  ) AS percentage
FROM health.user_logs
GROUP BY measure
ORDER BY frequency DESC;
```
|measure|frequency|percentage|
|:----|:----|:----|
|blood_glucose|38692|88.15|
|weight|2782|6.34|
|blood_pressure|2417|5.51|

As seen in the table above, most of the `measure` value are for `blood_glucose`. It will be nice if we look at the `id` column as well,

```sql
SELECT
  id,
  COUNT(*) AS frequency,
  ROUND(
    100 * COUNT(*) / SUM(COUNT(*)) OVER (),
    2
  ) AS percentage
FROM health.user_logs
GROUP BY id
ORDER BY frequency DESC
LIMIT 10;
```
|id|frequency|percentage|
|:----|:----|:----|
|054250c692e07a9fa9e62e345231df4b54ff435d|22325|50.86|
|0f7b13f3f0512e6546b8d2c0d56e564a2408536a|1589|3.62|
|ee653a96022cc3878e76d196b1667d95beca2db6|1235|2.81|
|abc634a555bbba7d6d6584171fdfa206ebf6c9a0|1212|2.76|
|576fdb528e5004f733912fae3020e7d322dbc31a|1018|2.32|
|87be2f14a5550389cb2cba03b3329c54c993f7d2|747|1.70|
|46d921f1111a1d1ad5dd6eb6e4d0533ab61907c9|651|1.48|
|fba135f6a50a2e3f371e47f943b025705f9d9617|633|1.44|
|d696925de5e9297694ef32a1c9871f3629bec7e5|597|1.36|
|6c2f9a8372dac248192c50219c97f9087ab778ba|582|1.33|

The result above showed that about 51% of the total records are from one  `id` or one user. Let's also take a quick look at the most frequent values for each column:

### Measure_value column
```sql
SELECT
  measure_value,
  COUNT(*) AS frequency
FROM health.user_logs
GROUP BY measure_value
ORDER BY frequency DESC
LIMIT 10;
```
|measure_value|frequency|
|:----|:----|
|0|572|
|401|433|
|117|390|
|118|346|
|123|342|
|122|331|
|126|326|
|120|323|
|128|319|
|115|319|

## Systolic
```sql
SELECT
  systolic,
  COUNT(*) AS frequency
FROM health.user_logs
GROUP BY 1
ORDER BY 2 DESC
LIMIT 10;
```
|systolic|frequency|
|:----|:----|
| |26023|
|0|15451|
|120|71|
|123|70|
|128|66|
|127|64|
|130|60|
|119|60|
|135|57|
|124|55|

There seems to me a lot of nulls..

### Diastolic
```sql
SELECT
  diastolic,
  COUNT(*) AS frequency
FROM health.user_logs
GROUP BY 1
ORDER BY 2 DESC
LIMIT 10;
```
|diastolic|frequency|
|:----|:----|
| |26023|
|0|15449|
|80|156|
|79|124|
|81|119|
|78|110|
|77|109|
|73|109|
|83|106|
|76|102|

This also contail a lot of null values.




