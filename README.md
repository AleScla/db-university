1. Selezionare tutti gli studenti nati nel 1990 (160)
SELECT * 
FROM `students`
WHERE YEAR(date_of_birth) = 1990;
--

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)
SELECT * 
FROM `courses`
WHERE cfu > 10;
--

3. Selezionare tutti gli studenti che hanno più di 30 anni (2694)
SELECT * 
FROM `students`
WHERE YEAR(date_of_birth) < 1994
AND MONTH(date_of_birth) < 10;
--

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
laurea (286)
SELECT * 
FROM `courses` 
WHERE period = 'I semestre' 
AND year = 1;
--

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 (21)
SELECT * FROM `exams`
WHERE hour(hour) >= 14
AND date = '2020/06/20';
--

6. Selezionare tutti i corsi di laurea magistrale (38)
SELECT * 
FROM `degrees` 
WHERE level = 'magistrale';
-- 


7. Da quanti dipartimenti è composta l'università? (12)
SELECT COUNT(*) AS departments_number 
FROM `departments`;
--

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
SELECT COUNT(*) 
AS no_numb_teachers 
FROM `teachers` 
WHERE phone IS NULL;
--

9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo
degree_id, inserire un valore casuale)
INSERT INTO `students` (`id`, `degree_id`, `name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`, `email`) 
VALUES (NULL, '11', 'Alessandro', 'Sclafani', '1997-07-31', 'ABCCBE97B31I5555S', '2024-10-06', '555555', 'aleale@ale.ale');

--

10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126
UPDATE teachers
SET office_number = 126 
WHERE name = 'Pietro'
AND surname = 'Rizzo';
--


11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9

DELETE FROM `students` 
WHERE name = 'Alessandro' 
AND surname = 'Sclafani';
--