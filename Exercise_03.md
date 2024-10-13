# Week 03
## Exercise 03

### 1. Write a query that lists the names of all countries and airports. Select Iceland as the country and assign the following aliases: name column of the country table:  alias "country name" name column of the airport table: alias "airport name" <br>
SELECT country.name AS "country name", airport.name AS "airport name" FROM country JOIN airport ON country.iso_country = airport.iso_country WHERE country.name = "Iceland";

![3-1](https://github.com/user-attachments/assets/0dc8941e-4fe2-46d1-b83b-fd733046cf46)


### 2. Write a query  to list the names of all large airports in France. Assign the name column the alias "airport name". <br>
SELECT airport.name AS "airport name" FROM airport JOIN country ON airport.iso_country = country.iso_country WHERE country.name = "France" AND airport.type = "large_airport";

![3-2](https://github.com/user-attachments/assets/861dc271-f300-4548-9e9c-dc5890b0423c)



### 3. Write a query that lists the names and country names of all airports on Antartica. Use aliases country_name and airport_name. SQLite does not support aliases with multiple words. MariaDB does, but requires the name to be enclosed in quotation marks.<br>
SELECT country.name AS "country_name", airport.name AS "airport_name" FROM country JOIN airport ON country.iso_country = airport.iso_country WHERE country.continent = "AN";

![3-3](https://github.com/user-attachments/assets/bfcb90c3-d478-4cae-bd5c-aef8e58f26c8)


### 4. What is the height of Heini's current location measured from the sea level? <br>
SELECT airport.elevation_ft FROM airport JOIN game ON airport.ident = game.location WHERE game.screen_name = "Heini";

![3-4](https://github.com/user-attachments/assets/afc3afcd-82e6-436e-bcbe-6b323488f617)


### 5. What is the height of Heini's current location measured from the sea level? Print out the result in meters and assign the result the alias elevation_m. One feet corresponds to 0.3048 meters. <br>
SELECT airport.elevation_ft * 0.3048 AS "elevation_m" FROM airport JOIN game ON airport.ident = game.location WHERE game.screen_name = "Heini"

![3-5](https://github.com/user-attachments/assets/da856ee2-f59e-48c4-89e7-66bc27e5291e)



### 6. What is the name of the airport Ilkka is currently at? <br>
SELECT airport.name FROM airport JOIN game ON airport.ident = game.location WHERE game.screen_name = "Ilkka";

![3-6](https://github.com/user-attachments/assets/fabea1a8-ac24-4a4f-b0c2-54b03b6b0222)



### 7. What is the name of the country Ilkka is currently at? <br>
SELECT country.name FROM country JOIN airport ON airport.iso_country = country.iso_country JOIN game ON airport.ident = game.location WHERE game.screen_name = "Ilkka";

![3-7](https://github.com/user-attachments/assets/4eba0a7d-ad4d-416e-b9ca-78532e2b76d8)


### 8. List the weather condition goals Heini as achieved so far.<br>
SELECT goal.name FROM goal_reached INNER JOIN goal ON goal_reached.goal_id = goal.id INNER JOIN game ON goal_reached.game_id = game.id WHERE game.screen_name = "Heini";

![3-8](https://github.com/user-attachments/assets/631263a0-57ce-4252-85e3-c339308f54e7)


### 9. Print out the name of the airport where Ilkka achieved the clouds weather goal. <br>
SELECT airport.name FROM goal_reached INNER JOIN goal ON goal_reached.goal_id = goal.id INNER JOIN game ON goal_reached.game_id = game.id INNER JOIN airport ON airport.ident = game.location WHERE game.screen_name = "Ilkka" AND goal.name = "CLOUDS";

![3-9](https://github.com/user-attachments/assets/b46d6da4-0aba-413c-a185-37d9a2100abe)


### 10. Print out the name of the country where Ilkka achieved the clouds goal. (Br)

![3-10](https://github.com/user-attachments/assets/8949a478-ceda-41df-bb1d-eb68a28306f7)













