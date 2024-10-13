# Week 04
## Exercise 05
### 1. One country has an airport where the airport name begins with the word "Satsuma". Print out the name of the country. <br>
SELECT country.name FROM country WHERE country.iso_country IN ( SELECT airport.iso_country FROM airport WHERE airport.name LIKE "Satsuma%" );

![5-1](https://github.com/user-attachments/assets/c34b4ba7-338e-4bf1-b1ae-fcf77393cfa3)

### 2. List the names of all airports in Monaco.<br>
SELECT airport.name FROM airport WHERE airport.iso_country IN ( SELECT country.iso_country FROM country WHERE country.name = "Monaco" );

![5-2](https://github.com/user-attachments/assets/66efcd2d-0e83-4612-9130-bc38e355378a)

### 3. List the names of all players who have achieved the clouds goal. <br>
SELECT game.screen_name FROM game WHERE game.id IN ( SELECT goal_reached.game_id FROM goal_reached WHERE goal_reached.goal_id IN ( SELECT goal.id FROM goal WHERE goal.name = "CLOUDS" ));

![5-3](https://github.com/user-attachments/assets/b6362a71-d050-451d-9556-3c49ecaaf4ff)

### 4. List all countries that have no airports. <br>
SELECT country.name FROM country WHERE country.iso_country NOT IN ( SELECT DISTINCT airport.iso_country FROM airport );

![5-4](https://github.com/user-attachments/assets/549ec846-0a5c-42e6-a535-1dfaf8df871b)

### 5. Which weather goals has Heini not achieved yet? <br>
SELECT goal.name FROM goal WHERE goal.id NOT IN ( SELECT goal_reached.goal_id FROM goal_reached WHERE goal_reached.game_id IN ( SELECT game.id FROM game WHERE game.screen_name = "Heini" ));

![5-5](https://github.com/user-attachments/assets/e505fe39-3eed-4127-b33a-4ee45afc3983)

