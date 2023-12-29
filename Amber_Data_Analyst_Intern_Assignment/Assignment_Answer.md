### All queries as per MySQL DBMS software

1. SELECT NAME,
     CASE WHEN DEPARTMENT_ID IS NOT NULL DEPARTMENT_ID ELSE "UNASSIGNED"
   END AS DEPARTMENT_NAME FROM EMPLOYEE;
   
2. SELECT DEPARTMENT_ID, COUNT(DISTINCT EMPLOYEE_ID) AS NUMBER_OF_EMPLOYEES FROM EMPLOYEE
   GROUP BY  DEPARTMENT_ID;
   
3. SELECT E.DEPARTMENT_ID FROM EMPLOYEE AS E
   WHERE AVG(S.SALARY) > (SELECT S.SALARY FROM SALARY AS S WHERE S.SALARY > 5500.00)
   GROUP BY E.DEPARTMENT_ID;
   
4. SELECT NAME, HIRE_DATE FROM EMPLOYEE
   WHERE HIRE_DATE > '2022-03-01';

5. SELECT E.EMPLOYEE_ID, E.NAME, S.EFFECTIVE_DATE, S.SALARY, AVG(S.SALARY), (S.SALARY - AVG(S.SALARY)) AS SALARY_DIFFERENCE FROM EMPLOYEE AS E
   INNER JOIN SALARY AS S
   ON S.EMPLOYEE_ID = E.EMPLOYEE_ID
   GROUP BY E.EMPLOYEE_ID;