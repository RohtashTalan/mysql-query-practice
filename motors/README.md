# Motors Sql Query practice 


<details><summary>Question 1 : How would you fetch details of the customers who cancelled orders?</summary>
  
  ## QUERY : 
``` 
        SELECT *, orders.status FROM customers
        INNER JOIN orders ON orders.customer_id=customers.customer_id
        WHERE orders.status='cancelled';


        ----
        SELECT * FROM customers
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



<details><summary>Question 2 : Fetch the details of customers who have done payments between the amount 5,000 and 35,000 ?</summary>
  
  ## QUERY : 
``` 

        SELECT * FROM customers
        INNER JOIN payments ON payments.customer_id=customers.customer_id
        WHERE payments.amount BETWEEN 5000 AND 35000;

```

## RESULT 
```
+-------------+------------------------------------+-------------+------------+--------------------+-------------------------------+-----------------------+----------------+---------------+-------------+-------------+-------------------+--------------+-------------+--------------+--------------+----------+
| customer_id | customer_name                      | last_name   | first_name | phone              | address_line1                 | address_line2         | city           | state         | postal_code | country     | sales_employee_id | credit_limit | customer_id | check_number | payment_date | amount   |
+-------------+------------------------------------+-------------+------------+--------------------+-------------------------------+-----------------------+----------------+---------------+-------------+-------------+-------------------+--------------+-------------+--------------+--------------+----------+
|         103 | Atelier graphique                  | Schmitt     | Carine     | 40.32.2555         | 54, rue Royale                | NULL                  | Nantes         | NULL          | 44000       | France      |              1370 |     21000.00 |         103 | HQ336336     | 2018-10-19   |  6066.78 |
|         103 | Atelier graphique                  | Schmitt     | Carine     | 40.32.2555         | 54, rue Royale                | NULL                  | Nantes         | NULL          | 44000       | France      |              1370 |     21000.00 |         103 | JM555205     | 2017-06-05   | 14571.44 |
|         112 | Signal Gift Stores                 | King        | Jean       | 7025551838         | 8489 Strong St.               | NULL                  | Las Vegas      | NV            | 83030       | USA         |              1166 |     71800.00 |         112 | BO864823     | 2018-12-17   | 14191.12 |
|         112 | Signal Gift Stores                 | King        | Jean       | 7025551838         | 8489 Strong St.               | NULL                  | Las Vegas      | NV            | 83030       | USA         |              1166 |     71800.00 |         112 | HQ55022      | 2017-06-06   | 32641.98 |
|         112 | Signal Gift Stores                 | King        | Jean       | 7025551838         | 8489 Strong St.               | NULL                  | Las Vegas      | NV            | 83030       | USA         |              1166 |     71800.00 |         112 | ND748579     | 2018-08-20   | 33347.88 |
|         114 | Australian Collectors, Co.         | Ferguson    | Peter      | 03 9520 4555       | 636 St Kilda Road             | Level 3               | Melbourne      | Victoria      | 3004        | Australia   |              1611 |    117300.00 |         114 | NP603840     | 2017-05-31   |  7565.08 |
|         119 | La Rochelle Gifts                  | Labrune     | Janine     | 40.67.8555         | 67, rue des Cinquante Otages  | NULL                  | Nantes         | NULL          | 44000       | France      |              1370 |    118200.00 |         119 | DB933704     | 2018-11-14   | 19501.82 |
|         121 | Baane Mini Imports                 | Bergulfsen  | Jonas      | 07-98 9555         | Erling Skakkes gate 78        | NULL                  | Stavern        | NULL          | 4110        | Norway      |              1504 |     81700.00 |         121 | KI831359     | 2018-11-04   | 17876.32 |
|         121 | Baane Mini Imports                 | Bergulfsen  | Jonas      | 07-98 9555         | Erling Skakkes gate 78        | NULL                  | Stavern        | NULL          | 4110        | Norway      |              1504 |     81700.00 |         121 | MA302151     | 2018-11-28   | 34638.14 |
|         124 | Mini Gifts Distributors Ltd.       | Nelson      | Susan      | 4155551450         | 5677 Strong St.               | NULL                  | San Rafael     | CA            | 97562       | USA         |              1165 |    210500.00 |         124 | CQ287967     | 2017-04-11   | 11044.30 |
|         128 | Blauer See Auto, Co.               | Keitel      | Roland     | +49 69 66 90 2555  | Lyonerstr. 34                 | NULL                  | Frankfurt      | NULL          | 60528       | Germany     |              1504 |     59700.00 |         128 | DI925118     | 2017-01-28   | 10549.01 |
|         128 | Blauer See Auto, Co.               | Keitel      | Roland     | +49 69 66 90 2555  | Lyonerstr. 34                 | NULL                  | Frankfurt      | NULL          | 60528       | Germany     |              1504 |     59700.00 |         128 | FA465482     | 2017-10-18   | 24101.81 |
|         128 | Blauer See Auto, Co.               | Keitel      | Roland     | +49 69 66 90 2555  | Lyonerstr. 34                 | NULL                  | Frankfurt      | NULL          | 60528       | Germany     |              1504 |     59700.00 |         128 | FH668230     | 2018-03-24   | 33820.62 |
|         128 | Blauer See Auto, Co.               | Keitel      | Roland     | +49 69 66 90 2555  | Lyonerstr. 34                 | NULL                  | Frankfurt      | NULL          | 60528       | Germany     |              1504 |     59700.00 |         128 | IP383901     | 2018-11-18   |  7466.32 |
|         129 | Mini Wheels Co.                    | Murphy      | Julie      | 6505555787         | 5557 North Pendale Street     | NULL                  | San Francisco  | CA            | 94217       | USA         |              1165 |     64600.00 |         129 | DM826140     | 2018-12-08   | 26248.78 |
|         129 | Mini Wheels Co.                    | Murphy      | Julie      | 6505555787         | 5557 North Pendale Street     | NULL                  | San Francisco  | CA            | 94217       | USA         |              1165 |     64600.00 |         129 | ID449593     | 2017-12-11   | 23923.93 |
|         129 | Mini Wheels Co.                    | Murphy      | Julie      | 6505555787         | 5557 North Pendale Street     | NULL                  | San Francisco  | CA            | 94217       | USA         |              1165 |     64600.00 |         129 | PI42991      | 2017-04-09   | 16537.85 |
|         131 | Land of Toys Inc.                  | Lee         | Kwai       | 2125557818         | 897 Long Airport Avenue       | NULL                  | NYC            | NY            | 10022       | USA         |              1323 |    114900.00 |         131 | CL442705     | 2017-03-12   | 22292.62 |
|         141 | Euro+ Shopping Channel             | Freyre      | Diego      | (91) 555 94 44     | C/ Moralzarzal, 86            | NULL                  | Madrid         | NULL          | 28034       | Spain       |              1370 |    227600.00 |         141 | MF629602     | 2018-08-16   | 20009.53 |
|         141 | Euro+ Shopping Channel             | Freyre      | Diego      | (91) 555 94 44     | C/ Moralzarzal, 86            | NULL                  | Madrid         | NULL          | 28034       | Spain       |              1370 |    227600.00 |         141 | NU627706     | 2018-05-17   | 26155.91 |
|         144 | Volvo Model Replicas, Co           | Berglund    | Christina  | 0921-12 3555       | Berguvsvägen  8               | NULL                  | Luleå          | NULL          | S-958 22    | Sweden      |              1504 |     53100.00 |         144 | LA685678     | 2017-04-09   |  7674.94 |
|         145 | Danish Wholesale Imports           | Petersen    | Jytte      | 31 12 3555         | Vinbæltet 34                  | NULL                  | Kobenhavn      | NULL          | 1734        | Denmark     |              1401 |     83400.00 |         145 | ED39322      | 2018-04-26   | 28211.70 |
|         145 | Danish Wholesale Imports           | Petersen    | Jytte      | 31 12 3555         | Vinbæltet 34                  | NULL                  | Kobenhavn      | NULL          | 1734        | Denmark     |              1401 |     83400.00 |         145 | HR182688     | 2018-12-01   | 20564.86 |
|         151 | Muscle Machine Inc                 | Young       | Jeff       | 2125557413         | 4092 Furth Circle             | Suite 400             | NYC            | NY            | 10022       | USA         |              1286 |    138500.00 |         151 | GB852215     | 2018-07-26   | 20314.44 |
|         161 | Technics Stores Inc.               | Hashimoto   | Juri       | 6505556809         | 9408 Furth Circle             | NULL                  | Burlingame     | CA            | 94217       | USA         |              1165 |     84600.00 |         161 | KG644125     | 2019-02-02   | 12692.19 |
|         166 | Handji Gifts& Co                   | Victorino   | Wendy      | +65 224 1555       | 106 Linden Road Sandown       | 2nd Floor             | Singapore      | NULL          | 069045      | Singapore   |              1612 |     97900.00 |         166 | LA318629     | 2018-02-28   | 22474.17 |
|         167 | Herkku Gifts                       | Oeztan      | Veysel     | +47 2267 3215      | Brehmen St. 121               | PR 334 Sentrum        | Bergen         | NULL          | N 5804      | Norway      |              1504 |     96800.00 |         167 | ED743615     | 2018-09-19   | 12538.01 |
|         171 | Daedalus Designs Imports           | Rancé       | Martine    | 20.16.1555         | 184, chaussée de Tournai      | NULL                  | Lille          | NULL          | 59000       | France      |              1370 |     82900.00 |         171 | GB878038     | 2018-03-15   | 18997.89 |
|         172 | La Corne D'abondance, Co.          | Bertrand    | Marie      | (1) 42.34.2555     | 265, boulevard Charonne       | NULL                  | Paris          | NULL          | 75012       | France      |              1337 |     84300.00 |         172 | EH208589     | 2017-04-20   | 33383.14 |
|         173 | Cambridge Collectables Co.         | Tseng       | Jerry      | 6175555555         | 4658 Baden Av.                | NULL                  | Cambridge      | MA            | 51247       | USA         |              1188 |     43400.00 |         173 | GP545698     | 2018-05-13   | 11843.45 |
|         173 | Cambridge Collectables Co.         | Tseng       | Jerry      | 6175555555         | 4658 Baden Av.                | NULL                  | Cambridge      | MA            | 51247       | USA         |              1188 |     43400.00 |         173 | IG462397     | 2018-03-29   | 20355.24 |
|         175 | Gift Depot Inc.                    | King        | Julie      | 2035552570         | 25593 South Bay Ln.           | NULL                  | Bridgewater    | CT            | 97562       | USA         |              1323 |     84300.00 |         175 | CITI3434344  | 2019-05-19   | 28500.78 |
|         175 | Gift Depot Inc.                    | King        | Julie      | 2035552570         | 25593 South Bay Ln.           | NULL                  | Bridgewater    | CT            | 97562       | USA         |              1323 |     84300.00 |         175 | IO448913     | 2017-11-19   | 24879.08 |
|         177 | Osaka Souveniers Co.               | Kentary     | Mory       | +81 06 6342 5555   | 1-6-20 Dojima                 | NULL                  | Kita-ku        | Osaka         |  530-0003   | Japan       |              1621 |     81200.00 |         177 | AU750837     | 2018-04-17   | 15183.63 |
|         181 | Vitachrome Inc.                    | Frick       | Michael    | 2125551500         | 2678 Kingston Rd.             | Suite 101             | NYC            | NY            | 10022       | USA         |              1286 |     76400.00 |         181 | CM564612     | 2018-04-25   | 22602.36 |
|         181 | Vitachrome Inc.                    | Frick       | Michael    | 2125551500         | 2678 Kingston Rd.             | Suite 101             | NYC            | NY            | 10022       | USA         |              1286 |     76400.00 |         181 | GQ132144     | 2017-01-30   |  5494.78 |
|         186 | Toys of Finland, Co.               | Karttunen   | Matti      | 90-224 8555        | Keskuskatu 45                 | NULL                  | Helsinki       | NULL          | 21240       | Finland     |              1501 |     96500.00 |         186 | AE192287     | 2019-03-10   | 23602.90 |
|         186 | Toys of Finland, Co.               | Karttunen   | Matti      | 90-224 8555        | Keskuskatu 45                 | NULL                  | Helsinki       | NULL          | 21240       | Finland     |              1501 |     96500.00 |         186 | KA602407     | 2018-10-21   | 34341.08 |
|         189 | Clover Collections, Co.            | Cassidy     | Dean       | +353 1862 1555     | 25 Maiden Lane                | Floor No. 4           | Dublin         | NULL          | 2           | Ireland     |              1504 |     69400.00 |         189 | BO711618     | 2018-10-03   | 17359.53 |
|         189 | Clover Collections, Co.            | Cassidy     | Dean       | +353 1862 1555     | 25 Maiden Lane                | Floor No. 4           | Dublin         | NULL          | 2           | Ireland     |              1504 |     69400.00 |         189 | NM916675     | 2018-03-01   | 32538.74 |
|         198 | Auto-Moto Classics Inc.            | Taylor      | Leslie     | 6175558428         | 16780 Pompton St.             | NULL                  | Brickhaven     | MA            | 58339       | USA         |              1216 |     23000.00 |         198 | FI192930     | 2018-12-06   |  9658.74 |
|         198 | Auto-Moto Classics Inc.            | Taylor      | Leslie     | 6175558428         | 16780 Pompton St.             | NULL                  | Brickhaven     | MA            | 58339       | USA         |              1216 |     23000.00 |         198 | HQ920205     | 2017-07-06   |  6036.96 |
|         198 | Auto-Moto Classics Inc.            | Taylor      | Leslie     | 6175558428         | 16780 Pompton St.             | NULL                  | Brickhaven     | MA            | 58339       | USA         |              1216 |     23000.00 |         198 | IS946883     | 2018-09-21   |  5858.56 |
|         201 | UK Collectables, Ltd.              | Devon       | Elizabeth  | (171) 555-2282     | 12, Berkeley Gardens Blvd     | NULL                  | Liverpool      | NULL          | WX1 6LT     | UK          |              1501 |     92700.00 |         201 | DP677013     | 2017-10-20   | 23908.24 |
|         202 | Canadian Gift Exchange Network     | Tamuri      | Yoshi      | (604) 555-3392     | 1900 Oak St.                  | NULL                  | Vancouver      | BC            | V3F 2K1     | Canada      |              1323 |     90300.00 |         202 | IQ627690     | 2018-11-08   | 33594.58 |
|         216 | Enaco Distributors                 | Saavedra    | Eduardo    | (93) 203 4555      | Rambla de Cataluña, 23        | NULL                  | Barcelona      | NULL          | 08022       | Spain       |              1702 |     60300.00 |         216 | ML780814     | 2018-12-06   | 24945.21 |
|         233 | Québec Home Shopping Network       | Fresnière   | Jean       | (514) 555-8054     | 43 rue St. Laurent            | NULL                  | Montréal       | Québec        | H1J 1C3     | Canada      |              1286 |     48700.00 |         233 | BOFA23232    | 2019-05-20   | 29070.38 |
|         233 | Québec Home Shopping Network       | Fresnière   | Jean       | (514) 555-8054     | 43 rue St. Laurent            | NULL                  | Montréal       | Québec        | H1J 1C3     | Canada      |              1286 |     48700.00 |         233 | II180006     | 2018-07-01   | 22997.45 |
|         233 | Québec Home Shopping Network       | Fresnière   | Jean       | (514) 555-8054     | 43 rue St. Laurent            | NULL                  | Montréal       | Québec        | H1J 1C3     | Canada      |              1286 |     48700.00 |         233 | JG981190     | 2017-11-18   | 16909.84 |
|         240 | giftsbymail.co.uk                  | Bennett     | Helen      | (198) 555-8888     | Garden House                  | Crowther Way 23       | Cowes          | Isle of Wight | PO31 7PJ    | UK          |              1501 |     93900.00 |         240 | JO719695     | 2018-03-28   | 24995.61 |
|         242 | Alpha Cognac                       | Roulet      | Annette    | 61.77.6555         | 1 rue Alsace-Lorraine         | NULL                  | Toulouse       | NULL          | 31000       | France      |              1370 |     61100.00 |         242 | AF40894      | 2017-11-22   | 33818.34 |
|         242 | Alpha Cognac                       | Roulet      | Annette    | 61.77.6555         | 1 rue Alsace-Lorraine         | NULL                  | Toulouse       | NULL          | 31000       | France      |              1370 |     61100.00 |         242 | HR224331     | 2019-06-03   | 12432.32 |
|         242 | Alpha Cognac                       | Roulet      | Annette    | 61.77.6555         | 1 rue Alsace-Lorraine         | NULL                  | Toulouse       | NULL          | 31000       | France      |              1370 |     61100.00 |         242 | KI744716     | 2017-07-21   | 14232.70 |
|         249 | Amica Models & Co.                 | Accorti     | Paolo      | 011-4988555        | Via Monte Bianco 34           | NULL                  | Torino         | NULL          | 10100       | Italy       |              1401 |    113000.00 |         249 | IJ399820     | 2018-09-19   | 33924.24 |
|         250 | Lyon Souveniers                    | Da Silva    | Daniel     | +33 1 46 62 7555   | 27 rue du Colonel Pierre Avia | NULL                  | Paris          | NULL          | 75508       | France      |              1337 |     68100.00 |         250 | EQ12267      | 2019-05-17   | 17928.09 |
|         250 | Lyon Souveniers                    | Da Silva    | Daniel     | +33 1 46 62 7555   | 27 rue du Colonel Pierre Avia | NULL                  | Paris          | NULL          | 75508       | France      |              1337 |     68100.00 |         250 | HD284647     | 2018-12-30   | 26311.63 |
|         250 | Lyon Souveniers                    | Da Silva    | Daniel     | +33 1 46 62 7555   | 27 rue du Colonel Pierre Avia | NULL                  | Paris          | NULL          | 75508       | France      |              1337 |     68100.00 |         250 | HN114306     | 2017-07-18   | 23419.47 |
|         256 | Auto Associés & Cie.               | Tonini      | Daniel     | 30.59.8555         | 67, avenue de l'Europe        | NULL                  | Versailles     | NULL          | 78000       | France      |              1370 |     77900.00 |         256 | EP227123     | 2018-02-10   |  5759.42 |
|         259 | Toms Spezialitäten, Ltd            | Pfalzheim   | Henriette  | 0221-5554327       | Mehrheimerstr. 369            | NULL                  | Köln           | NULL          | 50739       | Germany     |              1504 |    120400.00 |         259 | GB361972     | 2017-12-07   | 27988.47 |
|         260 | Royal Canadian Collectables, Ltd.  | Lincoln     | Elizabeth  | (604) 555-4555     | 23 Tsawassen Blvd.            | NULL                  | Tsawassen      | BC            | T2F 8M4     | Canada      |              1323 |     89600.00 |         260 | NH776924     | 2018-04-24   | 29284.42 |
|         276 | Anna's Decorations, Ltd            | O'Hara      | Anna       | 02 9936 8555       | 201 Miller Street             | Level 15              | North Sydney   | NSW           | 2060        | Australia   |              1611 |    107800.00 |         276 | EM979878     | 2019-02-09   | 27083.78 |
|         276 | Anna's Decorations, Ltd            | O'Hara      | Anna       | 02 9936 8555       | 201 Miller Street             | Level 15              | North Sydney   | NSW           | 2060        | Australia   |              1611 |    107800.00 |         276 | OJ819725     | 2019-04-30   | 29848.52 |
|         282 | Souveniers And Things Co.          | Huxley      | Adrian     | +61 2 9495 8555    | Monitor Money Building        | 815 Pacific Hwy       | Chatswood      | NSW           | 2067        | Australia   |              1611 |     93300.00 |         282 | IA793562     | 2017-08-03   | 24013.52 |
|         282 | Souveniers And Things Co.          | Huxley      | Adrian     | +61 2 9495 8555    | Monitor Money Building        | 815 Pacific Hwy       | Chatswood      | NSW           | 2067        | Australia   |              1611 |     93300.00 |         282 | OD327378     | 2019-01-03   | 31835.36 |
|         299 | Norway Gifts By Mail, Co.          | Klaeboe     | Jan        | +47 2212 1555      | Drammensveien 126A            | PB 211 Sentrum        | Oslo           | NULL          | N 0106      | Norway      |              1504 |     95100.00 |         299 | NR157385     | 2018-09-05   | 32260.16 |
|         311 | Oulu Toy Supplies, Inc.            | Koskitalo   | Pirkko     | 981-443655         | Torikatu 38                   | NULL                  | Oulu           | NULL          | 90110       | Finland     |              1501 |     90500.00 |         311 | FA728475     | 2017-10-06   | 32723.04 |
|         311 | Oulu Toy Supplies, Inc.            | Koskitalo   | Pirkko     | 981-443655         | Torikatu 38                   | NULL                  | Oulu           | NULL          | 90110       | Finland     |              1501 |     90500.00 |         311 | NQ966143     | 2018-04-25   | 16212.59 |
|         314 | Petit Auto                         | Dewey       | Catherine  | (02) 5554 67       | Rue Joseph-Bens 532           | NULL                  | Bruxelles      | NULL          | B-1180      | Belgium     |              1401 |     79900.00 |         314 | MD809704     | 2018-03-03   | 16901.38 |
|         320 | Mini Creations Ltd.                | Huang       | Wing       | 5085559555         | 4575 Hillside Dr.             | NULL                  | New Bedford    | MA            | 50553       | USA         |              1188 |     94500.00 |         320 | GJ597719     | 2019-01-18   |  8307.28 |
|         324 | Stylish Desk Decors, Co.           | Brown       | Ann        | (171) 555-0297     | 35 King George                | NULL                  | London         | NULL          | WX3 6FW     | UK          |              1501 |     77000.00 |         324 | DQ409197     | 2018-12-13   | 13671.82 |
|         324 | Stylish Desk Decors, Co.           | Brown       | Ann        | (171) 555-0297     | 35 King George                | NULL                  | London         | NULL          | WX3 6FW     | UK          |              1501 |     77000.00 |         324 | FP443161     | 2017-07-07   | 29429.14 |
|         328 | Tekni Collectables Inc.            | Brown       | William    | 2015559350         | 7476 Moss Rd.                 | NULL                  | Newark         | NJ            | 94019       | USA         |              1323 |     43000.00 |         328 | EN930356     | 2018-04-16   |  7178.66 |
|         328 | Tekni Collectables Inc.            | Brown       | William    | 2015559350         | 7476 Moss Rd.                 | NULL                  | Newark         | NJ            | 94019       | USA         |              1323 |     43000.00 |         328 | NR631421     | 2018-05-30   | 31102.85 |
|         333 | Australian Gift Network, Co        | Calaghan    | Ben        | 61-7-3844-6555     | 31 Duncan St. West End        | NULL                  | South Brisbane | Queensland    | 4101        | Australia   |              1611 |     51600.00 |         333 | HL209210     | 2017-11-15   | 23936.53 |
|         333 | Australian Gift Network, Co        | Calaghan    | Ben        | 61-7-3844-6555     | 31 Duncan St. West End        | NULL                  | South Brisbane | Queensland    | 4101        | Australia   |              1611 |     51600.00 |         333 | JK479662     | 2017-10-17   |  9821.32 |
|         333 | Australian Gift Network, Co        | Calaghan    | Ben        | 61-7-3844-6555     | 31 Duncan St. West End        | NULL                  | South Brisbane | Queensland    | 4101        | Australia   |              1611 |     51600.00 |         333 | NF959653     | 2019-03-01   | 21432.31 |
|         334 | Suominen Souveniers                | Suominen    | Kalle      | +358 9 8045 555    | Software Engineering Center   | SEC Oy                | Espoo          | NULL          | FIN-02271   | Finland     |              1501 |     98800.00 |         334 | HH517378     | 2017-08-16   | 29716.86 |
|         334 | Suominen Souveniers                | Suominen    | Kalle      | +358 9 8045 555    | Software Engineering Center   | SEC Oy                | Espoo          | NULL          | FIN-02271   | Finland     |              1501 |     98800.00 |         334 | LF737277     | 2018-05-22   | 28394.54 |
|         339 | Classic Gift Ideas, Inc            | Cervantes   | Francisca  | 2155554695         | 782 First Street              | NULL                  | Philadelphia   | PA            | 71270       | USA         |              1188 |     81100.00 |         339 | AP286625     | 2018-10-24   | 23333.06 |
|         339 | Classic Gift Ideas, Inc            | Cervantes   | Francisca  | 2155554695         | 782 First Street              | NULL                  | Philadelphia   | PA            | 71270       | USA         |              1188 |     81100.00 |         339 | DA98827      | 2017-11-28   | 34606.28 |
|         344 | CAF Imports                        | Fernandez   | Jesus      | +34 913 728 555    | Merchants House               | 27-30 Merchant's Quay | Madrid         | NULL          | 28023       | Spain       |              1702 |     59600.00 |         344 | AF246722     | 2017-11-24   | 31428.21 |
|         344 | CAF Imports                        | Fernandez   | Jesus      | +34 913 728 555    | Merchants House               | 27-30 Merchant's Quay | Madrid         | NULL          | 28023       | Spain       |              1702 |     59600.00 |         344 | NJ906924     | 2018-04-02   | 15322.93 |
|         347 | Men 'R' US Retailers, Ltd.         | Chandler    | Brian      | 2155554369         | 6047 Douglas Av.              | NULL                  | Los Angeles    | CA            | 91003       | USA         |              1166 |     57700.00 |         347 | DG700707     | 2018-01-18   | 21053.69 |
|         347 | Men 'R' US Retailers, Ltd.         | Chandler    | Brian      | 2155554369         | 6047 Douglas Av.              | NULL                  | Los Angeles    | CA            | 91003       | USA         |              1166 |     57700.00 |         347 | LG808674     | 2017-10-24   | 20452.50 |
|         350 | Marseille Mini Autos               | Lebihan     | Laurence   | 91.24.4555         | 12, rue des Bouchers          | NULL                  | Marseille      | NULL          | 13008       | France      |              1337 |     65000.00 |         350 | BQ602907     | 2018-12-11   | 18888.31 |
|         353 | Reims Collectables                 | Henriot     | Paul       | 26.47.1555         | 59 rue de l'Abbaye            | NULL                  | Reims          | NULL          | 51100       | France      |              1337 |     81100.00 |         353 | ED878227     | 2017-07-21   | 13920.26 |
|         353 | Reims Collectables                 | Henriot     | Paul       | 26.47.1555         | 59 rue de l'Abbaye            | NULL                  | Reims          | NULL          | 51100       | France      |              1337 |     81100.00 |         353 | GT878649     | 2017-05-21   | 16700.47 |
|         357 | GiftsForHim.com                    | MacKinlay   | Wales      | 64-9-3763555       | 199 Great North Road          | NULL                  | Auckland       | NULL          | NULL        | New Zealand |              1612 |     77700.00 |         357 | AG240323     | 2017-12-16   | 20220.04 |
|         362 | Gifts4AllAges.com                  | Yoshido     | Juri       | 6175559555         | 8616 Spinnaker Dr.            | NULL                  | Boston         | MA            | 51003       | USA         |              1216 |     41900.00 |         362 | FP170292     | 2018-07-11   | 18473.71 |
|         362 | Gifts4AllAges.com                  | Yoshido     | Juri       | 6175559555         | 8616 Spinnaker Dr.            | NULL                  | Boston         | MA            | 51003       | USA         |              1216 |     41900.00 |         362 | OG208861     | 2018-09-21   | 15059.76 |
|         363 | Online Diecast Creations Co.       | Young       | Dorothy    | 6035558647         | 2304 Long Airport Avenue      | NULL                  | Nashua         | NH            | 62019       | USA         |              1216 |    114200.00 |         363 | IS232033     | 2017-01-16   | 10223.83 |
|         379 | Collectables For Less Inc.         | Nelson      | Allen      | 6175558555         | 7825 Douglas Av.              | NULL                  | Brickhaven     | MA            | 58339       | USA         |              1188 |     70700.00 |         379 | CA762595     | 2019-02-12   | 28322.83 |
|         379 | Collectables For Less Inc.         | Nelson      | Allen      | 6175558555         | 7825 Douglas Av.              | NULL                  | Brickhaven     | MA            | 58339       | USA         |              1188 |     70700.00 |         379 | FR499138     | 2017-09-16   | 32680.31 |
|         379 | Collectables For Less Inc.         | Nelson      | Allen      | 6175558555         | 7825 Douglas Av.              | NULL                  | Brickhaven     | MA            | 58339       | USA         |              1188 |     70700.00 |         379 | GB890854     | 2018-08-02   | 12530.51 |
|         381 | Royale Belge                       | Cartrain    | Pascale    | (071) 23 67 2555   | Boulevard Tirou, 255          | NULL                  | Charleroi      | NULL          | B-6000      | Belgium     |              1401 |     23500.00 |         381 | BC726082     | 2018-12-03   | 12081.52 |
|         381 | Royale Belge                       | Cartrain    | Pascale    | (071) 23 67 2555   | Boulevard Tirou, 255          | NULL                  | Charleroi      | NULL          | B-6000      | Belgium     |              1401 |     23500.00 |         381 | GB117430     | 2019-02-03   | 14379.90 |
|         382 | Salzburg Collectables              | Pipps       | Georg      | 6562-9555          | Geislweg 14                   | NULL                  | Salzburg       | NULL          | 5020        | Austria     |              1401 |     71700.00 |         382 | CT821147     | 2018-08-01   |  6419.84 |
|         385 | Cruz & Sons Co.                    | Cruz        | Arnold     | +63 2 555 3587     | 15 McCallum Street            | NatWest Center #13-03 | Makati City    | NULL          | 1227 MM     | Philippines |              1621 |     81500.00 |         385 | BN347084     | 2017-12-02   | 20644.24 |
|         385 | Cruz & Sons Co.                    | Cruz        | Arnold     | +63 2 555 3587     | 15 McCallum Street            | NatWest Center #13-03 | Makati City    | NULL          | 1227 MM     | Philippines |              1621 |     81500.00 |         385 | CP804873     | 2018-11-19   | 15822.84 |
|         398 | Tokyo Collectables, Ltd            | Shimamura   | Akiko      | +81 3 3584 0555    | 2-2-8 Roppongi                | NULL                  | Minato-ku      | Tokyo         | 106-0032    | Japan       |              1621 |     94400.00 |         398 | AJ478695     | 2019-02-14   | 33967.73 |
|         398 | Tokyo Collectables, Ltd            | Shimamura   | Akiko      | +81 3 3584 0555    | 2-2-8 Roppongi                | NULL                  | Minato-ku      | Tokyo         | 106-0032    | Japan       |              1621 |     94400.00 |         398 | DO787644     | 2018-06-21   | 22037.91 |
|         406 | Auto Canal+ Petit                  | Perrier     | Dominique  | (1) 47.55.6555     | 25, rue Lauriston             | NULL                  | Paris          | NULL          | 75016       | France      |              1337 |     95000.00 |         406 | BJMPR4545    | 2019-04-23   | 12190.85 |
|         406 | Auto Canal+ Petit                  | Perrier     | Dominique  | (1) 47.55.6555     | 25, rue Lauriston             | NULL                  | Paris          | NULL          | 75016       | France      |              1337 |     95000.00 |         406 | NA197101     | 2018-06-17   | 25080.96 |
|         412 | Extreme Desk Decorations, Ltd      | McRoy       | Sarah      | 04 499 9555        | 101 Lambton Quay              | Level 11              | Wellington     | NULL          | NULL        | New Zealand |              1612 |     86800.00 |         412 | PJ434867     | 2018-04-14   | 31670.37 |
|         415 | Bavarian Collectables Imports, Co. | Donnermeyer | Michael    |  +49 89 61 08 9555 | Hansastr. 15                  | NULL                  | Munich         | NULL          | 80686       | Germany     |              1504 |     77000.00 |         415 | ER54537      | 2018-09-28   | 31310.09 |
|         424 | Classic Legends Inc.               | Hernandez   | Maria      | 2125558493         | 5905 Pompton St.              | Suite 750             | NYC            | NY            | 10022       | USA         |              1286 |     67500.00 |         424 | KF480160     | 2018-12-07   | 25505.98 |
|         424 | Classic Legends Inc.               | Hernandez   | Maria      | 2125558493         | 5905 Pompton St.              | Suite 750             | NYC            | NY            | 10022       | USA         |              1286 |     67500.00 |         424 | LM271923     | 2017-04-16   | 21665.98 |
|         424 | Classic Legends Inc.               | Hernandez   | Maria      | 2125558493         | 5905 Pompton St.              | Suite 750             | NYC            | NY            | 10022       | USA         |              1286 |     67500.00 |         424 | OA595449     | 2017-10-31   | 22042.37 |
|         447 | Gift Ideas Corp.                   | Lewis       | Dan        | 2035554407         | 2440 Pompton St.              | NULL                  | Glendale       | CT            | 97561       | USA         |              1323 |     49700.00 |         447 | AO757239     | 2017-09-15   |  6631.36 |
|         447 | Gift Ideas Corp.                   | Lewis       | Dan        | 2035554407         | 2440 Pompton St.              | NULL                  | Glendale       | CT            | 97561       | USA         |              1323 |     49700.00 |         447 | ER615123     | 2017-06-25   | 17032.29 |
|         447 | Gift Ideas Corp.                   | Lewis       | Dan        | 2035554407         | 2440 Pompton St.              | NULL                  | Glendale       | CT            | 97561       | USA         |              1323 |     49700.00 |         447 | OU516561     | 2018-12-17   | 26304.13 |
|         448 | Scandinavian Gift Ideas            | Larsson     | Martha     | 0695-34 6555       | Åkergatan 24                  | NULL                  | Bräcke         | NULL          | S-844 67    | Sweden      |              1504 |    116400.00 |         448 | FS299615     | 2019-04-18   | 27966.54 |
|         452 | Mini Auto Werke                    | Mendel      | Roland     | 7675-3555          | Kirchgasse 6                  | NULL                  | Graz           | NULL          | 8010        | Austria     |              1401 |     45300.00 |         452 | ED473873     | 2017-11-15   | 27121.90 |
|         452 | Mini Auto Werke                    | Mendel      | Roland     | 7675-3555          | Kirchgasse 6                  | NULL                  | Graz           | NULL          | 8010        | Austria     |              1401 |     45300.00 |         452 | FN640986     | 2017-11-20   | 15130.97 |
|         452 | Mini Auto Werke                    | Mendel      | Roland     | 7675-3555          | Kirchgasse 6                  | NULL                  | Graz           | NULL          | 8010        | Austria     |              1401 |     45300.00 |         452 | HG635467     | 2019-05-03   |  8807.12 |
|         455 | Super Scale Inc.                   | Murphy      | Leslie     | 2035559545         | 567 North Pendale Street      | NULL                  | New Haven      | CT            | 97823       | USA         |              1286 |     95400.00 |         455 | IR662429     | 2018-05-12   | 32239.47 |
|         456 | Microscale Inc.                    | Choi        | Yu         | 2125551957         | 5290 North Pendale Street     | Suite 200             | NYC            | NY            | 10022       | USA         |              1286 |     39800.00 |         456 | GJ715659     | 2018-11-13   | 27550.51 |
|         458 | Corrida Auto Replicas, Ltd         | Sommer      | Martín     | (91) 555 22 82     | C/ Araquil, 67                | NULL                  | Madrid         | NULL          | 28023       | Spain       |              1702 |    104600.00 |         458 | DD995006     | 2018-11-15   | 33145.56 |
|         458 | Corrida Auto Replicas, Ltd         | Sommer      | Martín     | (91) 555 22 82     | C/ Araquil, 67                | NULL                  | Madrid         | NULL          | 28023       | Spain       |              1702 |    104600.00 |         458 | NA377824     | 2018-02-06   | 22162.61 |
|         462 | FunGiftIdeas.com                   | Benitez     | Violeta    | 5085552555         | 1785 First Street             | NULL                  | New Bedford    | MA            | 50553       | USA         |              1216 |     85800.00 |         462 | ED203908     | 2019-04-15   | 30293.77 |
|         462 | FunGiftIdeas.com                   | Benitez     | Violeta    | 5085552555         | 1785 First Street             | NULL                  | New Bedford    | MA            | 50553       | USA         |              1216 |     85800.00 |         462 | GC60330      | 2017-11-08   |  9977.85 |
|         471 | Australian Collectables, Ltd       | Clenahan    | Sean       | 61-9-3844-6555     | 7 Allen Street                | NULL                  | Glen Waverly   | Victoria      | 3150        | Australia   |              1611 |     60300.00 |         471 | AB661578     | 2018-07-28   |  9415.13 |
|         473 | Frau da Collezione                 | Ricotti     | Franco     | +39 022515555      | 20093 Cologno Monzese         | Alessandro Volta 16   | Milan          | NULL          | NULL        | Italy       |              1401 |     34800.00 |         473 | LL427009     | 2018-02-17   |  7612.06 |
|         473 | Frau da Collezione                 | Ricotti     | Franco     | +39 022515555      | 20093 Cologno Monzese         | Alessandro Volta 16   | Milan          | NULL          | NULL        | Italy       |              1401 |     34800.00 |         473 | PC688499     | 2017-10-27   | 17746.26 |
|         475 | West Coast Collectables Co.        | Thompson    | Steve      | 3105553722         | 3675 Furth Circle             | NULL                  | Burbank        | CA            | 94019       | USA         |              1166 |     55400.00 |         475 | JP113227     | 2017-12-09   |  7678.25 |
|         486 | Motor Mint Distributors Inc.       | Salazar     | Rosa       | 2155559857         | 11328 Douglas Av.             | NULL                  | Philadelphia   | PA            | 71270       | USA         |              1323 |     72600.00 |         486 | BL66528      | 2018-04-14   |  5899.38 |
|         486 | Motor Mint Distributors Inc.       | Salazar     | Rosa       | 2155559857         | 11328 Douglas Av.             | NULL                  | Philadelphia   | PA            | 71270       | USA         |              1323 |     72600.00 |         486 | JB117768     | 2017-03-20   | 25833.14 |
|         487 | Signal Collectibles Ltd.           | Taylor      | Sue        | 4155554312         | 2793 Furth Circle             | NULL                  | Brisbane       | CA            | 94217       | USA         |              1165 |     60300.00 |         487 | AH612904     | 2017-09-28   | 29997.09 |
|         487 | Signal Collectibles Ltd.           | Taylor      | Sue        | 4155554312         | 2793 Furth Circle             | NULL                  | Brisbane       | CA            | 94217       | USA         |              1165 |     60300.00 |         487 | PT550181     | 0000-00-00   | 12573.28 |
|         489 | Double Decker Gift Stores, Ltd     | Smith       | Thomas     | (171) 555-7555     | 120 Hanover Sq.               | NULL                  | London         | NULL          | WA1 1DP     | UK          |              1501 |     43300.00 |         489 | OC773849     | 2017-12-04   | 22275.73 |
|         489 | Double Decker Gift Stores, Ltd     | Smith       | Thomas     | (171) 555-7555     | 120 Hanover Sq.               | NULL                  | London         | NULL          | WA1 1DP     | UK          |              1501 |     43300.00 |         489 | PO860906     | 2018-01-31   |  7310.42 |
|         495 | Diecast Collectables               | Franco      | Valarie    | 6175552555         | 6251 Ingle Ln.                | NULL                  | Boston         | MA            | 51003       | USA         |              1188 |     85100.00 |         495 | FN155234     | 2018-05-14   |  6276.60 |
|         496 | Kelly's Gift Shop                  | Snowden     | Tony       | +64 9 5555500      | Arenales 1938 3'A'            | NULL                  | Auckland       | NULL          | NULL        | New Zealand |              1612 |    110000.00 |         496 | EU531600     | 2019-05-25   | 30253.75 |
|         496 | Kelly's Gift Shop                  | Snowden     | Tony       | +64 9 5555500      | Arenales 1938 3'A'            | NULL                  | Auckland       | NULL          | NULL        | New Zealand |              1612 |    110000.00 |         496 | MB342426     | 2017-07-16   | 32077.44 |
+-------------+------------------------------------+-------------+------------+--------------------+-------------------------------+-----------------------+----------------+---------------+-------------+-------------+-------------------+--------------+-------------+--------------+--------------+----------+
134 rows in set (0.00 sec)

```
</details>




<details><summary>Question 3 : Add new employee/saleman with following details:- 
Emp Id: 15657
First Name: Lakshmi
Last Name: Roy
Extension: x4065
Email: lakshiroy1@lcomotors.com
Office Code: 4
Reports To: 1088
Job Title: Sales Rep
</summary>
  
  ## QUERY : 
``` 
       INSERT INTO employees(employee_id,first_name,last_name,extension,email,office_code,reports_to,job_title) VALUE(15657,'Lakshmi','Roy','x4065','lakshiroy1@lcomotors.com',4,1088,'Sales Rep');
       
```

## RESULT 
```
Query OK, 1 row affected (0.00 sec)
```
</details>




<details><summary>Question 4 : Assign the new employee to the customer whose phone is 2125557413.</summary>
  
  ## QUERY : 
``` 
  UPDATE customers SET sales_employee_id=(SELECT employee_id FROM employees WHERE employee_id=15657) WHERE phone='2125557413';
  
```

## RESULT 
```

Query OK, 1 row affected (0.03 sec)
Rows matched: 1  Changed: 1  Warnings: 0

```
</details>




<details><summary>Question 5 : Write a SQL query to fetch shipped motorcycles.</summary>
  
  ## QUERY : 
``` 
       SELECT products.product_name,products.product_line,products.product_scale,products.product_vendor, orders.status FROM products
       INNER JOIN orderdetails ON orderdetails.product_code=products.product_code
       INNER JOIN orders ON orders.order_id=orderdetails.order_id
       WHERE orders.status='shipped' AND products.product_line='Motorcycles';

```

## RESULT 
```

+---------------------------------------+--------------+---------------+---------------------------+---------+
| product_name                          | product_line | product_scale | product_vendor            | status  |
+---------------------------------------+--------------+---------------+---------------------------+---------+
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1969 Harley Davidson Ultimate Chopper | Motorcycles  | 1:10          | Min Lin Diecast           | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 1996 Moto Guzzi 1100i                 | Motorcycles  | 1:10          | Highway 66 Mini Classics  | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2017 Harley-Davidson Eagle Drag Bike  | Motorcycles  | 1:10          | Red Start Diecast         | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 2002 Suzuki XREO                      | Motorcycles  | 1:12          | Unimax Art Galleries      | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1936 Harley Davidson El Knucklehead   | Motorcycles  | 1:18          | Welly Diecast Productions | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1957 Vespa GS150                      | Motorcycles  | 1:18          | Studio M Art Models       | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1997 BMW R 1100 S                     | Motorcycles  | 1:24          | Autoart Studio Design     | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1960 BSA Gold Star DBD34              | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1982 Ducati 900 Monster               | Motorcycles  | 1:24          | Highway 66 Mini Classics  | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1997 BMW F650 ST                      | Motorcycles  | 1:32          | Exoto Designs             | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1982 Ducati 996 R                     | Motorcycles  | 1:32          | Gearbox Collectibles      | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 1974 Ducati 350 Mk3 Desmo             | Motorcycles  | 1:32          | Second Gear Diecast       | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
| 2002 Yamaha YZR M1                    | Motorcycles  | 1:50          | Autoart Studio Design     | Shipped |
+---------------------------------------+--------------+---------------+---------------------------+---------+
351 rows in set (0.01 sec)

```
</details>




<details><summary>Question 6 : Write a SQL query to get details of all employees/salesmen in the office lacted in Sydney?</summary>
  
  ## QUERY : 
``` 
   SELECT * FROM employees
       INNER JOIN offices ON offices.office_code=employees.office_code
       WHERE offices.city='Sydney';

```

## RESULT 
```
+-------------+-----------+------------+-----------+--------------------------+-------------+------------+----------------------+-------------+--------+-----------------+-----------------------+---------------+-------+-----------+-------------+-----------+
| employee_id | last_name | first_name | extension | email                    | office_code | reports_to | job_title            | office_code | city   | phone           | address_line1         | address_line2 | state | country   | postal_code | territory |
+-------------+-----------+------------+-----------+--------------------------+-------------+------------+----------------------+-------------+--------+-----------------+-----------------------+---------------+-------+-----------+-------------+-----------+
|        1088 | Patterson | William    | x4871     | wpatterson@lcomotors.com | 6           |       1056 | Sales Manager (APAC) | 6           | Sydney | +61 2 9264 2451 | 5-11 Wentworth Avenue | Floor #2      | NULL  | Australia | NSW 2010    | APAC      |
|        1611 | Fixter    | Andy       | x101      | afixter@lcomotors.com    | 6           |       1088 | Sales Rep            | 6           | Sydney | +61 2 9264 2451 | 5-11 Wentworth Avenue | Floor #2      | NULL  | Australia | NSW 2010    | APAC      |
|        1612 | Marsh     | Peter      | x102      | pmarsh@lcomotors.com     | 6           |       1088 | Sales Rep            | 6           | Sydney | +61 2 9264 2451 | 5-11 Wentworth Avenue | Floor #2      | NULL  | Australia | NSW 2010    | APAC      |
|        1619 | King      | Tom        | x103      | tking@lcomotors.com      | 6           |       1088 | Sales Rep            | 6           | Sydney | +61 2 9264 2451 | 5-11 Wentworth Avenue | Floor #2      | NULL  | Australia | NSW 2010    | APAC      |
+-------------+-----------+------------+-----------+--------------------------+-------------+------------+----------------------+-------------+--------+-----------------+-----------------------+---------------+-------+-----------+-------------+-----------+
4 rows in set (0.01 sec)

```
</details>




<details><summary>Question 7 : How would you fetch the details of customers whose orders are in process?</summary>
  
  ## QUERY : 
``` 
       SELECT * FROM customers
       INNER JOIN orders ON orders.customer_id=customers.customer_id
       WHERE orders.status='In Process';

```

## RESULT 
```
+-------------+------------------------------+-----------+------------+-----------------+------------------------------+-----------------+------------+-------+-------------+-----------+-------------------+--------------+----------+------------+---------------+--------------+------------+-----------------------------------------------------+-------------+
| customer_id | customer_name                | last_name | first_name | phone           | address_line1                | address_line2   | city       | state | postal_code | country   | sales_employee_id | credit_limit | order_id | order_date | required_date | shipped_date | status     | comments                                            | customer_id |
+-------------+------------------------------+-----------+------------+-----------------+------------------------------+-----------------+------------+-------+-------------+-----------+-------------------+--------------+----------+------------+---------------+--------------+------------+-----------------------------------------------------+-------------+
|         282 | Souveniers And Things Co.    | Huxley    | Adrian     | +61 2 9495 8555 | Monitor Money Building       | 815 Pacific Hwy | Chatswood  | NSW   | 2067        | Australia |              1611 |     93300.00 |    10420 | 2019-05-29 | 2019-06-07    | NULL         | In Process | NULL                                                |         282 |
|         124 | Mini Gifts Distributors Ltd. | Nelson    | Susan      | 4155551450      | 5677 Strong St.              | NULL            | San Rafael | CA    | 97562       | USA       |              1165 |    210500.00 |    10421 | 2019-05-29 | 2019-06-06    | NULL         | In Process | Custom shipping instructions were sent to warehouse |         124 |
|         157 | Diecast Classics Inc.        | Leong     | Kelvin     | 2155551555      | 7586 Pompton St.             | NULL            | Allentown  | PA    | 70267       | USA       |              1216 |    100600.00 |    10422 | 2019-05-30 | 2019-06-11    | NULL         | In Process | NULL                                                |         157 |
|         314 | Petit Auto                   | Dewey     | Catherine  | (02) 5554 67    | Rue Joseph-Bens 532          | NULL            | Bruxelles  | NULL  | B-1180      | Belgium   |              1401 |     79900.00 |    10423 | 2019-05-30 | 2019-06-05    | NULL         | In Process | NULL                                                |         314 |
|         141 | Euro+ Shopping Channel       | Freyre    | Diego      | (91) 555 94 44  | C/ Moralzarzal, 86           | NULL            | Madrid     | NULL  | 28034       | Spain     |              1370 |    227600.00 |    10424 | 2019-05-31 | 2019-06-08    | NULL         | In Process | NULL                                                |         141 |
|         119 | La Rochelle Gifts            | Labrune   | Janine     | 40.67.8555      | 67, rue des Cinquante Otages | NULL            | Nantes     | NULL  | 44000       | France    |              1370 |    118200.00 |    10425 | 2019-05-31 | 2019-06-07    | NULL         | In Process | NULL                                                |         119 |
+-------------+------------------------------+-----------+------------+-----------------+------------------------------+-----------------+------------+-------+-------------+-----------+-------------------+--------------+----------+------------+---------------+--------------+------------+-----------------------------------------------------+-------------+
6 rows in set (0.01 sec)

```
</details>




<details><summary>Question 8 : how would you fetch details of products with less than30 orders?</summary>
  
  ## QUERY : 
``` 
       SELECT products.product_name,products.product_line,products.product_scale,products.product_vendor FROM products
       INNER JOIN orderdetails ON orderdetails.product_code=products.product_code
       WHERE orderdetails.quantity_ordered <30;

```

## RESULT 
```

+---------------------------------------------+------------------+---------------+---------------------------+
| product_name                                | product_line     | product_scale | product_vendor            |
+---------------------------------------------+------------------+---------------+---------------------------+
| 1932 Alfa Romeo 8C2300 Spider Sport         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1932 Model A Ford J-Coupe                   | Vintage Cars     | 1:18          | Autoart Studio Design     |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1952 Alpine Renault 1300                    | Classic Cars     | 1:10          | Classic Metal Creations   |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1926 Ford Fire Engine                       | Trucks and Buses | 1:18          | Carousel DieCast Legends  |
| 1913 Ford Model T Speedster                 | Vintage Cars     | 1:18          | Carousel DieCast Legends  |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1936 Chrysler Airflow                       | Vintage Cars     | 1:24          | Second Gear Diecast       |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1964 Mercedes Tour Bus                      | Trucks and Buses | 1:18          | Unimax Art Galleries      |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| The Queen Mary                              | Ships            | 1:700         | Welly Diecast Productions |
| Pont Yacht                                  | Ships            | 1:72          | Unimax Art Galleries      |
| 1928 British Royal Navy Airplane            | Planes           | 1:24          | Classic Metal Creations   |
| 1900s Vintage Tri-Plane                     | Planes           | 1:24          | Unimax Art Galleries      |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1936 Harley Davidson El Knucklehead         | Motorcycles      | 1:18          | Welly Diecast Productions |
| 1997 BMW R 1100 S                           | Motorcycles      | 1:24          | Autoart Studio Design     |
| 1997 BMW F650 ST                            | Motorcycles      | 1:32          | Exoto Designs             |
| 1969 Dodge Super Bee                        | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 1993 Mazda RX-7                             | Classic Cars     | 1:18          | Highway 66 Mini Classics  |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1982 Lamborghini Diablo                     | Classic Cars     | 1:24          | Second Gear Diecast       |
| 1932 Alfa Romeo 8C2300 Spider Sport         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1966 Shelby Cobra 427 S/C                   | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1969 Chevrolet Camaro Z28                   | Classic Cars     | 1:24          | Exoto Designs             |
| 1934 Ford V8 Coupe                          | Vintage Cars     | 1:18          | Min Lin Diecast           |
| 1936 Chrysler Airflow                       | Vintage Cars     | 1:24          | Second Gear Diecast       |
| 1952 Alpine Renault 1300                    | Classic Cars     | 1:10          | Classic Metal Creations   |
| 1913 Ford Model T Speedster                 | Vintage Cars     | 1:18          | Carousel DieCast Legends  |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1996 Peterbilt 379 Stake Bed with Outrigger | Trucks and Buses | 1:32          | Red Start Diecast         |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| 1958 Chevy Corvette Limited Edition         | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1954 Greyhound Scenicruiser                 | Trucks and Buses | 1:32          | Classic Metal Creations   |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| 1950's Chicago Surface Lines Streetcar      | Trains           | 1:32          | Gearbox Collectibles      |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1904 Buick Runabout                         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1962 City of Detroit Streetcar              | Trains           | 1:50          | Classic Metal Creations   |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| 1941 Chevrolet Special Deluxe Cabriolet     | Vintage Cars     | 1:18          | Exoto Designs             |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| Corsair F4U ( Bird Cage)                    | Planes           | 1:24          | Second Gear Diecast       |
| The Schooner Bluenose                       | Ships            | 1:700         | Autoart Studio Design     |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| American Airlines: MD-11S                   | Planes           | 1:700         | Second Gear Diecast       |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1900s Vintage Tri-Plane                     | Planes           | 1:24          | Unimax Art Galleries      |
| 1997 BMW F650 ST                            | Motorcycles      | 1:32          | Exoto Designs             |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 1974 Ducati 350 Mk3 Desmo                   | Motorcycles      | 1:32          | Second Gear Diecast       |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1969 Dodge Super Bee                        | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1957 Corvette Convertible                   | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1961 Chevrolet Impala                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1965 Aston Martin DB5                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1917 Grand Touring Sedan                    | Vintage Cars     | 1:18          | Welly Diecast Productions |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 1952 Citroen-15CV                           | Classic Cars     | 1:24          | Exoto Designs             |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| 1996 Peterbilt 379 Stake Bed with Outrigger | Trucks and Buses | 1:32          | Red Start Diecast         |
| 1957 Chevy Pickup                           | Trucks and Buses | 1:12          | Exoto Designs             |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1950's Chicago Surface Lines Streetcar      | Trains           | 1:32          | Gearbox Collectibles      |
| 1980s Black Hawk Helicopter                 | Planes           | 1:18          | Red Start Diecast         |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| American Airlines: MD-11S                   | Planes           | 1:700         | Second Gear Diecast       |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| 1997 BMW F650 ST                            | Motorcycles      | 1:32          | Exoto Designs             |
| 1930 Buick Marquette Phaeton                | Vintage Cars     | 1:50          | Studio M Art Models       |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1982 Ducati 900 Monster                     | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1982 Lamborghini Diablo                     | Classic Cars     | 1:24          | Second Gear Diecast       |
| 1971 Alpine Renault 1600s                   | Classic Cars     | 1:24          | Welly Diecast Productions |
| 1961 Chevrolet Impala                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1993 Mazda RX-7                             | Classic Cars     | 1:18          | Highway 66 Mini Classics  |
| 1966 Shelby Cobra 427 S/C                   | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1949 Jaguar XK 120                          | Classic Cars     | 1:24          | Classic Metal Creations   |
| 2002 Chevy Corvette                         | Classic Cars     | 1:24          | Gearbox Collectibles      |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1934 Ford V8 Coupe                          | Vintage Cars     | 1:18          | Min Lin Diecast           |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1936 Chrysler Airflow                       | Vintage Cars     | 1:24          | Second Gear Diecast       |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1939 Cadillac Limousine                     | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1996 Peterbilt 379 Stake Bed with Outrigger | Trucks and Buses | 1:32          | Red Start Diecast         |
| 1957 Chevy Pickup                           | Trucks and Buses | 1:12          | Exoto Designs             |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1958 Chevy Corvette Limited Edition         | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1954 Greyhound Scenicruiser                 | Trucks and Buses | 1:32          | Classic Metal Creations   |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1904 Buick Runabout                         | Vintage Cars     | 1:18          | Exoto Designs             |
| The Titanic                                 | Ships            | 1:700         | Carousel DieCast Legends  |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| Corsair F4U ( Bird Cage)                    | Planes           | 1:24          | Second Gear Diecast       |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| F/A 18 Hornet 1/72                          | Planes           | 1:72          | Motor City Art Classics   |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| 1982 Ducati 900 Monster                     | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1974 Ducati 350 Mk3 Desmo                   | Motorcycles      | 1:32          | Second Gear Diecast       |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 1957 Corvette Convertible                   | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1982 Lamborghini Diablo                     | Classic Cars     | 1:24          | Second Gear Diecast       |
| 1956 Porsche 356A Coupe                     | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1993 Mazda RX-7                             | Classic Cars     | 1:18          | Highway 66 Mini Classics  |
| 1995 Honda Civic                            | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1948 Porsche Type 356 Roadster              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1949 Jaguar XK 120                          | Classic Cars     | 1:24          | Classic Metal Creations   |
| 2002 Chevy Corvette                         | Classic Cars     | 1:24          | Gearbox Collectibles      |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1936 Chrysler Airflow                       | Vintage Cars     | 1:24          | Second Gear Diecast       |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1982 Camaro Z28                             | Classic Cars     | 1:18          | Carousel DieCast Legends  |
| 1957 Chevy Pickup                           | Trucks and Buses | 1:12          | Exoto Designs             |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 2001 Ferrari Enzo                           | Classic Cars     | 1:12          | Second Gear Diecast       |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 1904 Buick Runabout                         | Vintage Cars     | 1:18          | Exoto Designs             |
| The Queen Mary                              | Ships            | 1:700         | Welly Diecast Productions |
| 1941 Chevrolet Special Deluxe Cabriolet     | Vintage Cars     | 1:18          | Exoto Designs             |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| 1930 Buick Marquette Phaeton                | Vintage Cars     | 1:50          | Studio M Art Models       |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| 1960 BSA Gold Star DBD34                    | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1969 Dodge Super Bee                        | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1957 Vespa GS150                            | Motorcycles      | 1:18          | Studio M Art Models       |
| 1982 Ducati 900 Monster                     | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1961 Chevrolet Impala                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1974 Ducati 350 Mk3 Desmo                   | Motorcycles      | 1:32          | Second Gear Diecast       |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1993 Mazda RX-7                             | Classic Cars     | 1:18          | Highway 66 Mini Classics  |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1966 Shelby Cobra 427 S/C                   | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1949 Jaguar XK 120                          | Classic Cars     | 1:24          | Classic Metal Creations   |
| 1952 Citroen-15CV                           | Classic Cars     | 1:24          | Exoto Designs             |
| 1969 Chevrolet Camaro Z28                   | Classic Cars     | 1:24          | Exoto Designs             |
| 1917 Grand Touring Sedan                    | Vintage Cars     | 1:18          | Welly Diecast Productions |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1952 Alpine Renault 1300                    | Classic Cars     | 1:10          | Classic Metal Creations   |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1939 Cadillac Limousine                     | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1958 Chevy Corvette Limited Edition         | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1904 Buick Runabout                         | Vintage Cars     | 1:18          | Exoto Designs             |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| 1912 Ford Model T Delivery Wagon            | Vintage Cars     | 1:24          | Min Lin Diecast           |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| The Titanic                                 | Ships            | 1:700         | Carousel DieCast Legends  |
| The Queen Mary                              | Ships            | 1:700         | Welly Diecast Productions |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1960 BSA Gold Star DBD34                    | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| Corsair F4U ( Bird Cage)                    | Planes           | 1:24          | Second Gear Diecast       |
| 1997 BMW F650 ST                            | Motorcycles      | 1:32          | Exoto Designs             |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| 1961 Chevrolet Impala                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1949 Jaguar XK 120                          | Classic Cars     | 1:24          | Classic Metal Creations   |
| 1969 Chevrolet Camaro Z28                   | Classic Cars     | 1:24          | Exoto Designs             |
| 2002 Chevy Corvette                         | Classic Cars     | 1:24          | Gearbox Collectibles      |
| 1917 Grand Touring Sedan                    | Vintage Cars     | 1:18          | Welly Diecast Productions |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1934 Ford V8 Coupe                          | Vintage Cars     | 1:18          | Min Lin Diecast           |
| 1917 Maxwell Touring Car                    | Vintage Cars     | 1:18          | Exoto Designs             |
| 1932 Alfa Romeo 8C2300 Spider Sport         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 1952 Citroen-15CV                           | Classic Cars     | 1:24          | Exoto Designs             |
| 1936 Chrysler Airflow                       | Vintage Cars     | 1:24          | Second Gear Diecast       |
| 1957 Chevy Pickup                           | Trucks and Buses | 1:12          | Exoto Designs             |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1996 Peterbilt 379 Stake Bed with Outrigger | Trucks and Buses | 1:32          | Red Start Diecast         |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1950's Chicago Surface Lines Streetcar      | Trains           | 1:32          | Gearbox Collectibles      |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| The Schooner Bluenose                       | Ships            | 1:700         | Autoart Studio Design     |
| The Queen Mary                              | Ships            | 1:700         | Welly Diecast Productions |
| 1972 Alfa Romeo GTA                         | Classic Cars     | 1:10          | Motor City Art Classics   |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1900s Vintage Tri-Plane                     | Planes           | 1:24          | Unimax Art Galleries      |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 1969 Harley Davidson Ultimate Chopper       | Motorcycles      | 1:10          | Min Lin Diecast           |
| 1936 Harley Davidson El Knucklehead         | Motorcycles      | 1:18          | Welly Diecast Productions |
| 1957 Vespa GS150                            | Motorcycles      | 1:18          | Studio M Art Models       |
| 1960 BSA Gold Star DBD34                    | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1961 Chevrolet Impala                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1974 Ducati 350 Mk3 Desmo                   | Motorcycles      | 1:32          | Second Gear Diecast       |
| 2002 Yamaha YZR M1                          | Motorcycles      | 1:50          | Autoart Studio Design     |
| 1968 Ford Mustang                           | Classic Cars     | 1:12          | Autoart Studio Design     |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1995 Honda Civic                            | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1971 Alpine Renault 1600s                   | Classic Cars     | 1:24          | Welly Diecast Productions |
| 1956 Porsche 356A Coupe                     | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1937 Lincoln Berline                        | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1932 Model A Ford J-Coupe                   | Vintage Cars     | 1:18          | Autoart Studio Design     |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1952 Citroen-15CV                           | Classic Cars     | 1:24          | Exoto Designs             |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1952 Alpine Renault 1300                    | Classic Cars     | 1:10          | Classic Metal Creations   |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1940 Ford Pickup Truck                      | Trucks and Buses | 1:18          | Studio M Art Models       |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1940s Ford truck                            | Trucks and Buses | 1:18          | Motor City Art Classics   |
| 1982 Camaro Z28                             | Classic Cars     | 1:18          | Carousel DieCast Legends  |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| 2001 Ferrari Enzo                           | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| 1962 City of Detroit Streetcar              | Trains           | 1:50          | Classic Metal Creations   |
| The Schooner Bluenose                       | Ships            | 1:700         | Autoart Studio Design     |
| The Queen Mary                              | Ships            | 1:700         | Welly Diecast Productions |
| Pont Yacht                                  | Ships            | 1:72          | Unimax Art Galleries      |
| 1972 Alfa Romeo GTA                         | Classic Cars     | 1:10          | Motor City Art Classics   |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| 1997 BMW R 1100 S                           | Motorcycles      | 1:24          | Autoart Studio Design     |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1968 Ford Mustang                           | Classic Cars     | 1:12          | Autoart Studio Design     |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1993 Mazda RX-7                             | Classic Cars     | 1:18          | Highway 66 Mini Classics  |
| 1965 Aston Martin DB5                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1952 Citroen-15CV                           | Classic Cars     | 1:24          | Exoto Designs             |
| 1937 Lincoln Berline                        | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1917 Grand Touring Sedan                    | Vintage Cars     | 1:18          | Welly Diecast Productions |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1913 Ford Model T Speedster                 | Vintage Cars     | 1:18          | Carousel DieCast Legends  |
| 1934 Ford V8 Coupe                          | Vintage Cars     | 1:18          | Min Lin Diecast           |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1932 Alfa Romeo 8C2300 Spider Sport         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1936 Chrysler Airflow                       | Vintage Cars     | 1:24          | Second Gear Diecast       |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1940 Ford Pickup Truck                      | Trucks and Buses | 1:18          | Studio M Art Models       |
| 1982 Camaro Z28                             | Classic Cars     | 1:18          | Carousel DieCast Legends  |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1969 Corvair Monza                          | Classic Cars     | 1:18          | Welly Diecast Productions |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1941 Chevrolet Special Deluxe Cabriolet     | Vintage Cars     | 1:18          | Exoto Designs             |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| The Schooner Bluenose                       | Ships            | 1:700         | Autoart Studio Design     |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| The Titanic                                 | Ships            | 1:700         | Carousel DieCast Legends  |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| 1930 Buick Marquette Phaeton                | Vintage Cars     | 1:50          | Studio M Art Models       |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| 1969 Harley Davidson Ultimate Chopper       | Motorcycles      | 1:10          | Min Lin Diecast           |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1960 BSA Gold Star DBD34                    | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 1968 Ford Mustang                           | Classic Cars     | 1:12          | Autoart Studio Design     |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1982 Lamborghini Diablo                     | Classic Cars     | 1:24          | Second Gear Diecast       |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1932 Model A Ford J-Coupe                   | Vintage Cars     | 1:18          | Autoart Studio Design     |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1932 Alfa Romeo 8C2300 Spider Sport         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1934 Ford V8 Coupe                          | Vintage Cars     | 1:18          | Min Lin Diecast           |
| 1917 Maxwell Touring Car                    | Vintage Cars     | 1:18          | Exoto Designs             |
| 1939 Cadillac Limousine                     | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1954 Greyhound Scenicruiser                 | Trucks and Buses | 1:32          | Classic Metal Creations   |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| 1969 Corvair Monza                          | Classic Cars     | 1:18          | Welly Diecast Productions |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| 1912 Ford Model T Delivery Wagon            | Vintage Cars     | 1:24          | Min Lin Diecast           |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| 1941 Chevrolet Special Deluxe Cabriolet     | Vintage Cars     | 1:18          | Exoto Designs             |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| 1928 British Royal Navy Airplane            | Planes           | 1:24          | Classic Metal Creations   |
| Corsair F4U ( Bird Cage)                    | Planes           | 1:24          | Second Gear Diecast       |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1997 BMW R 1100 S                           | Motorcycles      | 1:24          | Autoart Studio Design     |
| 1982 Ducati 900 Monster                     | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1961 Chevrolet Impala                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1993 Mazda RX-7                             | Classic Cars     | 1:18          | Highway 66 Mini Classics  |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1969 Chevrolet Camaro Z28                   | Classic Cars     | 1:24          | Exoto Designs             |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1952 Citroen-15CV                           | Classic Cars     | 1:24          | Exoto Designs             |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1932 Model A Ford J-Coupe                   | Vintage Cars     | 1:18          | Autoart Studio Design     |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1937 Lincoln Berline                        | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1964 Mercedes Tour Bus                      | Trucks and Buses | 1:18          | Unimax Art Galleries      |
| 1958 Chevy Corvette Limited Edition         | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1950's Chicago Surface Lines Streetcar      | Trains           | 1:32          | Gearbox Collectibles      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| 1936 Harley Davidson El Knucklehead         | Motorcycles      | 1:18          | Welly Diecast Productions |
| 1900s Vintage Tri-Plane                     | Planes           | 1:24          | Unimax Art Galleries      |
| 1997 BMW F650 ST                            | Motorcycles      | 1:32          | Exoto Designs             |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| F/A 18 Hornet 1/72                          | Planes           | 1:72          | Motor City Art Classics   |
| 1968 Ford Mustang                           | Classic Cars     | 1:12          | Autoart Studio Design     |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1971 Alpine Renault 1600s                   | Classic Cars     | 1:24          | Welly Diecast Productions |
| 1995 Honda Civic                            | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1937 Lincoln Berline                        | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1917 Grand Touring Sedan                    | Vintage Cars     | 1:18          | Welly Diecast Productions |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1952 Alpine Renault 1300                    | Classic Cars     | 1:10          | Classic Metal Creations   |
| 1913 Ford Model T Speedster                 | Vintage Cars     | 1:18          | Carousel DieCast Legends  |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1964 Mercedes Tour Bus                      | Trucks and Buses | 1:18          | Unimax Art Galleries      |
| 1926 Ford Fire Engine                       | Trucks and Buses | 1:18          | Carousel DieCast Legends  |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1954 Greyhound Scenicruiser                 | Trucks and Buses | 1:32          | Classic Metal Creations   |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| 1904 Buick Runabout                         | Vintage Cars     | 1:18          | Exoto Designs             |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| Pont Yacht                                  | Ships            | 1:72          | Unimax Art Galleries      |
| The USS Constitution Ship                   | Ships            | 1:700         | Red Start Diecast         |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1928 British Royal Navy Airplane            | Planes           | 1:24          | Classic Metal Creations   |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| 1936 Harley Davidson El Knucklehead         | Motorcycles      | 1:18          | Welly Diecast Productions |
| 1969 Harley Davidson Ultimate Chopper       | Motorcycles      | 1:10          | Min Lin Diecast           |
| 1957 Vespa GS150                            | Motorcycles      | 1:18          | Studio M Art Models       |
| 1997 BMW R 1100 S                           | Motorcycles      | 1:24          | Autoart Studio Design     |
| 1982 Ducati 900 Monster                     | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 1974 Ducati 350 Mk3 Desmo                   | Motorcycles      | 1:32          | Second Gear Diecast       |
| 2002 Yamaha YZR M1                          | Motorcycles      | 1:50          | Autoart Studio Design     |
| 1968 Ford Mustang                           | Classic Cars     | 1:12          | Autoart Studio Design     |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1961 Chevrolet Impala                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1982 Lamborghini Diablo                     | Classic Cars     | 1:24          | Second Gear Diecast       |
| 1956 Porsche 356A Coupe                     | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1965 Aston Martin DB5                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1966 Shelby Cobra 427 S/C                   | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1952 Citroen-15CV                           | Classic Cars     | 1:24          | Exoto Designs             |
| 1969 Chevrolet Camaro Z28                   | Classic Cars     | 1:24          | Exoto Designs             |
| 2002 Chevy Corvette                         | Classic Cars     | 1:24          | Gearbox Collectibles      |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1934 Ford V8 Coupe                          | Vintage Cars     | 1:18          | Min Lin Diecast           |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1940 Ford Pickup Truck                      | Trucks and Buses | 1:18          | Studio M Art Models       |
| 1940s Ford truck                            | Trucks and Buses | 1:18          | Motor City Art Classics   |
| 1964 Mercedes Tour Bus                      | Trucks and Buses | 1:18          | Unimax Art Galleries      |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| 1969 Corvair Monza                          | Classic Cars     | 1:18          | Welly Diecast Productions |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1972 Alfa Romeo GTA                         | Classic Cars     | 1:10          | Motor City Art Classics   |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| Pont Yacht                                  | Ships            | 1:72          | Unimax Art Galleries      |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1969 Dodge Super Bee                        | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1957 Corvette Convertible                   | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1974 Ducati 350 Mk3 Desmo                   | Motorcycles      | 1:32          | Second Gear Diecast       |
| 1968 Ford Mustang                           | Classic Cars     | 1:12          | Autoart Studio Design     |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1993 Mazda RX-7                             | Classic Cars     | 1:18          | Highway 66 Mini Classics  |
| 1965 Aston Martin DB5                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1971 Alpine Renault 1600s                   | Classic Cars     | 1:24          | Welly Diecast Productions |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1917 Maxwell Touring Car                    | Vintage Cars     | 1:18          | Exoto Designs             |
| 1939 Cadillac Limousine                     | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1996 Peterbilt 379 Stake Bed with Outrigger | Trucks and Buses | 1:32          | Red Start Diecast         |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1950's Chicago Surface Lines Streetcar      | Trains           | 1:32          | Gearbox Collectibles      |
| 1962 City of Detroit Streetcar              | Trains           | 1:50          | Classic Metal Creations   |
| 1972 Alfa Romeo GTA                         | Classic Cars     | 1:10          | Motor City Art Classics   |
| 1904 Buick Runabout                         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1912 Ford Model T Delivery Wagon            | Vintage Cars     | 1:24          | Min Lin Diecast           |
| The Titanic                                 | Ships            | 1:700         | Carousel DieCast Legends  |
| Pont Yacht                                  | Ships            | 1:72          | Unimax Art Galleries      |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| F/A 18 Hornet 1/72                          | Planes           | 1:72          | Motor City Art Classics   |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| 1900s Vintage Tri-Plane                     | Planes           | 1:24          | Unimax Art Galleries      |
| 1957 Corvette Convertible                   | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1993 Mazda RX-7                             | Classic Cars     | 1:18          | Highway 66 Mini Classics  |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1966 Shelby Cobra 427 S/C                   | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1956 Porsche 356A Coupe                     | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1952 Alpine Renault 1300                    | Classic Cars     | 1:10          | Classic Metal Creations   |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1996 Peterbilt 379 Stake Bed with Outrigger | Trucks and Buses | 1:32          | Red Start Diecast         |
| 1926 Ford Fire Engine                       | Trucks and Buses | 1:18          | Carousel DieCast Legends  |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1969 Corvair Monza                          | Classic Cars     | 1:18          | Welly Diecast Productions |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| 18th century schooner                       | Ships            | 1:24          | Carousel DieCast Legends  |
| 1912 Ford Model T Delivery Wagon            | Vintage Cars     | 1:24          | Min Lin Diecast           |
| The Schooner Bluenose                       | Ships            | 1:700         | Autoart Studio Design     |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| The Queen Mary                              | Ships            | 1:700         | Welly Diecast Productions |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| 1997 BMW R 1100 S                           | Motorcycles      | 1:24          | Autoart Studio Design     |
| 1928 British Royal Navy Airplane            | Planes           | 1:24          | Classic Metal Creations   |
| 1900s Vintage Tri-Plane                     | Planes           | 1:24          | Unimax Art Galleries      |
| 1997 BMW F650 ST                            | Motorcycles      | 1:32          | Exoto Designs             |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| 1971 Alpine Renault 1600s                   | Classic Cars     | 1:24          | Welly Diecast Productions |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 2002 Yamaha YZR M1                          | Motorcycles      | 1:50          | Autoart Studio Design     |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1965 Aston Martin DB5                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1995 Honda Civic                            | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1956 Porsche 356A Coupe                     | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1940 Ford Pickup Truck                      | Trucks and Buses | 1:18          | Studio M Art Models       |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1917 Grand Touring Sedan                    | Vintage Cars     | 1:18          | Welly Diecast Productions |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1936 Chrysler Airflow                       | Vintage Cars     | 1:24          | Second Gear Diecast       |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1926 Ford Fire Engine                       | Trucks and Buses | 1:18          | Carousel DieCast Legends  |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1940s Ford truck                            | Trucks and Buses | 1:18          | Motor City Art Classics   |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| 1958 Chevy Corvette Limited Edition         | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1982 Camaro Z28                             | Classic Cars     | 1:18          | Carousel DieCast Legends  |
| 1969 Corvair Monza                          | Classic Cars     | 1:18          | Welly Diecast Productions |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1972 Alfa Romeo GTA                         | Classic Cars     | 1:10          | Motor City Art Classics   |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| The Titanic                                 | Ships            | 1:700         | Carousel DieCast Legends  |
| 1928 British Royal Navy Airplane            | Planes           | 1:24          | Classic Metal Creations   |
| Corsair F4U ( Bird Cage)                    | Planes           | 1:24          | Second Gear Diecast       |
| 1900s Vintage Tri-Plane                     | Planes           | 1:24          | Unimax Art Galleries      |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| F/A 18 Hornet 1/72                          | Planes           | 1:72          | Motor City Art Classics   |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| 1936 Harley Davidson El Knucklehead         | Motorcycles      | 1:18          | Welly Diecast Productions |
| 1974 Ducati 350 Mk3 Desmo                   | Motorcycles      | 1:32          | Second Gear Diecast       |
| 1968 Ford Mustang                           | Classic Cars     | 1:12          | Autoart Studio Design     |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1995 Honda Civic                            | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1948 Porsche Type 356 Roadster              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1971 Alpine Renault 1600s                   | Classic Cars     | 1:24          | Welly Diecast Productions |
| 1965 Aston Martin DB5                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1917 Maxwell Touring Car                    | Vintage Cars     | 1:18          | Exoto Designs             |
| 1926 Ford Fire Engine                       | Trucks and Buses | 1:18          | Carousel DieCast Legends  |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1939 Cadillac Limousine                     | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1982 Camaro Z28                             | Classic Cars     | 1:18          | Carousel DieCast Legends  |
| 1957 Chevy Pickup                           | Trucks and Buses | 1:12          | Exoto Designs             |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1969 Corvair Monza                          | Classic Cars     | 1:18          | Welly Diecast Productions |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 18th century schooner                       | Ships            | 1:24          | Carousel DieCast Legends  |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| 1972 Alfa Romeo GTA                         | Classic Cars     | 1:10          | Motor City Art Classics   |
| The Schooner Bluenose                       | Ships            | 1:700         | Autoart Studio Design     |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| 1941 Chevrolet Special Deluxe Cabriolet     | Vintage Cars     | 1:18          | Exoto Designs             |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| 1930 Buick Marquette Phaeton                | Vintage Cars     | 1:50          | Studio M Art Models       |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| F/A 18 Hornet 1/72                          | Planes           | 1:72          | Motor City Art Classics   |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1900s Vintage Tri-Plane                     | Planes           | 1:24          | Unimax Art Galleries      |
| 1997 BMW F650 ST                            | Motorcycles      | 1:32          | Exoto Designs             |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| 1969 Harley Davidson Ultimate Chopper       | Motorcycles      | 1:10          | Min Lin Diecast           |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1966 Shelby Cobra 427 S/C                   | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 2002 Chevy Corvette                         | Classic Cars     | 1:24          | Gearbox Collectibles      |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1932 Model A Ford J-Coupe                   | Vintage Cars     | 1:18          | Autoart Studio Design     |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1934 Ford V8 Coupe                          | Vintage Cars     | 1:18          | Min Lin Diecast           |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1940s Ford truck                            | Trucks and Buses | 1:18          | Motor City Art Classics   |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| 18th century schooner                       | Ships            | 1:24          | Carousel DieCast Legends  |
| 1972 Alfa Romeo GTA                         | Classic Cars     | 1:10          | Motor City Art Classics   |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1997 BMW F650 ST                            | Motorcycles      | 1:32          | Exoto Designs             |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| F/A 18 Hornet 1/72                          | Planes           | 1:72          | Motor City Art Classics   |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1997 BMW R 1100 S                           | Motorcycles      | 1:24          | Autoart Studio Design     |
| 1982 Ducati 900 Monster                     | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 2002 Yamaha YZR M1                          | Motorcycles      | 1:50          | Autoart Studio Design     |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1995 Honda Civic                            | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1969 Dodge Super Bee                        | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1965 Aston Martin DB5                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1949 Jaguar XK 120                          | Classic Cars     | 1:24          | Classic Metal Creations   |
| 1969 Chevrolet Camaro Z28                   | Classic Cars     | 1:24          | Exoto Designs             |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1964 Mercedes Tour Bus                      | Trucks and Buses | 1:18          | Unimax Art Galleries      |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1940s Ford truck                            | Trucks and Buses | 1:18          | Motor City Art Classics   |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| 1912 Ford Model T Delivery Wagon            | Vintage Cars     | 1:24          | Min Lin Diecast           |
| 1980s Black Hawk Helicopter                 | Planes           | 1:18          | Red Start Diecast         |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| 1928 British Royal Navy Airplane            | Planes           | 1:24          | Classic Metal Creations   |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| 1960 BSA Gold Star DBD34                    | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 1974 Ducati 350 Mk3 Desmo                   | Motorcycles      | 1:32          | Second Gear Diecast       |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1971 Alpine Renault 1600s                   | Classic Cars     | 1:24          | Welly Diecast Productions |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1995 Honda Civic                            | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1948 Porsche Type 356 Roadster              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 2002 Chevy Corvette                         | Classic Cars     | 1:24          | Gearbox Collectibles      |
| 1956 Porsche 356A Coupe                     | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1940 Ford Pickup Truck                      | Trucks and Buses | 1:18          | Studio M Art Models       |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1969 Corvair Monza                          | Classic Cars     | 1:18          | Welly Diecast Productions |
| 1957 Chevy Pickup                           | Trucks and Buses | 1:12          | Exoto Designs             |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| 1950's Chicago Surface Lines Streetcar      | Trains           | 1:32          | Gearbox Collectibles      |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| 1980s Black Hawk Helicopter                 | Planes           | 1:18          | Red Start Diecast         |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| The USS Constitution Ship                   | Ships            | 1:700         | Red Start Diecast         |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1957 Vespa GS150                            | Motorcycles      | 1:18          | Studio M Art Models       |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1948 Porsche Type 356 Roadster              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1982 Lamborghini Diablo                     | Classic Cars     | 1:24          | Second Gear Diecast       |
| 1971 Alpine Renault 1600s                   | Classic Cars     | 1:24          | Welly Diecast Productions |
| 1956 Porsche 356A Coupe                     | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 2002 Yamaha YZR M1                          | Motorcycles      | 1:50          | Autoart Studio Design     |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1934 Ford V8 Coupe                          | Vintage Cars     | 1:18          | Min Lin Diecast           |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1966 Shelby Cobra 427 S/C                   | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 1952 Alpine Renault 1300                    | Classic Cars     | 1:10          | Classic Metal Creations   |
| 1940 Ford Pickup Truck                      | Trucks and Buses | 1:18          | Studio M Art Models       |
| 1939 Cadillac Limousine                     | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| 1972 Alfa Romeo GTA                         | Classic Cars     | 1:10          | Motor City Art Classics   |
| 1904 Buick Runabout                         | Vintage Cars     | 1:18          | Exoto Designs             |
| 18th century schooner                       | Ships            | 1:24          | Carousel DieCast Legends  |
| 1962 City of Detroit Streetcar              | Trains           | 1:50          | Classic Metal Creations   |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1997 BMW R 1100 S                           | Motorcycles      | 1:24          | Autoart Studio Design     |
| 1928 British Royal Navy Airplane            | Planes           | 1:24          | Classic Metal Creations   |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| The Schooner Bluenose                       | Ships            | 1:700         | Autoart Studio Design     |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 1995 Honda Civic                            | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1969 Dodge Super Bee                        | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1957 Vespa GS150                            | Motorcycles      | 1:18          | Studio M Art Models       |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1966 Shelby Cobra 427 S/C                   | Classic Cars     | 1:24          | Carousel DieCast Legends  |
| 1982 Ducati 996 R                           | Motorcycles      | 1:32          | Gearbox Collectibles      |
| 1932 Alfa Romeo 8C2300 Spider Sport         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1949 Jaguar XK 120                          | Classic Cars     | 1:24          | Classic Metal Creations   |
| 1952 Citroen-15CV                           | Classic Cars     | 1:24          | Exoto Designs             |
| 1969 Chevrolet Camaro Z28                   | Classic Cars     | 1:24          | Exoto Designs             |
| 2002 Chevy Corvette                         | Classic Cars     | 1:24          | Gearbox Collectibles      |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1917 Maxwell Touring Car                    | Vintage Cars     | 1:18          | Exoto Designs             |
| 1939 Cadillac Limousine                     | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1972 Alfa Romeo GTA                         | Classic Cars     | 1:10          | Motor City Art Classics   |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| 1950's Chicago Surface Lines Streetcar      | Trains           | 1:32          | Gearbox Collectibles      |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| The USS Constitution Ship                   | Ships            | 1:700         | Red Start Diecast         |
| The Queen Mary                              | Ships            | 1:700         | Welly Diecast Productions |
| Pont Yacht                                  | Ships            | 1:72          | Unimax Art Galleries      |
| 1941 Chevrolet Special Deluxe Cabriolet     | Vintage Cars     | 1:18          | Exoto Designs             |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| American Airlines: MD-11S                   | Planes           | 1:700         | Second Gear Diecast       |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1928 British Royal Navy Airplane            | Planes           | 1:24          | Classic Metal Creations   |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1969 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1936 Harley Davidson El Knucklehead         | Motorcycles      | 1:18          | Welly Diecast Productions |
| 1997 BMW R 1100 S                           | Motorcycles      | 1:24          | Autoart Studio Design     |
| 1960 BSA Gold Star DBD34                    | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1957 Corvette Convertible                   | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1961 Chevrolet Impala                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1995 Honda Civic                            | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1932 Model A Ford J-Coupe                   | Vintage Cars     | 1:18          | Autoart Studio Design     |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 2002 Yamaha YZR M1                          | Motorcycles      | 1:50          | Autoart Studio Design     |
| 1917 Maxwell Touring Car                    | Vintage Cars     | 1:18          | Exoto Designs             |
| 1940s Ford truck                            | Trucks and Buses | 1:18          | Motor City Art Classics   |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1964 Mercedes Tour Bus                      | Trucks and Buses | 1:18          | Unimax Art Galleries      |
| 1970 Triumph Spitfire                       | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1982 Camaro Z28                             | Classic Cars     | 1:18          | Carousel DieCast Legends  |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1950's Chicago Surface Lines Streetcar      | Trains           | 1:32          | Gearbox Collectibles      |
| 1962 City of Detroit Streetcar              | Trains           | 1:50          | Classic Metal Creations   |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 1928 British Royal Navy Airplane            | Planes           | 1:24          | Classic Metal Creations   |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| The Mayflower                               | Ships            | 1:700         | Studio M Art Models       |
| 1969 Harley Davidson Ultimate Chopper       | Motorcycles      | 1:10          | Min Lin Diecast           |
| 1996 Moto Guzzi 1100i                       | Motorcycles      | 1:10          | Highway 66 Mini Classics  |
| Corsair F4U ( Bird Cage)                    | Planes           | 1:24          | Second Gear Diecast       |
| 1900s Vintage Tri-Plane                     | Planes           | 1:24          | Unimax Art Galleries      |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1936 Harley Davidson El Knucklehead         | Motorcycles      | 1:18          | Welly Diecast Productions |
| 1948 Porsche 356-A Roadster                 | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1957 Corvette Convertible                   | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1960 BSA Gold Star DBD34                    | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1971 Alpine Renault 1600s                   | Classic Cars     | 1:24          | Welly Diecast Productions |
| 1974 Ducati 350 Mk3 Desmo                   | Motorcycles      | 1:32          | Second Gear Diecast       |
| 1932 Model A Ford J-Coupe                   | Vintage Cars     | 1:18          | Autoart Studio Design     |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1939 Chevrolet Deluxe Coupe                 | Vintage Cars     | 1:24          | Motor City Art Classics   |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 2002 Chevy Corvette                         | Classic Cars     | 1:24          | Gearbox Collectibles      |
| 1934 Ford V8 Coupe                          | Vintage Cars     | 1:18          | Min Lin Diecast           |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1940 Ford Pickup Truck                      | Trucks and Buses | 1:18          | Studio M Art Models       |
| 1964 Mercedes Tour Bus                      | Trucks and Buses | 1:18          | Unimax Art Galleries      |
| 1926 Ford Fire Engine                       | Trucks and Buses | 1:18          | Carousel DieCast Legends  |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1940s Ford truck                            | Trucks and Buses | 1:18          | Motor City Art Classics   |
| 1939 Cadillac Limousine                     | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1996 Peterbilt 379 Stake Bed with Outrigger | Trucks and Buses | 1:32          | Red Start Diecast         |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1954 Greyhound Scenicruiser                 | Trucks and Buses | 1:32          | Classic Metal Creations   |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 1962 City of Detroit Streetcar              | Trains           | 1:50          | Classic Metal Creations   |
| 1980s Black Hawk Helicopter                 | Planes           | 1:18          | Red Start Diecast         |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| 1940 Ford Delivery Sedan                    | Vintage Cars     | 1:24          | Carousel DieCast Legends  |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| Pont Yacht                                  | Ships            | 1:72          | Unimax Art Galleries      |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| 1936 Harley Davidson El Knucklehead         | Motorcycles      | 1:18          | Welly Diecast Productions |
| 1969 Harley Davidson Ultimate Chopper       | Motorcycles      | 1:10          | Min Lin Diecast           |
| 1960 BSA Gold Star DBD34                    | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1982 Ducati 900 Monster                     | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 1970 Plymouth Hemi Cuda                     | Classic Cars     | 1:12          | Studio M Art Models       |
| 1969 Dodge Super Bee                        | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1957 Vespa GS150                            | Motorcycles      | 1:18          | Studio M Art Models       |
| 1911 Ford Town Car                          | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1999 Indy 500 Monte Carlo SS                | Classic Cars     | 1:18          | Red Start Diecast         |
| 1937 Lincoln Berline                        | Vintage Cars     | 1:18          | Motor City Art Classics   |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 1957 Ford Thunderbird                       | Classic Cars     | 1:18          | Studio M Art Models       |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 1958 Setra Bus                              | Trucks and Buses | 1:12          | Welly Diecast Productions |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1962 Volkswagen Microbus                    | Trucks and Buses | 1:24          | Autoart Studio Design     |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1964 Mercedes Tour Bus                      | Trucks and Buses | 1:18          | Unimax Art Galleries      |
| 1903 Ford Model A                           | Vintage Cars     | 1:18          | Unimax Art Galleries      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 1904 Buick Runabout                         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1992 Porsche Cayenne Turbo Silver           | Classic Cars     | 1:24          | Exoto Designs             |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| 18th century schooner                       | Ships            | 1:24          | Carousel DieCast Legends  |
| The Schooner Bluenose                       | Ships            | 1:700         | Autoart Studio Design     |
| 1980s Black Hawk Helicopter                 | Planes           | 1:18          | Red Start Diecast         |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| 1941 Chevrolet Special Deluxe Cabriolet     | Vintage Cars     | 1:18          | Exoto Designs             |
| HMS Bounty                                  | Ships            | 1:700         | Unimax Art Galleries      |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| 1930 Buick Marquette Phaeton                | Vintage Cars     | 1:50          | Studio M Art Models       |
| 1968 Ford Mustang                           | Classic Cars     | 1:12          | Autoart Studio Design     |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1928 Mercedes-Benz SSK                      | Vintage Cars     | 1:18          | Gearbox Collectibles      |
| 2002 Yamaha YZR M1                          | Motorcycles      | 1:50          | Autoart Studio Design     |
| 1952 Alpine Renault 1300                    | Classic Cars     | 1:10          | Classic Metal Creations   |
| 1940 Ford Pickup Truck                      | Trucks and Buses | 1:18          | Studio M Art Models       |
| 1938 Cadillac V-16 Presidential Limousine   | Vintage Cars     | 1:24          | Classic Metal Creations   |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1982 Camaro Z28                             | Classic Cars     | 1:18          | Carousel DieCast Legends  |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| Collectable Wooden Train                    | Trains           | 1:18          | Carousel DieCast Legends  |
| 1912 Ford Model T Delivery Wagon            | Vintage Cars     | 1:24          | Min Lin Diecast           |
| The USS Constitution Ship                   | Ships            | 1:700         | Red Start Diecast         |
| 1999 Yamaha Speed Boat                      | Ships            | 1:18          | Min Lin Diecast           |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| F/A 18 Hornet 1/72                          | Planes           | 1:72          | Motor City Art Classics   |
| 2017 Harley-Davidson Eagle Drag Bike        | Motorcycles      | 1:10          | Red Start Diecast         |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| Boeing X-32A JSF                            | Planes           | 1:72          | Motor City Art Classics   |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| ATA: B757-300                               | Planes           | 1:700         | Highway 66 Mini Classics  |
| 1969 Harley Davidson Ultimate Chopper       | Motorcycles      | 1:10          | Min Lin Diecast           |
| 1982 Ducati 900 Monster                     | Motorcycles      | 1:24          | Highway 66 Mini Classics  |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1932 Alfa Romeo 8C2300 Spider Sport         | Vintage Cars     | 1:18          | Exoto Designs             |
| 1970 Chevy Chevelle SS 454                  | Classic Cars     | 1:24          | Unimax Art Galleries      |
| 1969 Chevrolet Camaro Z28                   | Classic Cars     | 1:24          | Exoto Designs             |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1932 Model A Ford J-Coupe                   | Vintage Cars     | 1:18          | Autoart Studio Design     |
| 1952 Alpine Renault 1300                    | Classic Cars     | 1:10          | Classic Metal Creations   |
| 1962 LanciaA Delta 16V                      | Classic Cars     | 1:10          | Second Gear Diecast       |
| 1940 Ford Pickup Truck                      | Trucks and Buses | 1:18          | Studio M Art Models       |
| 1980?s GM Manhattan Express                 | Trucks and Buses | 1:32          | Motor City Art Classics   |
| 1996 Peterbilt 379 Stake Bed with Outrigger | Trucks and Buses | 1:32          | Red Start Diecast         |
| 1970 Dodge Coronet                          | Classic Cars     | 1:24          | Highway 66 Mini Classics  |
| 1954 Greyhound Scenicruiser                 | Trucks and Buses | 1:32          | Classic Metal Creations   |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
| 1969 Ford Falcon                            | Classic Cars     | 1:12          | Second Gear Diecast       |
| 1950's Chicago Surface Lines Streetcar      | Trains           | 1:32          | Gearbox Collectibles      |
| The Titanic                                 | Ships            | 1:700         | Carousel DieCast Legends  |
| 1900s Vintage Bi-Plane                      | Planes           | 1:24          | Autoart Studio Design     |
| 1937 Horch 930V Limousine                   | Vintage Cars     | 1:24          | Autoart Studio Design     |
| 1980s Black Hawk Helicopter                 | Planes           | 1:18          | Red Start Diecast         |
| P-51-D Mustang                              | Planes           | 1:72          | Gearbox Collectibles      |
| Corsair F4U ( Bird Cage)                    | Planes           | 1:24          | Second Gear Diecast       |
| 1928 Ford Phaeton Deluxe                    | Vintage Cars     | 1:32          | Highway 66 Mini Classics  |
| American Airlines: B767-300                 | Planes           | 1:700         | Min Lin Diecast           |
| America West Airlines B757-200              | Planes           | 1:700         | Motor City Art Classics   |
| 2002 Suzuki XREO                            | Motorcycles      | 1:12          | Unimax Art Galleries      |
| 1969 Dodge Super Bee                        | Classic Cars     | 1:18          | Min Lin Diecast           |
| 1976 Ford Gran Torino                       | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1957 Corvette Convertible                   | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1961 Chevrolet Impala                       | Classic Cars     | 1:18          | Classic Metal Creations   |
| 1968 Ford Mustang                           | Classic Cars     | 1:12          | Autoart Studio Design     |
| 1968 Dodge Charger                          | Classic Cars     | 1:12          | Welly Diecast Productions |
| 1982 Lamborghini Diablo                     | Classic Cars     | 1:24          | Second Gear Diecast       |
| 2002 Chevy Corvette                         | Classic Cars     | 1:24          | Gearbox Collectibles      |
| 1936 Mercedes Benz 500k Roadster            | Vintage Cars     | 1:24          | Red Start Diecast         |
| 1936 Mercedes-Benz 500K Special Roadster    | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1913 Ford Model T Speedster                 | Vintage Cars     | 1:18          | Carousel DieCast Legends  |
| 18th Century Vintage Horse Carriage         | Vintage Cars     | 1:18          | Red Start Diecast         |
| 1917 Maxwell Touring Car                    | Vintage Cars     | 1:18          | Exoto Designs             |
| 1936 Chrysler Airflow                       | Vintage Cars     | 1:24          | Second Gear Diecast       |
| 1939 Cadillac Limousine                     | Vintage Cars     | 1:18          | Studio M Art Models       |
| 1998 Chrysler Plymouth Prowler              | Classic Cars     | 1:18          | Gearbox Collectibles      |
| 1926 Ford Fire Engine                       | Trucks and Buses | 1:18          | Carousel DieCast Legends  |
| 1992 Ferrari 360 Spider red                 | Classic Cars     | 1:18          | Unimax Art Galleries      |
| 1954 Greyhound Scenicruiser                 | Trucks and Buses | 1:32          | Classic Metal Creations   |
| Diamond T620 Semi-Skirted Tanker            | Trucks and Buses | 1:50          | Highway 66 Mini Classics  |
+---------------------------------------------+------------------+---------------+---------------------------+
976 rows in set (0.00 sec)

```
</details>




<details><summary>Question 9 : It is noted that the payment (check number OM314922) was actually 2575. Update the record.</summary>
  
  ## QUERY : 
``` 
 UPDATE payments SET amount=2575 WHERE check_number='OM314933';
```

## RESULT 
```
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

```
</details>




<details><summary>Question 10 : Fetch the details of salesmen/employees dealing with customers whose orders are resolved.</summary>
  
  ## QUERY : 
``` 
     SELECT employees.employee_id, CONCAT(employees.first_name, ' ',employees.last_name) AS employees_name, employees.email, employees.job_title, employees.extension  FROM employees 
        INNER JOIN customers ON employees.employee_id=customers.sales_employee_id
        INNER JOIN orders ON orders.customer_id=customers.customer_id
        WHERE orders.status <> 'IN Process';

```

## RESULT 
```
+-------------+------------------+--------------------------+-----------+-----------+
| employee_id | employees_name   | email                    | job_title | extension |
+-------------+------------------+--------------------------+-----------+-----------+
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1165 | Leslie Jennings  | ljennings@lcomotors.com  | Sales Rep | x3291     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1166 | Leslie Thompson  | lthompson@lcomotors.com  | Sales Rep | x4065     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1188 | Julie Firrelli   | jfirrelli@lcomotors.com  | Sales Rep | x2173     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1216 | Steve Patterson  | spatterson@lcomotors.com | Sales Rep | x4334     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1286 | Foon Yue Tseng   | ftseng@lcomotors.com     | Sales Rep | x2248     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1323 | George Vanauf    | gvanauf@lcomotors.com    | Sales Rep | x4102     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1337 | Loui Bondur      | lbondur@lcomotors.com    | Sales Rep | x6493     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1370 | Gerard Hernandez | ghernande@lcomotors.com  | Sales Rep | x2028     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1401 | Pamela Castillo  | pcastillo@lcomotors.com  | Sales Rep | x2759     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1501 | Larry Bott       | lbott@lcomotors.com      | Sales Rep | x2311     |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1504 | Barry Jones      | bjones@lcomotors.com     | Sales Rep | x102      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1611 | Andy Fixter      | afixter@lcomotors.com    | Sales Rep | x101      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1612 | Peter Marsh      | pmarsh@lcomotors.com     | Sales Rep | x102      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1621 | Mami Nishi       | mnishi@lcomotors.com     | Sales Rep | x101      |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
|        1702 | Martin Gerard    | mgerard@lcomotors.com    | Sales Rep | x2312     |
+-------------+------------------+--------------------------+-----------+-----------+
316 rows in set (0.01 sec)

```
</details>




<details><summary>Question 11 : Get the details of the customer who made the maximum payment.</summary>
  
  ## QUERY : 
``` 
        SELECT customers.* FROM customers 
        INNER JOIN payments ON payments.customer_id=customers.customer_id
        ORDER BY payments.amount DESC LIMIT 1;
```

## RESULT 
```
+-------------+------------------------+-----------+------------+----------------+--------------------+---------------+--------+-------+-------------+---------+-------------------+--------------+
| customer_id | customer_name          | last_name | first_name | phone          | address_line1      | address_line2 | city   | state | postal_code | country | sales_employee_id | credit_limit |
+-------------+------------------------+-----------+------------+----------------+--------------------+---------------+--------+-------+-------------+---------+-------------------+--------------+
|         141 | Euro+ Shopping Channel | Freyre    | Diego      | (91) 555 94 44 | C/ Moralzarzal, 86 | NULL          | Madrid | NULL  | 28034       | Spain   |              1370 |    227600.00 |
+-------------+------------------------+-----------+------------+----------------+--------------------+---------------+--------+-------+-------------+---------+-------------------+--------------+
1 row in set (0.01 sec)

```
</details>




<details><summary>Question 12 : Fetch list of orders shipped to France.</summary>
  
  ## QUERY : 
``` 

        SELECT orders.* FROM orders 
        INNER JOIN customers ON customers.customer_id=orders.customer_id
        WHERE customers.country='France' AND orders.status='Shipped';
```

## RESULT 
```
+----------+------------+---------------+--------------+---------+--------------------------------------------------------------------------------------------------+-------------+
| order_id | order_date | required_date | shipped_date | status  | comments                                                                                         | customer_id |
+----------+------------+---------------+--------------+---------+--------------------------------------------------------------------------------------------------+-------------+
|    10123 | 2017-05-20 | 2017-05-29    | 2017-05-22   | Shipped | NULL                                                                                             |         103 |
|    10298 | 2018-09-27 | 2018-10-05    | 2018-10-01   | Shipped | NULL                                                                                             |         103 |
|    10345 | 2018-11-25 | 2018-12-01    | 2018-11-26   | Shipped | NULL                                                                                             |         103 |
|    10275 | 2018-07-23 | 2018-08-02    | 2018-07-29   | Shipped | NULL                                                                                             |         119 |
|    10315 | 2018-10-29 | 2018-11-08    | 2018-10-30   | Shipped | NULL                                                                                             |         119 |
|    10375 | 2019-02-03 | 2019-02-10    | 2019-02-06   | Shipped | NULL                                                                                             |         119 |
|    10194 | 2017-11-25 | 2017-12-02    | 2017-11-26   | Shipped | NULL                                                                                             |         146 |
|    10208 | 2018-01-02 | 2018-01-11    | 2018-01-04   | Shipped | NULL                                                                                             |         146 |
|    10227 | 2018-03-02 | 2018-03-12    | 2018-03-08   | Shipped | NULL                                                                                             |         146 |
|    10180 | 2017-11-11 | 2017-11-19    | 2017-11-14   | Shipped | NULL                                                                                             |         171 |
|    10224 | 2018-02-21 | 2018-03-02    | 2018-02-26   | Shipped | Customer has worked with some of our vendors in the past and is aware of their mrp               |         171 |
|    10114 | 2017-04-01 | 2017-04-07    | 2017-04-02   | Shipped | NULL                                                                                             |         172 |
|    10286 | 2018-08-28 | 2018-09-06    | 2018-09-01   | Shipped | NULL                                                                                             |         172 |
|    10336 | 2018-11-20 | 2018-11-26    | 2018-11-24   | Shipped | Customer requested that DHL is used for this shipping                                            |         172 |
|    10241 | 2018-04-13 | 2018-04-20    | 2018-04-19   | Shipped | NULL                                                                                             |         209 |
|    10255 | 2018-06-04 | 2018-06-12    | 2018-06-09   | Shipped | NULL                                                                                             |         209 |
|    10405 | 2019-04-14 | 2019-04-24    | 2019-04-20   | Shipped | NULL                                                                                             |         209 |
|    10136 | 2017-07-04 | 2017-07-14    | 2017-07-06   | Shipped | Customer is interested in buying more Ferrari models                                             |         242 |
|    10178 | 2017-11-08 | 2017-11-16    | 2017-11-10   | Shipped | Custom shipping instructions sent to warehouse                                                   |         242 |
|    10397 | 2019-03-28 | 2019-04-09    | 2019-04-01   | Shipped | NULL                                                                                             |         242 |
|    10134 | 2017-07-01 | 2017-07-10    | 2017-07-05   | Shipped | NULL                                                                                             |         250 |
|    10356 | 2018-12-09 | 2018-12-15    | 2018-12-12   | Shipped | NULL                                                                                             |         250 |
|    10395 | 2019-03-17 | 2019-03-24    | 2019-03-23   | Shipped | We must be cautions with this customer. Their VP of Sales resigned. Company may be heading down. |         250 |
|    10216 | 2018-02-02 | 2018-02-10    | 2018-02-04   | Shipped | NULL                                                                                             |         256 |
|    10304 | 2018-10-11 | 2018-10-20    | 2018-10-17   | Shipped | NULL                                                                                             |         256 |
|    10122 | 2017-05-08 | 2017-05-16    | 2017-05-13   | Shipped | NULL                                                                                             |         350 |
|    10344 | 2018-11-25 | 2018-12-02    | 2018-11-29   | Shipped | NULL                                                                                             |         350 |
|    10364 | 2019-01-06 | 2019-01-17    | 2019-01-09   | Shipped | NULL                                                                                             |         350 |
|    10121 | 2017-05-07 | 2017-05-13    | 2017-05-13   | Shipped | NULL                                                                                             |         353 |
|    10137 | 2017-07-10 | 2017-07-20    | 2017-07-14   | Shipped | NULL                                                                                             |         353 |
|    10343 | 2018-11-24 | 2018-12-01    | 2018-11-26   | Shipped | NULL                                                                                             |         353 |
|    10359 | 2018-12-15 | 2018-12-23    | 2018-12-18   | Shipped | NULL                                                                                             |         353 |
|    10398 | 2019-03-30 | 2019-04-09    | 2019-03-31   | Shipped | NULL                                                                                             |         353 |
|    10211 | 2018-01-15 | 2018-01-25    | 2018-01-18   | Shipped | NULL                                                                                             |         406 |
|    10252 | 2018-05-26 | 2018-06-04    | 2018-05-29   | Shipped | NULL                                                                                             |         406 |
|    10402 | 2019-04-07 | 2019-04-14    | 2019-04-12   | Shipped | NULL                                                                                             |         406 |
+----------+------------+---------------+--------------+---------+--------------------------------------------------------------------------------------------------+-------------+
36 rows in set (0.00 sec)

```
</details>




<details><summary>Question 13 : How many customers and from Finland who placed orders.</summary>
  
  ## QUERY : 
``` 
     SELECT COUNT(*) FROM orders 
        INNER JOIN customers ON customers.customer_id=orders.customer_id
        WHERE customers.country='Finland';


```

## RESULT 
```
+----------+
| COUNT(*) |
+----------+
|        9 |
+----------+
1 row in set (0.00 sec)

```
</details>




<details><summary>Question 14 : Get the details of the customer who made the maximum payment.</summary>
  
  ## QUERY : 
``` 
        SELECT customers.* FROM customers
        INNER JOIN payments ON customers.customer_id=customers.customer_id
        ORDER BY payments.amount DESC LIMIT 1;

```

## RESULT 
```
+-------------+-------------------+-----------+------------+------------+----------------+---------------+--------+-------+-------------+---------+-------------------+--------------+
| customer_id | customer_name     | last_name | first_name | phone      | address_line1  | address_line2 | city   | state | postal_code | country | sales_employee_id | credit_limit |
+-------------+-------------------+-----------+------------+------------+----------------+---------------+--------+-------+-------------+---------+-------------------+--------------+
|         103 | Atelier graphique | Schmitt   | Carine     | 40.32.2555 | 54, rue Royale | NULL          | Nantes | NULL  | 44000       | France  |              1370 |     21000.00 |
+-------------+-------------------+-----------+------------+------------+----------------+---------------+--------+-------+-------------+---------+-------------------+--------------+
1 row in set (0.03 sec)

```
</details>




<details>
<summary>Question 15 : Get the details of the customer and payments they made between may 2019 and june 2019.</summary>
  
  ## QUERY : 
``` 
        SELECT customers.*, payments.payment_date FROM customers
        INNER JOIN payments ON payments.customer_id=customers.customer_id
        WHERE payments.payment_date BETWEEN '2019-05-01 00:00:00' AND '2019-06-01 00:00:00';


```

## RESULT 
```
+-------------+------------------------------+-----------+-------------+------------------+-------------------------------+---------------+-------------+--------+-------------+-------------+-------------------+--------------+--------------+
| customer_id | customer_name                | last_name | first_name  | phone            | address_line1                 | address_line2 | city        | state  | postal_code | country     | sales_employee_id | credit_limit | payment_date |
+-------------+------------------------------+-----------+-------------+------------------+-------------------------------+---------------+-------------+--------+-------------+-------------+-------------------+--------------+--------------+
|         141 | Euro+ Shopping Channel       | Freyre    | Diego       | (91) 555 94 44   | C/ Moralzarzal, 86            | NULL          | Madrid      | NULL   | 28034       | Spain       |              1370 |    227600.00 | 2019-05-19   |
|         175 | Gift Depot Inc.              | King      | Julie       | 2035552570       | 25593 South Bay Ln.           | NULL          | Bridgewater | CT     | 97562       | USA         |              1323 |     84300.00 | 2019-05-19   |
|         209 | Mini Caravy                  | Citeaux   | Frédérique  | 88.60.1555       | 24, place Kléber              | NULL          | Strasbourg  | NULL   | 67000       | France      |              1370 |     53800.00 | 2019-05-03   |
|         233 | Québec Home Shopping Network | Fresnière | Jean        | (514) 555-8054   | 43 rue St. Laurent            | NULL          | Montréal    | Québec | H1J 1C3     | Canada      |              1286 |     48700.00 | 2019-05-20   |
|         250 | Lyon Souveniers              | Da Silva  | Daniel      | +33 1 46 62 7555 | 27 rue du Colonel Pierre Avia | NULL          | Paris       | NULL   | 75508       | France      |              1337 |     68100.00 | 2019-05-17   |
|         323 | Down Under Souveniers, Inc   | Graham    | Mike        | +64 9 312 5555   | 162-164 Grafton Road          | Level 2       | Auckland    | NULL   | NULL        | New Zealand |              1612 |     88000.00 | 2019-05-23   |
|         398 | Tokyo Collectables, Ltd      | Shimamura | Akiko       | +81 3 3584 0555  | 2-2-8 Roppongi                | NULL          | Minato-ku   | Tokyo  | 106-0032    | Japan       |              1621 |     94400.00 | 2019-05-18   |
|         452 | Mini Auto Werke              | Mendel    | Roland      | 7675-3555        | Kirchgasse 6                  | NULL          | Graz        | NULL   | 8010        | Austria     |              1401 |     45300.00 | 2019-05-03   |
|         496 | Kelly's Gift Shop            | Snowden   | Tony        | +64 9 5555500    | Arenales 1938 3'A'            | NULL          | Auckland    | NULL   | NULL        | New Zealand |              1612 |    110000.00 | 2019-05-25   |
+-------------+------------------------------+-----------+-------------+------------------+-------------------------------+---------------+-------------+--------+-------------+-------------+-------------------+--------------+--------------+
9 rows in set (0.00 sec)

```
</details>




<details><summary>Question 16 : How many orders shipped to Belgium in 2018?</summary>
  
  ## QUERY : 
``` 
        SELECT COUNT(*) FROM orders
        INNER JOIN customers ON customers.customer_id=orders.customer_id
        WHERE customers.country='Belgium' AND  YEAR(orders.shipped_date) ='2018';
```

## RESULT 
```
+----------+
| COUNT(*) |
+----------+
|        3 |
+----------+
1 row in set (0.00 sec)

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


