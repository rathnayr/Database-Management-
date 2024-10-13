# Week 04
## Exercise 04
### 1. List all Finnish airports that provide scheduled services. The result must include both the name of the country as well as the name of the airport. <br>
SELECT country.name AS "country name", airport.name AS "airport name" FROM country INNER JOIN airport ON airport.iso_country = country.iso_country WHERE country.name = "Finland" AND airport.scheduled_service = "yes";

![4-1](https://github.com/user-attachments/assets/c3f9fe6e-e054-4ce7-a47b-5833e3eceb8c)


### 2. List the names and current airports of all players. <br>
SELECT game.screen_name, airport.name FROM game INNER JOIN airport ON airport.ident = game.location;

![4-2](https://github.com/user-attachments/assets/314ee594-b18c-45e4-b589-6b33d783ed14)


### 3. List the names and current countries of all players. <br>
SELECT game.screen_name, country.name FROM game INNER JOIN airport ON airport.ident = game.location INNER JOIN country ON country.iso_country = airport.iso_country;

![4-3](https://github.com/user-attachments/assets/e1276287-e10f-44d6-bf54-770705b99f3c)


### 4. List the names of all airports that include the string "Hels" and the names of any players that might currently be on any of the listed airports. <br>
SELECT airport.name, game.screen_name FROM airport LEFT JOIN game ON game.location = airport.ident WHERE airport.name LIKE "%Hels%";

![4-4](https://github.com/user-attachments/assets/222c867e-2699-4bd3-b622-2e75601c884b)


### 5. List the names of all weather goals and the names of any players that have so far achieved the listed goals. <br>
SELECT goal.name, game.screen_name FROM goal_reached LEFT JOIN game ON game.id = goal_reached.game_id RIGHT JOIN goal ON goal.id = goal_reached.goal_id;

![4-5](https://github.com/user-attachments/assets/698656ae-1140-4d0c-afbb-112db9c59c37)





