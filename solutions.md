## The youngest musicians first.

<pre> first_name |   last_name    |    date_of_birth    |  instrument   
------------+----------------+---------------------+---------------
 Oriol      | Hunter         | 1998-05-29 23:34:56 | Drums
 Loretta    | Clark          | 1997-12-05 17:51:56 | Drums
 Gerald     | Ali            | 1994-10-13 05:55:12 | Clarinet
 Arturo     | Schumacher     | 1994-09-17 17:45:58 | Trombone
 Bernhard   | Hunter         | 1994-05-19 12:39:27 | Voice
 Bernhard   | Hunter         | 1994-03-20 07:46:53 | Saxphone
 Olivia     | Karnasiotti    | 1993-11-23 17:11:58 | Flute
 Loretta    | O&apos;Connor       | 1993-09-07 20:40:22 | Voice
 Aaliyah    | Brown          | 1993-08-20 18:26:23 | Clarinet
 Oriol      | Miller         | 1992-04-10 12:39:51 | Trumpet
 Grace      | Blanc          | 1991-08-18 13:24:56 | Saxphone
 ...
</pre>

## task4 (10 youngest)

<pre>data=# SELECT * FROM musician ORDER BY date_of_birth DESC limit 10;
 first_name |  last_name  |    date_of_birth    | instrument 
------------+-------------+---------------------+------------
 Oriol      | Hunter      | 1998-05-29 23:34:56 | Drums
 Loretta    | Clark       | 1997-12-05 17:51:56 | Drums
 Gerald     | Ali         | 1994-10-13 05:55:12 | Clarinet
 Arturo     | Schumacher  | 1994-09-17 17:45:58 | Trombone
 Bernhard   | Hunter      | 1994-05-19 12:39:27 | Voice
 Bernhard   | Hunter      | 1994-03-20 07:46:53 | Saxphone
 Olivia     | Karnasiotti | 1993-11-23 17:11:58 | Flute
 Loretta    | O&apos;Connor    | 1993-09-07 20:40:22 | Voice
 Aaliyah    | Brown       | 1993-08-20 18:26:23 | Clarinet
 Oriol      | Miller      | 1992-04-10 12:39:51 | Trumpet
(10 rows)
</pre>

## task5 (Saxophone)

<pre>data=# update musician set instrument =&apos;Saxophone&apos; where instrument = &apos;Saxphone&apos;;
UPDATE 6
data=# select * from musician where instrument = &apos;Saxophone&apos;;
 first_name | last_name |    date_of_birth    | instrument 
------------+-----------+---------------------+------------
 Ella       | Moore     | 1962-02-25 04:30:36 | Saxophone
 Bernhard   | Hunter    | 1994-03-20 07:46:53 | Saxophone
 Olivia     | Hutticher | 1969-12-02 08:52:37 | Saxophone
 Grace      | Jones     | 1959-04-15 20:19:27 | Saxophone
 Grace      | Blanc     | 1991-08-18 13:24:56 | Saxophone
 William    | Adams     | 1980-07-03 11:25:22 | Saxophone
(6 rows)
</pre>

## task6 (piano)

<pre>data=# SELECT instrument FROM musician WHERE first_name = &apos;Bernhard&apos; and last_name =&apos;Schwarzenegger&apos; ;
 instrument 
------------
 Piano
(1 row)
</pre>

## task7

<pre>data=# SELECT last_name, date_of_birth
FROM musician
WHERE first_name = &apos;Araceli&apos;
AND instrument = &apos;Piano&apos;;
 last_name |    date_of_birth    
-----------+---------------------
 Garcia    | 1999-09-07 22:44:10
(1 row)
</pre>

## task8

<pre>data=# SELECT first_name, last_name, instrument
FROM musician
WHERE instrument IN (&apos;Piano&apos;, &apos;Guitar&apos;)
ORDER BY instrument, last_name;</pre>

## task9

<pre>data=# SELECT first_name, last_name, date_of_birth, instrument
FROM musician
WHERE first_name = &apos;Araceli&apos; AND instrument IN (&apos;Piano&apos;, &apos;Guitar&apos;)
ORDER BY date_of_birth
LIMIT 3;
 first_name | last_name |    date_of_birth    | instrument 
------------+-----------+---------------------+------------
 Araceli    | Lewis     | 1950-11-26 13:26:01 | Guitar
 Araceli    | Ali       | 1955-07-13 07:07:38 | Piano
 Araceli    | White     | 1971-11-01 15:02:13 | Piano
(3 rows)
</pre>

## task10

<pre>data=# SELECT DISTINCT instrument
FROM musician
ORDER BY instrument;
  instrument   
---------------
 Cello
 Clarinet
 Drums
 Electric Bass
 Flute
 Guitar
 Harp
 Keyboard
 Piano
 Saxophone
 Trombone
 Trumpet
 Violin
 Voice
(14 rows)

</pre>

## task11

<pre>data=# SELECT first_name AS Name, last_name AS &quot;Family name&quot;, date_of_birth AS &quot;Date of birth&quot;
FROM musician
WHERE instrument = &apos;Harp&apos;
AND last_name LIKE &apos;M%&apos;
ORDER BY date_of_birth ASC
LIMIT 1
OFFSET 3;
 name  | Family name |    Date of birth    
-------+-------------+---------------------
 Lucas | Müller      | 1972-04-25 23:15:24
(1 row)
</pre>

## task12

<pre>data=# SELECT first_name, last_name, date_of_birth, instrument
FROM musician
WHERE last_name NOT LIKE &apos;Y%&apos; AND last_name NOT LIKE &apos;M%&apos; AND last_name NOT LIKE &apos;C%&apos; AND last_name NOT LIKE &apos;A%&apos;
ORDER BY last_name, first_name
LIMIT 5 OFFSET 4;
 first_name | last_name |    date_of_birth    | instrument 
------------+-----------+---------------------+------------
 Abigail    | Black     | 1969-10-11 23:08:11 | Piano
 Benjamin   | Black     | 1995-08-28 23:25:55 | Keyboard
 Evelyn     | Black     | 1951-08-20 00:36:39 | Violin
 Naomi      | Black     | 1987-03-16 00:23:44 | Harp
 Noah       | Black     | 1959-03-10 00:16:37 | Cello
(5 rows)
</pre>

## task13

<pre> first_name |   last_name    |    date_of_birth    | instrument 
------------+----------------+---------------------+------------
 Aaliyah    | Ahmas          | 1991-02-03 09:47:31 | Harp
 Noah       | Muller         | 1950-09-14 16:59:59 | Cello
 Amelia     | Martí          | 1963-10-15 14:22:20 | Violin
 Chloe      | Nguyen         | 1961-02-25 21:25:29 | Violin
 Julia      | Masferrer      | 1990-06-18 05:20:34 | Harp
 Lucas      | Young          | 1961-01-31 20:00:49 | Violin
 William    | Miller         | 1964-12-25 22:55:54 | Harp
 Naomi      | Lewis          | 1951-08-20 00:06:42 | Harp
 Evelyn     | Black          | 1951-08-20 00:36:39 | Violin
 Abdul      | Schwarzenegger | 1975-08-20 10:48:32 | Harp
 Ahmed      | Jones          | 1982-09-20 11:51:42 | Cello
 Noah       | Sanchez        | 1974-04-12 23:02:47 | Cello
 Anna       | Masferrer      | 1950-10-08 18:57:48 | Guitar
 ...
</pre>

## task14

<pre>data=# TRUNCATE TABLE musician;
TRUNCATE TABLE
data=# SELECT * FROM musician;
 first_name | last_name | date_of_birth | instrument 
------------+-----------+---------------+------------
(0 rows)

data=# 
</pre>
