# Week 03
## Exercise 03

### 1. Write a query that lists the names of all countries and airports. Select Iceland as the country and assign the following aliases: name column of the country table:  alias "country name" name column of the airport table: alias "airport name" <br>
SELECT country.name as "country name", airport.name as "airport name"
FROM country, airport
WHERE country.iso_country = airport.iso_country and country.name = "Iceland";
![1](https://github.com/user-attachments/assets/ed33fd06-60e2-4a1e-8067-4c3e02cce14e)

### 2. Write a query  to list the names of all large airports in France. Assign the name column the alias "airport name". <br>
SELECT airport.name as "airport name"
FROM airport, country
where airport.iso_country=country.iso_country and country.name = "France" AND airport.type = "large_airport";
![2](https://github.com/user-attachments/assets/43929310-0fa9-452e-908a-809d2a001fe7)

### 3. Write a query that lists the names and country names of all airports on Antartica. Use aliases country_name and airport_name. SQLite does not support aliases with multiple words. MariaDB does, but requires the name to be enclosed in quotation marks.<br>
![3](https://github.com/user-attachments/assets/b04d0079-16fa-4da5-9dfa-1c32a1507a3b)

### 4. What is the height of Heini's current location measured from the sea level? <br>
SELECT elevation_ft
from airport, game
where location = ident and screen_name="Heini";
![4](https://github.com/user-attachments/assets/1acd7535-bbc9-4936-8b77-948415db2cb7)

### 5. What is the height of Heini's current location measured from the sea level? Print out the result in meters and assign the result the alias elevation_m. One feet corresponds to 0.3048 meters. <br>
select elevation_ft * 0.3048 as "elevation_m"
from airport, game
where location = ident and screen_name="Heini";
![5](https://github.com/user-attachments/assets/2e668a6d-84c2-4767-85fd-3ff63c1f7e77)

### 6. What is the name of the airport Ilkka is currently at? <br>
select airport.name as "name"
from airport, game
where location = ident and screen_name = "Ilkka";
![6](https://github.com/user-attachments/assets/b2e47314-5735-4614-b00d-fa72e26e54a2)

### 7. What is the name of the country Ilkka is currently at? <br>
select country.name as "name"
from country, airport, game
where location = ident and airport.iso_country = country.iso_country and screen_name = "Ilkka";
![7](https://github.com/user-attachments/assets/55fd7b70-7f28-4ea0-9d96-267772733e44)

### 8. List the weather condition goals Heini as achieved so far.<br>
select name from goal, game, goal_reached where game.id=game_id and goal.id=goal_id and screen_name="Heini";
![8](https://github.com/user-attachments/assets/98c646ae-d07d-4817-b1d1-9f0d84c580ce)

### 9. Print out the name of the airport where Ilkka achieved the clouds weather goal. <br>
select airport.name from airport, goal_reached, goal, game
where ident = location and goal.id = goal_reached.goal_id and game.id = goal_reached.game_id and screen_name = "Ilkka" and goal.name = "CLOUDS";
![9](https://github.com/user-attachments/assets/6ee97866-e3b1-4127-b0bd-538fda0fb701)

### 10. Print out the name of the country where Ilkka achieved the clouds goal. (Br)
select country.name
from country, game, goal, goal_reached, airport
where airport.iso_country = country.iso_country and ident=location AND
game_id=game.id AND goal_id=goal.id and screen_name = "Ilkka" and goal.name = "CLOUDS";
![10](https://github.com/user-attachments/assets/44bb5fa1-5dba-47e6-9a04-e0b0fa02188a)











