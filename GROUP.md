Contare quanti iscritti ci sono stati ogni anno
SELECT COUNT(*), YEAR(`enrolment_date`) `year` FROM `students` WHERE YEAR(`enrolment_date`) GROUP BY YEAR(`enrolment_date`);

Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT COUNT(*) `numero_insegnanti`, `office_address` `indirizzo_ufficio` FROM `teachers` GROUP BY `office_address`;