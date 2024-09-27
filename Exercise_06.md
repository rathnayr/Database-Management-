# Week 5
## Exercise 06
### 1. What is the elevation of the highest airport location? <br>
SELECT MAX(elevation_ft) FROM airport;
![1](https://github.com/user-attachments/assets/48e6ed52-aa40-40df-8615-c852430faac9)

### 2. Write a query that lists all continents and the number of countries on them. <br>
select continent, count(*)
from country
group by continent;
![2](https://github.com/user-attachments/assets/ae35b5c4-b8c2-4507-b6f8-a7a743a4bd7a)

### 3. List the names of all players and the number of weather goals they have achieved. <br>
select screen_name, count(*)
from game, goal_reached
where id = game_id
group by screen_name;
![3](https://github.com/user-attachments/assets/cceb1367-ef85-4a37-baff-f5417c894ad5)

### 4. Which player has the smallest carbon foot print? <br>
select screen_name
from game
where co2_consumed in(
select min(co2_consumed)
from game
);
![4](https://github.com/user-attachments/assets/cdc3a9a0-9719-4ee5-bdd0-cff5a461ff4a)

### 5. Print out the names of all countries and the number of airports in each country. Order the results by the airport count in descending order. Only include the top 50 countries with the largest number of airports <br>
select country.name, count(*)
from airport, country
where airport.iso_country = country.iso_country
group by country.iso_country
order by count(*) desc
limit 50;

![5](https://github.com/user-attachments/assets/b45f449b-0cda-4a63-a6a4-7e2425a30f6d)

### 6. List the countries with more than 1000 airports. Use the iso_country field in the query. <br>
select country.name
from airport, country
where airport.iso_country = country.iso_country
group by country.iso_country
having count(*) > 1000;

![6](https://github.com/user-attachments/assets/2dcc0a0f-b304-4daf-8f45-40acbd478928)

### 7. Print out the name of the highest airport in the world. <br>
select name
from airport
where elevation_ft in (
select max(elevation_ft)
from airport
);
![7](https://github.com/user-attachments/assets/ecf2105e-e697-4a70-a1cf-abd182d6ff30)

### 8. In which country does the highest airport reside in? <br>
select name
from country
where iso_country in (
select iso_country
from airport
where elevation_ft in(
select max(elevation_ft)
from airport
)
);
![8](https://github.com/user-attachments/assets/ad75abc4-8baa-4b0c-b2ab-33cfe0050551)

### 9. How many weather goals has Vesa achieved so far? <br>
select count(*)
from game, goal_reached
where id = game_id and screen_name = "Vesa"
group by screen_name;
![9](https://github.com/user-attachments/assets/66cb267c-e61a-43b7-aec2-158c88523270)

### 10. What is the name of the airport that resides closest to the polar regions? <br>
select name
from airport
where latitude_deg in(
select min(latitude_deg)
from airport
);
![10](https://github.com/user-attachments/assets/48d7781d-8c92-42cc-bd28-d51cd6958f99)
