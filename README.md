2.1.     Bütün işçilərin adlarını(first_name) və soyadlarını(last_name) seçin:
SELECT first_name, last_name 
FROM employees;


2.2.    İşçilərdən maaşı(salary) 10000-dən çox olanların e-poçt(email) ünvanlarını seçin:
SELECT email 
FROM employees 
WHERE salary > 10000;


2.3.   Maaşı(salary) 5000 və 10000 arasında olan və ya meneceri(manager_id) 101 nömrəli olan işçiləri tapın:
SELECT * 
FROM employees 
WHERE (salary BETWEEN 5000 AND 10000) OR manager_id = 101;


2.4.    Adında (first_name) 'a' hərfi olan və ya soyadında (last_name) 'e' hərfi olan işçiləri tapın:
SELECT * 
FROM employees 
WHERE first_name LIKE '%a%' OR last_name LIKE '%e%';


2.5.    Vəzifəsi (job_id) 'IT_PROG' olan və maaşı (salary) 6000-dən çox olan işçiləri tapın:
SELECT * 
FROM employees 
WHERE job_id = 'IT_PROG' AND salary > 6000;


2.6.    Adında (first_name)  'e' hərfi olan işçiləri tapın
SELECT * 
FROM employees 
WHERE first_name LIKE '%e%';


2.7.    E-poçtu (email) 'gmail.com' domaini ilə bitən işçiləri tapın:
SELECT * 
FROM employees 
WHERE email LIKE '%gmail.com';


2.8.        Soyadında (last_name) 'son' ifadəsi olan işçiləri tapın:
SELECT * 
FROM employees 
WHERE last_name LIKE '%son%';


2.9.          Maaşı (salary) 4000 və 8000 arasında olan işçiləri tapın:
SELECT * 
FROM employees 
WHERE salary BETWEEN 4000 AND 8000;


2.10.            Departament id-si (department_id) 20 və 100 arasında olan işçiləri tapın
SELECT * 
FROM employees 
WHERE department_id BETWEEN 20 AND 100;


2.11.           Bütün işçiləri maaşa (salary) görə azalan sıra ilə sıralayın:
SELECT * 
FROM employees 
ORDER BY salary DESC;


2.12.           Bütün işçiləri soyadlarına (last_name) görə artan sıra ilə sıralayın:
SELECT * 
FROM employees 
ORDER BY last_name ASC;


2.13.           Bütün işçiləri işəgötürəlmə tarixinə (hire_date) görə azalan sıra ilə sıralayın:
SELECT * 
FROM employees 
ORDER BY hire_date DESC;


2.14.           Bütün müxtəlif departament id-lərini tapın:
SELECT DISTINCT department_id 
FROM employees;


2.15.           5 yeni bir işçi əlavə edin:
INSERT INTO employees (employee_id, first_name, last_name, email,phone_number, hire_date, job_id, salary, commission_pct, manager_id, department_id) 
VALUES 
(319, 'Ali', 'Veliyev', 'ali.veliyev@example.com','515.123.8182','2025-01-01', 'IT_PROG', 6000,0, 103, 50),
(318, 'Aysel', 'Mammadova', 'aysel.mammadova@example.com','515.321.7128','2025-01-01', 'HR_REP', 4500,0, 101, 60);


2.16.           Bütün IT proqramçılarının (IT_PROG) maaşını 200 artırın:  
UPDATE employees 
SET salary = salary + 200 
WHERE job_id = 'IT_PROG';

1.1. Map funksiyası ilə string əməliyyatları:
Verilmiş listdəki bütün sözləri böyük hərflərlə çap edən funksiya:
def words_to_uppercase(words):
    return list(map(str.upper, words))
words = ["salam", "dünya", "python", "kod"]
print(words_to_uppercase(words))

1.2. List Comprehensions ilə ədədlərin qüvvətə yüksəldilməsi:
Verilmiş listdəki bütün ədədləri öz qüvvətinə yüksəldən funksiya:

def power_numbers(nums):
    return [num ** num for num in nums]
numbers = [2, 3, 4]
print(power_numbers(numbers))

1.3. Map və filter ilə ədədlərin seçilməsi:
Bir listdəki cüt ədədləri seçin və onların kvadratını hesablayın:

def square_even_numbers(nums):
    return list(map(lambda x: x ** 2, filter(lambda x: x % 2 == 0, nums)))
numbers = [1, 2, 3, 4, 5, 6]
print(square_even_numbers(numbers))

1.4. Lambda funksiyaları:
İki ədədin cəmini hesablayan və çap edən lambda funksiyası:

sum_two_numbers = lambda x, y: x + y
print(sum_two_numbers(5, 7))

1.5. Filter və lambda ilə ədədlərin seçilməsi:
Verilmiş bir listdəki müsbət ədədləri seçən və nəticəni yeni bir listə yığan kod:

def filter_positive_numbers(nums):
    return list(filter(lambda x: x > 0, nums))
numbers = [-3, 5, -1, 0, 9, -8]
print(filter_positive_numbers(numbers))
