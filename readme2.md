PATH: C:\\xampp\\mysql\\bin\\mysql.exe -u root -p -P 8889
PSW: PREMERE INVIO E BASTA

OPPURE 
PATH: C:\\xampp\\mysql\\bin\\mysql.exe -u root -P 8889


## task n.1 "Selezionare tutti gli studenti nati nel 1990 (160)"

-SHOW databases;
-USE `91_university`;
-SHOW tables;
-DESCRIBE `students`;
-SELECT * FROM students WHERE YEAR(date_of_birth) = 1990;

## task n.2 "Selezionare tutti i corsi che valgono più di 10 crediti (479)"

-SHOW databases;
-USE `91_university`;
-SHOW tables;
-DESCRIBE `courses`;
-SELECT `cfu` FROM `courses` WHERE `cfu` > 10;