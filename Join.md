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