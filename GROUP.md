Contare quanti iscritti ci sono stati ogni anno
SELECT COUNT(*), YEAR(`enrolment_date`) `year` FROM `students` WHERE YEAR(`enrolment_date`) GROUP BY YEAR(`enrolment_date`);

Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT COUNT(*) `numero_insegnanti`, `office_address` `indirizzo_ufficio` FROM `teachers` GROUP BY `office_address`;

Calcolare la media dei voti di ogni appello d'esame
SELECT COUNT(`exam_id`) `numero_appelli`, AVG(`vote`) `vote`
FROM `exam_student`
INNER JOIN `exams`
ON `exam_student`.`exam_id`= `exams`.`id`
GROUP BY `exam_id`;

Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT COUNT(*) `tot_corsi`, `department_id` FROM `degrees` GROUP BY `department_id`;