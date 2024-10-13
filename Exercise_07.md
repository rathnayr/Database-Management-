# Week 5
## Exercise 07
### 1. Vesa flies from his current location to the Nottingham Airport. At the same time, Vesa's carbon footprint increases by 500. Update the information to the database. <br>
UPDATE game SET location = (SELECT ident FROM airport WHERE name = "Nottingham Airport"), co2_consumed = co2_consumed + 500 WHERE screen_name = "Vesa";

![7-1](https://github.com/user-attachments/assets/964c5fca-8f07-4040-8496-324dc34a0d74)

### 2. Prepare your own database for the project by deleting all dummy data relating to the game state. To maintain referential integrity, you have to delete the data in a specific order. Do you have to delete data first from the game table or from the goal_reached table? <br>

![7-2](https://github.com/user-attachments/assets/87d50189-26ff-4153-9e4e-650c59e7b595)

### 3. Delete the dummy data from the goal_reached table. <br>

![7-3](https://github.com/user-attachments/assets/daef07f5-6b11-4fe1-aa71-4dd5c1d89c3c)

### 4. Delete the data from the game table. <br>

![7-4](https://github.com/user-attachments/assets/dfa6d4d2-9068-4521-97d2-a788654dc992)

