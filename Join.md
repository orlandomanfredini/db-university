Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SELECT * FROM `students` INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
SELECT * FROM 'departements' INNER JOIN `degrees` ON `departement`.`id` = `degrees`.`departement_id`
WHERE `departements`.`name` = 'Dipartimento di Neuroscienze' AND `degrees`.`level` = 'magistrale'

Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
SELECT * , `courses`.`name` `nome_corso` FROM `teachers` INNER JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id` INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id` WHERE `teachers`.`id` = 44;

Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
nome
SELECT * FROM `students` INNER JOIN `degrees` ON `students`.`degree_id`= `degrees`.`id` INNER JOIN `departments` ON `degrees`.`department_id` = `departments`.`id` ORDER BY `students`.`name` ASC;

Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
SELECT * FROM `degrees` INNER JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id` INNER JOIN `course_teacher` ON `courses`.`id`= `course_teacher`.`course_id`;

 Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54)
SELECT DISTINCT * 
FROM `departments`
INNER JOIN `degrees`
ON `departments`.`id` = `degrees`.`department_id`
INNER JOIN `courses`
ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`
WHERE `departments`.`name` = 'Dipartimento di Matematica';

<!-- CORRETTO -->
SELECT DISTINCT `teachers`.`name`, `teachers`.`id` `id_prof`, `departments`.`id`, `departments`.`name` FROM `teachers` INNER JOIN `course_teacher` ON `teachers`.`id`=`course_teacher`.`teacher_id` INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id` INNER JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id` INNER JOIN `departments` ON `degrees`.`department_id` = `departments`.`id` WHERE `departments`.`name` = "Dipartimento di Matematica";