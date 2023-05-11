<!--Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.-->

# Database University;

## Data types:
- strings: [varchar(number), char(number), text, longtext]
- numbers: [tinyint, smallint, mediumint, int, bigint]
- decimals: [float(i,d), double(i,d), decimal(i,d)]
- dates: [datetime, date, time, year, timestamp]

## Attributes:
- NULL / NOT NULL
- DEFAULT(value)
- PRIMARY_KEY
- AUTO_INCREMENT
- UNIQUE

## Entity name: Department
## Table name: Departments

## Table Columns: Departments

-id | AUTO_INCREMENT, NOTNULL, PRIMARY_KEY, UNIQUE, INDEX, BIGINT
-name | VARCHAR(100), NOTNULL
-address| VARCHAR(150), NULL
-fee| DECIMAL(7,2) 
-type| DEFAULT(PUBLIC)


## Courses
-id| AUTO_INCREMENT, NOTNULL, PRIMARY_KEY, UNIQUE, INDEX, BIGINT
-departments_id| NOTNULL, FOREIGN_KEY, UNIQUE, INDEX, BIGINT
-name| VARCHAR(97), NOTNULL
-type| VARCHAR(48), NULL
-level| VARCHAR(10), NULL


## subjects
-id| AUTO_INCREMENT, NOTNULL, PRIMARY_KEY, UNIQUE, INDEX, BIGINT
-courses_id | NOTNULL, FOREIGN_KEY, UNIQUE, INDEX, BIGINT
-name| VARCHAR(50), NOTNULL
-credits| TINYINT, NOTNULL


## teachers
-id| AUTO_INCREMENT, NOTNULL, PRIMARY_KEY, UNIQUE, INDEX, BIGINT
-subjects_id|  NOTNULL, FOREIGN_KEY, UNIQUE, INDEX, BIGINT
-name| VARCHAR(22), NOTNULL
-lastname| VARCHAR(23), NOTNULL
-email| VARCHAR(40), NULL
-phone_number| CHAR(10) NULL
-note| TEXT, NULL

## exam
-id| AUTO_INCREMENT, NOTNULL, PRIMARY_KEY, UNIQUE, INDEX, BIGINT
-subject_id| NOTNULL, FOREIGN_KEY, INDEX, BIGINT
-student_id| NOTNULL, FOREIGN_KEY, INDEX, BIGINT
-date| DATETIME
-outcome| VARCHAR(10), NOTNULL
-vote| TINYINT, NOTNULL

## students
-id| AUTO_INCREMENT, NOTNULL, PRIMARY_KEY, UNIQUE, INDEX, BIGINT
-id_courses | INDEX, UNIQUE, NOTNULL
-badge_number: VARCHAR(10), NOTNULL
-name| VARCHAR(22), NOTNULL
-lastname| VARCHAR(23), NOTNULL
-email| VARCHAR(40), NULL
-phone_number| CHAR(10) NULL

## vote
-exam_id| FOREIGN KEY, NULL
-student_id | NOTNULL, FOREIGN_KEY, INDEX, BIGINT
