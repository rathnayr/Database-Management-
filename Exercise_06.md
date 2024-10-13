# Week 5
## Exercise 06
### 1. What is the elevation of the highest airport location? <br>
SELECT MAX(elevation_ft) FROM airport;

![6-1](https://github.com/user-attachments/assets/5708f5ad-e52c-47b3-a2d4-e7526549fc9a)


### 2. Write a query that lists all continents and the number of countries on them. <br>
SELECT continent, COUNT(*) FROM country GROUP BY continent;

![6-2](https://github.com/user-attachments/assets/8a5b3ec6-fb8a-4e3e-aba4-4fe8082979f4)


### 3. List the names of all players and the number of weather goals they have achieved. <br>
SELECT game.screen_name, COUNT(*) FROM game JOIN goal_reached ON game.id = goal_reached.game_id JOIN goal ON goal.id = goal_reached.goal_id GROUP BY game.screen_name;

![6-3](https://github.com/user-attachments/assets/9e794ac6-f7e1-46d4-80e6-0e1e3cc98e39)


### 4. Which player has the smallest carbon foot print? <br>
SELECT game.screen_name FROM game WHERE co2_consumed = ( SELECT MIN(co2_consumed) FROM game );

![6-4](https://github.com/user-attachments/assets/667842f3-f328-4ae9-baef-c73e3c52907d)

### 5. Print out the names of all countries and the number of airports in each country. Order the results by the airport count in descending order. Only include the top 50 countries with the largest number of airports <br>
SELECT country.name, COUNT(airport.ident) AS COUNT FROM country JOIN airport ON country.iso_country = airport.iso_country GROUP BY country.name ORDER BY COUNT DESC LIMIT 50;

![6-5](https://github.com/user-attachments/assets/8ca40a7e-2743-4b0a-a4cf-6ab2fa9e18d8)

### 6. List the countries with more than 1000 airports. Use the iso_country field in the query. <br>
SELECT country.name FROM country JOIN airport ON country.iso_country = airport.iso_country GROUP BY country.name HAVING COUNT(airport.iso_country) > 1000;

![6-6](https://github.com/user-attachments/assets/76de7e43-cc8f-4d0e-987f-9050d6ab35fc)

### 7. Print out the name of the highest airport in the world. <br>
SELECT airport.name FROM airport WHERE elevation_ft = ( SELECT MAX(elevation_ft) FROM airport );

![6-7](https://github.com/user-attachments/assets/44591d82-7ced-4d4e-9798-57cc39a7c8ee)


### 8. In which country does the highest airport reside in? <br>
SELECT country.name FROM country JOIN airport ON country.iso_country = airport.iso_country WHERE airport.elevation_ft = ( SELECT MAX(elevation_ft) FROM airport );

![6-8](https://github.com/user-attachments/assets/b6fcd93a-aaf0-4949-a002-3037f6962d75)


### 9. How many weather goals has Vesa achieved so far? <br>
SELECT COUNT(*) FROM game JOIN goal_reached ON game.id = goal_reached.game_id JOIN goal ON goal.id = goal_reached.goal_id WHERE game.screen_name = "Vesa";

![6-9](https://github.com/user-attachments/assets/f364b2a1-6988-484a-b3f3-5091a77a3b9d)


### 10. What is the name of the airport that resides closest to the polar regions? <br>
SELECT name FROM airport WHERE ABS(latitude_deg) = ( SELECT MAX(ABS(latitude_deg)) FROM airport );

![6-10](https://github.com/user-attachments/assets/6b780cb9-f7f8-4757-a268-d38f5456ebe8)

