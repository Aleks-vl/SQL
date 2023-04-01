# SQL
### SQL запросы 
###  <h2 align="left">
### Таблица Trip (купленные билеты). 
###  Таблица Pass_in_trip (таблица, связывающая купленные билеты с пассажирами). 
###  Таблица Company (Компании осуществляющие авиаперелеты).
###  Таблица Passenger (Пассажиры купившие билет).</h2>
![Image alt](https://github.com/Aleks-vl/SQL/blob/main/%D1%82%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D0%B0.png)
  
###   <h3 align="left">:heavy_check_mark: Вывести названия всех авиакомпаний </h3> 
 
 ```SQL
SELECT 
name 
FROM 
Company;
```
###  <h2 align="left">Результат</h2>

```
	name
1	Don_avia
2	Aeroflot
3	Dale_avia
4	air_France
5	British_AW

 ```
###   <h3 align="left">:heavy_check_mark: Вывести все рейсы, совершенные из Москвы </h3> 
  
 ```SQL
SELECT 
* 
FROM 
Trip
WHERE 
town_from = 'Moscow';
```
###  <h2 align="left">Результат</h2>
  
 ```
           id	company	plane town_from town_to	           time_out	                      time_in
1	1145	2	IL-86	Moscow	Rostov	1900-01-01T09:35:00.000Z	1900-01-01T11:23:00.000Z
2	1182	1	TU-134	Moscow	Rostov	1900-01-01T12:35:00.000Z	1900-01-01T14:30:00.000Z
3	1188	1	TU-134	Moscow	Rostov	1900-01-01T22:50:00.000Z	1900-01-02T00:48:00.000Z
4	1196	1	TU-154	Moscow	Rostov	1900-01-01T04:00:00.000Z	1900-01-01T05:45:00.000Z


 ```
 
 ###   <h3 align="left">:heavy_check_mark: Вывести имена людей, которые заканчиваются на "man" </h3> 
 
  ```SQL
  SELECT 
name 
FROM 
Passenger
WHERE 
name LIKE '%man';

  ```
  ###  <h2 align="left">Результат</h2>
  ```
  	name
1	Nikole Kidman
2	Alan Rickman
3	Gary Oldman

   ```
  ###   <h3 align="left">:heavy_check_mark: В какие города летал Bruce Willis </h3>  
  
   ```SQL
SELECT 
town_to
FROM 
Trip
JOIN Pass_in_trip ON Trip.id = Pass_in_trip.trip
JOIN Passenger ON Pass_in_trip.passenger = Passenger.id 
WHERE 
name = 'Bruce Willis';

 ```
   ###  <h2 align="left">Результат</h2>
  ```
  town_to
1	Paris
2	Vladivostok
3	Moscow

  ```
