# Week 03

## Exercise 02
### 1. Write a query that prints out all the columns in the goal table. The output should look as follows: <br>
select*from goal; 

![image](https://github.com/user-attachments/assets/b7b29066-e29e-458d-9617-dd5cf319a74b)


### 2. Write a query that prints out the name and type of each airport in Finland. The country code for Finland is: FI. Expected output: <br>
select name, type from airport where iso_country = "FI";

![2-2](https://github.com/user-attachments/assets/1579d78b-6f0c-46c8-aa9f-c1935bc5d074)

### 3. Write a query that prints out the names of all Finnish airports in alphabetical order. The country code for Finland is: FI. The output should look as follows (Note that the image has been cropped to fit the screen): <br>
SELECT name FROM airport WHERE iso_country = 'FI' ORDER BY name ASC;

![2-3](https://github.com/user-attachments/assets/e68e3325-bb3b-459a-9796-8cbe24dfaf14)

### 4. Write a query that prints out the name and type of each Finnish airport. Order the result first by type and secondly by name. The output should be as follows: <br>
select name, type from airport where iso_country = 'FI' order by type, name;

![2-4](https://github.com/user-attachments/assets/51964c54-9dfd-4cb3-bb7f-87a081faf784)

### 5. Write a query that prints out the names of all countries that start with the letter F from the country table. The output should look as follows: <br>
select name from country where name like 'F%';

![2-5](https://github.com/user-attachments/assets/70b639a9-764a-4d61-8002-62b61f5446dd)

### 6. Write a query that prints out all country names in the country table that include the letter F. The output should be as follows: <br>
select name from country where name like "%F%";

![2-6](https://github.com/user-attachments/assets/05c5a7d1-8077-4c1c-98c1-48ae163975d1)

### 7. What is Vesa's current location? The output should be as follows: <br>
select location from game where screen_name = "Vesa";

![2-7](https://github.com/user-attachments/assets/bbcf7504-3e81-4a77-9140-0d3aacce68ca)

### 8. How much of his CO2 budget has Ilkka consumed? The output should look as follows: <br>
select co2_consumed from game where screen_name = "Ilkka";

![2-8](https://github.com/user-attachments/assets/3af8541f-f6b7-4b11-a2e3-34d588dffda7)

### 9. What is the original CO2 budget? Print out the CO2 budget value only once. The output should be as follows: <br>
SELECT DISTINCT co2_budget FROM game;

![2-9](https://github.com/user-attachments/assets/f1d48517-9730-46d3-b9fe-a5e369e22112)

### 10. How much of his CO2 budget does Ilkka have left? Complete the query so that the result includes the following fields: screen_name, co2_budget, co2_consumed and co2_left. <br>
select screen_name, co2_budget, co2_consumed, co2_budget - co2_consumed as co2_left from game;

![2-10](https://github.com/user-attachments/assets/01616a33-6cb8-4805-89a9-a3937e918480)







