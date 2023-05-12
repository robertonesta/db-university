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

## task n.3 "Selezionare tutti gli studenti che hanno più di 30 anni"

-SHOW databases;
-USE `91_university`;
-SHOW tables;
-SELECT * FROM `students` WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) > 30;

## task n.4 "Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)"

-SHOW databases;
-USE `91_university`;
-SHOW tables;
-SELECT * from `courses`;
-SELECT * from `courses` WHERE PERIOD = 'I semestre' AND YEAR = '1';

## task n.5 "Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)"

-SHOW databases;
-USE `91_university`;
-SHOW tables;
-SELECT * FROM `exams`;
-SELECT * FROM `exams` WHERE DATE = "2020-06-20" AND HOUR >= "14:00";

## task n.6 "Selezionare tutti i corsi di laurea magistrale (38)"

-SHOW databases;
-USE `91_university`;
-SHOW tables;
-SELECT * from `degrees`;
-SELECT * from `degrees` WHERE `LEVEL` = "MAGISTRALE";

## task n.7 "Da quanti dipartimenti è composta l'università? (12)"

-SHOW databases;
-USE `91_university`;
-SHOW tables;
-DESCRIBE `departments`;
-SELECT `ID` FROM `departments`;

## task n.8 "Quanti sono gli insegnanti che non hanno un numero di telefono? (50)"

-SHOW databases;
-USE `91_university`;
-SHOW tables;
-DESCRIBE `teachers`;
-SELECT COUNT(*) FROM `teachers` WHERE phone IS NULL;