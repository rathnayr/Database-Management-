# Week 04
## Exercise 05
### 1. One country has an airport where the airport name begins with the word "Satsuma". Print out the name of the country. <br>
select name from country where iso_country in(
select iso_country from airport where name like 'Satsuma%');
![1](https://github.com/user-attachments/assets/e022927c-ebef-4c60-90dc-79d91bf872a0)

### 2. List the names of all airports in Monaco.<br>
select name from airport
where iso_country in(
select iso_country from country
where name = 'Monaco');
![2](https://github.com/user-attachments/assets/e42071db-92c1-4b33-b839-4c817bbf8649)

### 3. List the names of all players who have achieved the clouds goal. <br>
select screen_name from game
where id in (
select game_id from goal_reached
where goal_id in (
select id from goal
where name = "CLOUDS"));
![3](https://github.com/user-attachments/assets/c1f9d835-1c71-4244-9855-008ab78839f5)

### 4. List all countries that have no airports. <br>
select name from country
where iso_country not in(
select iso_country from airport);
![4](https://github.com/user-attachments/assets/a3193db6-f268-4426-ae3c-074df36829d5)

### 5. Which weather goals has Heini not achieved yet? <br>
select name from goal
where id not in(
select goal_id from goal_reached
where game_id in (
select id from game
where screen_name = "Heini"));
![5](https://github.com/user-attachments/assets/e377545c-c28e-4e22-80d6-369ab09b4e94)


