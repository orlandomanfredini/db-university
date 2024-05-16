Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SELECT * FROM `students` INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
SELECT * FROM 'departements' INNER JOIN `degrees` ON `departement`.`id` = `degrees`.`departement_id`
WHERE `departements`.`name` = 'Dipartimento di Neuroscienze' AND `degrees`.`level` = 'magistrale'

Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
