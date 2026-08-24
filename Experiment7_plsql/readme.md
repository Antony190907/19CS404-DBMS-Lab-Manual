# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.
### Code:
~~~
DECLARE
   num1 NUMBER := 25;   
   num2 NUMBER := 80;   
   greatest NUMBER;
BEGIN
   IF num1 > num2 THEN
      greatest := num1;
   ELSE
      greatest := num2;
   END IF;

   DBMS_OUTPUT.PUT_LINE('The greatest number is: ' || greatest);
END;
~~~


**Output:**  
<img width="305" height="97" alt="image" src="https://github.com/user-attachments/assets/ab88c2f4-1f5b-482f-bae0-b78a1bd53531" />
**Expected output**
The greatest number is: 80

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.
### Code:
~~~
DECLARE
   n NUMBER := 10;       
   sum NUMBER := 0;      
   i NUMBER;            
BEGIN
   FOR i IN 1..n LOOP
      sum := sum + i;
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
~~~
**Output:**  
<img width="291" height="106" alt="image" src="https://github.com/user-attachments/assets/8427bf83-9485-4c44-8d08-bca6fbd490ed" />
**Expected output:**
Sum of first 10 natural numbers is: 55

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
### Code:
~~~
DECLARE
   n NUMBER := 7;        
   a NUMBER := 0;      
   b NUMBER := 1;         
   c NUMBER;              
   i NUMBER;              
BEGIN
   DBMS_OUTPUT.PUT_LINE('Fibonacci Series up to ' || n || ' terms:');
   
   DBMS_OUTPUT.PUT_LINE(a);  
   DBMS_OUTPUT.PUT_LINE(b);  

   FOR i IN 3..n LOOP
      c := a + b;
      DBMS_OUTPUT.PUT_LINE(c);
      a := b;
      b := c;
   END LOOP;
END;
/
~~~


## Output:
<img width="232" height="139" alt="image" src="https://github.com/user-attachments/assets/8e78500d-3ee8-405b-903b-f2dcba6ac044" />

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.
### Code:
~~~
DECLARE
   n NUMBER := 1535;       
   rev NUMBER := 0;        
   digit NUMBER;         
BEGIN
   WHILE n > 0 LOOP
      digit := MOD(n, 10);          
      rev := (rev * 10) + digit;    
      n := TRUNC(n / 10);           
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('Reversed number is ' || rev);
END;
/
~~~
**Output:**
<img width="290" height="90" alt="image" src="https://github.com/user-attachments/assets/7935bf69-7920-490d-badf-88d97282eb44" />


**Expected Output:**  
n = 1535  
Reversed number is 5351

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

### Code:
~~~
DECLARE
   a NUMBER := 25;  
   b NUMBER := 40;  
   c NUMBER := 35;   
   largest NUMBER;
BEGIN
   IF a >= b AND a >= c THEN
      largest := a;
   ELSIF b >= a AND b >= c THEN
      largest := b;
   ELSE
      largest := c;
   END IF;

   DBMS_OUTPUT.PUT_LINE('The largest number is: ' || largest);
END;
/
~~~
**Output:**
<img width="306" height="86" alt="image" src="https://github.com/user-attachments/assets/2192cc06-8d84-4911-86b0-b76666c5212f" />


**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
