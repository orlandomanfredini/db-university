Contare quanti iscritti ci sono stati ogni anno
SELECT COUNT(*), YEAR(`enrolment_date`) `year` FROM `students` WHERE YEAR(`enrolment_date`) GROUP BY YEAR(`enrolment_date`);