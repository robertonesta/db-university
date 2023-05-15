PATH: C:\\xampp\\mysql\\bin\\mysql.exe -u root -P 8889

EX - QUERY CON GROUP BY

## 1. Contare quanti iscritti ci sono stati ogni anno

SELECT COUNT(`students`.`id`), YEAR(`students`.`enrolment_date`)
FROM `students`
GROUP BY YEAR(`students`.`enrolment_date`)

## 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT COUNT(`teachers`.`id`), `teachers`.`office_address`
FROM `teachers`
GROUP BY `teachers`.`office_address`

## 3. Calcolare la media dei voti di ogni appello d'esame

SELECT AVG(`exam_student`.`vote`), `exam_student`.`exam_id`
FROM `exam_student`
GROUP BY `exam_student`.`exam_id`

## 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT COUNT(`degrees`.`id`), `departments`.`name`
FROM `degrees`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
GROUP BY `degrees`.`department_id``