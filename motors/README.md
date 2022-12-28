# Motors Sql Query practice 


<details><summary>Question 1 : How would you fetch details of the customers who cancelled orders?</summary>
  
  ## QUERY : 
``` 
        SELECT customers.customer_id, customers.customer_name, customers.phone, orders.status FROM customers
        INNER JOIN orders ON orders.customer_id=customers.customer_id
        WHERE orders.status='cancelled';

```

## RESULT 
```
+-------------+-------------------------+----------------+-----------+
| customer_id | customer_name           | phone          | status    |
+-------------+-------------------------+----------------+-----------+
|         448 | Scandinavian Gift Ideas | 0695-34 6555   | Cancelled |
|         496 | Kelly's Gift Shop       | +64 9 5555500  | Cancelled |
|         131 | Land of Toys Inc.       | 2125557818     | Cancelled |
|         201 | UK Collectables, Ltd.   | (171) 555-2282 | Cancelled |
|         357 | GiftsForHim.com         | 64-9-3763555   | Cancelled |
|         141 | Euro+ Shopping Channel  | (91) 555 94 44 | Cancelled |
+-------------+-------------------------+----------------+-----------+
6 rows in set (0.00 sec)

```
</details>



<details><summary>Question 2 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 3 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 4 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 5 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 6 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 7 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 8 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 9 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 10 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 11 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 12 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 13 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 14 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 15 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 16 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 17 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 18 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 19 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 20 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>




<details><summary>Question 21 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>





<details><summary>Question 22 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>





<details><summary>Question 23 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>





<details><summary>Question 24 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>





<details><summary>Question 25 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>





<details><summary>Question 26 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>





<details><summary>Question 27 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>





<details><summary>Question 28 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>





<details><summary>Question 29 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>





<details><summary>Question 30 : </summary>
  
  ## QUERY : 
``` 

```

## RESULT 
```

```
</details>


