# Week 04
## Exercise 04
### 1. List all Finnish airports that provide scheduled services. The result must include both the name of the country as well as the name of the airport. <br>
select country.name as "country name", airport.name as "airport name"
from country inner join airport on country.iso_country=airport.iso_country
where country.name="Finland"
and airport.scheduled_service="yes";
![1](https://github.com/user-attachments/assets/0291bf3a-a599-4403-aef1-b9b51063375b)

### 2. List the names and current airports of all players. <br>
select screen_name, airport.name
from game inner join airport on game.location = airport.ident;
![2](https://github.com/user-attachments/assets/91fa54d3-369b-437b-b00c-16518ad6a9be)

### 3. List the names and current countries of all players. <br>
select screen_name, country.name
from game inner join airport on game.location = airport.ident
inner join country on country.iso_country=airport.iso_country;
![3](https://github.com/user-attachments/assets/f12f2c08-b4f6-4829-b3e5-b0b4cb2b3dcd)

### 4. List the names of all airports that include the string "Hels" and the names of any players that might currently be on any of the listed airports. <br>
select airport.name, screen_name
from airport left join game on airport.ident = game.location
where airport.name like "%Hels%";
![4](https://github.com/user-attachments/assets/78a8f65b-7e8e-4882-ac03-1c17afb31ab3)

### 5. List the names of all weather goals and the names of any players that have so far achieved the listed goals. <br>
select name, screen_name
from goal left join goal_reached on goal.id = goal_reached.goal_id
left join game on goal_reached.game_id = game.id;

![5](https://github.com/user-attachments/assets/1e0c5177-30e9-4317-9e0f-4f7b80e3ac3f)



