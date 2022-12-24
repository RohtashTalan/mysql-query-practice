# Films Sql Query practice 


<details>
  <summary>Question 1 : Which categories of movies released in 2018? Fetch with number of movies</summary>
  
  ## QUERY : 
``` 
SELECT film.film_id, film.title, film_category.category_id, category.name AS category_name, COUNT(category.category_id) AS Number_of_films from ((film
LEFT JOIN film_category on film_category.film_id = film.film_id ) 
LEFT JOIN category ON film_category.category_id = category.category_id) WHERE film.release_year=2018 GROUP BY category.category_id;
```

## RESULT 
```
+---------+-------------------+-------------+---------------+-----------------+
| film_id | title             | category_id | category_name | Number_of_films |
+---------+-------------------+-------------+---------------+-----------------+
|       2 | ACE GOLDFINGER    |          11 | Horror        |               2 |
|     118 | CANYON STOCK      |           2 | Animation     |               3 |
|     119 | CAPER MOTIONS     |           5 | Comedy        |               2 |
|     120 | CARIBBEAN LIBERTY |          15 | Sports        |               2 |
|     123 | CASABLANCA SUPER  |          16 | Travel        |               2 |
|     124 | CASPER DRAGONFLY  |           3 | Children      |               1 |
|     126 | CASUALTIES ENCINO |           1 | Action        |               2 |
|     128 | CATCH AMISTAD     |           9 | Foreign       |               1 |
|     129 | CAUSE DATE        |           6 | Documentary   |               1 |
|     131 | CENTER DINOSAUR   |           4 | Classics      |               1 |
|     132 | CHAINSAW UPTOWN   |          14 | Sci-Fi        |               4 |
|     133 | CHAMBER ITALIAN   |          12 | Music         |               1 |
|     136 | CHAPLIN LICENSE   |          13 | New           |               1 |
|     139 | CHASING FIGHT     |           8 | Family        |               1 |
+---------+-------------------+-------------+---------------+-----------------+

```
</details>




<details>
  <summary>Question 2 : Update the address of actor id 36 to "677 Jazz Street"</summary>
  
  ## QUERY : 
``` 
 UPDATE address LEFT JOIN actor ON actor.address_id=address.address_id SET address.address='677 Jazz Street', address.address2='' WHERE actor.actor_id=36;
```

## RESULT 
```
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

```
</details>


<details>
  <summary>Question 3 : Add the new actors (id: 105, 95) in film ARSENIC INDEPENDENCE(id:41)</summary>
  
  ## QUERY : 
``` 
INSERT INTO film_actor(actor_id, film_id) VALUE (105,41),(95, 41);
```

## RESULT 
```
Query OK, 2 rows affected (0.01 sec)
Records: 2  Duplicates: 0  Warnings: 0
--
SELECT * FROM film_actor WHERE film_id=41;
+----------+---------+---------------------+
| actor_id | film_id | last_update         |
+----------+---------+---------------------+
|       95 |      41 | 2022-12-23 19:58:41 |
|      105 |      41 | 2022-12-23 19:58:41 |
|      118 |      41 | 2020-07-30 18:07:54 |
|      135 |      41 | 2020-07-30 18:07:54 |
|      162 |      41 | 2020-07-30 18:07:54 |
+----------+---------+---------------------+

```
</details>


<details>
  <summary>Question 4 : Get the name of films of the actors who belong to India</summary>
  
  ## QUERY : 
``` 
 SELECT DISTINCT film.title, country.country from ((((((
    film LEFT JOIN film_actor ON film_actor.film_id=film.film_id)
   LEFT JOIN actor ON film_actor.actor_id=actor.actor_id)
   LEFT JOIN address ON actor.address_id = address.address_id)
   LEFT JOIN city ON city.city_id = address.city_id)
   LEFT JOIN country ON city.country_id = country.country_id)
   ) WHERE country.country ='India' ;

```

## RESULT 
```
+---------------------------+---------+
| title                     | country |
+---------------------------+---------+
| BORN SPINAL               | India   |
| CHITTY LOCK               | India   |
| CLYDE THEORY              | India   |
| COAST RAINBOW             | India   |
| CRAZY HOME                | India   |
| FACTORY DRAGON            | India   |
| FERRIS MOTHER             | India   |
| GONE TROUBLE              | India   |
| GREEK EVERYONE            | India   |
| HOOSIERS BIRDCAGE         | India   |
| MOB DUFFEL                | India   |
| OPEN AFRICAN              | India   |
| PRIX UNDEFEATED           | India   |
| ROCKY WAR                 | India   |
| SHRUNK DIVINE             | India   |
| SKY MIRACLE               | India   |
| TELEMARK HEARTBREAKERS    | India   |
| WISDOM WORKER             | India   |
| AIRPORT POLLOCK           | India   |
| ANONYMOUS HUMAN           | India   |
| BIRD INDEPENDENCE         | India   |
| CRUSADE HONEY             | India   |
| FELLOWSHIP AUTUMN         | India   |
| FLAMINGOS CONNECTICUT     | India   |
| FRONTIER CABIN            | India   |
| HARRY IDAHO               | India   |
| JERSEY SASSY              | India   |
| JET NEIGHBORS             | India   |
| MOVIE SHAKESPEARE         | India   |
| MUSSOLINI SPOILERS        | India   |
| NEMO CAMPUS               | India   |
| RACER EGG                 | India   |
| SECRET GROUNDHOG          | India   |
| SHOOTIST SUPERFLY         | India   |
| SNATCHERS MONTEZUMA       | India   |
| SPICE SORORITY            | India   |
| VACATION BOONDOCK         | India   |
| WATCH TRACY               | India   |
| ALIEN CENTER              | India   |
| BLINDNESS GUN             | India   |
| COMMANDMENTS EXPRESS      | India   |
| DINOSAUR SECRETARY        | India   |
| DOUBLE WRATH              | India   |
| ENDING CROWDS             | India   |
| GRINCH MASSAGE            | India   |
| GUN BONNIE                | India   |
| GUYS FALCON               | India   |
| HEAVEN FREEDOM            | India   |
| HOME PITY                 | India   |
| HOMEWARD CIDER            | India   |
| IMAGE PRINCESS            | India   |
| INTOLERABLE INTENTIONS    | India   |
| JERK PAYCHECK             | India   |
| KANE EXORCIST             | India   |
| KING EVOLUTION            | India   |
| MENAGERIE RUSHMORE        | India   |
| MONEY HAROLD              | India   |
| MOTIONS DETAILS           | India   |
| RANDOM GO                 | India   |
| RANGE MOONWALKER          | India   |
| REAP UNFAITHFUL           | India   |
| RIGHT CRANES              | India   |
| TALENTED HOMICIDE         | India   |
| TRUMAN CRAZY              | India   |
| VALENTINE VANISHING       | India   |
| WANDA CHAMBER             | India   |
| BABY HALL                 | India   |
| BLADE POLISH              | India   |
| CHICAGO NORTH             | India   |
| CONFUSED CANDLES          | India   |
| DIRTY ACE                 | India   |
| DOGMA FAMILY              | India   |
| FIRE WOLVES               | India   |
| FROGMEN BREAKING          | India   |
| GLEAMING JAWBREAKER       | India   |
| GUMP DATE                 | India   |
| HATE HANDICAP             | India   |
| INDEPENDENCE HOTEL        | India   |
| KILL BROTHERHOOD          | India   |
| MARS ROMAN                | India   |
| MIGHTY LUCK               | India   |
| MYSTIC TRUMAN             | India   |
| PARK CITIZEN              | India   |
| PARTY KNOCK               | India   |
| PINOCCHIO SIMON           | India   |
| POCUS PULP                | India   |
| POND SEATTLE              | India   |
| QUEEN LUKE                | India   |
| SHREK LICENSE             | India   |
| SORORITY QUEEN            | India   |
| SPIRIT FLINTSTONES        | India   |
| SWEET BROTHERHOOD         | India   |
| TEEN APOLLO               | India   |
| TRAMP OTHERS              | India   |
| WARDROBE PHANTOM          | India   |
| ADAPTATION HOLES          | India   |
| BLUES INSTINCT            | India   |
| CALENDAR GUNFIGHT         | India   |
| CASUALTIES ENCINO         | India   |
| CHOCOLATE DUCK            | India   |
| CONNECTION MICROCOSMOS    | India   |
| CROW GREASE               | India   |
| CUPBOARD SINNERS          | India   |
| DOOM DANCING              | India   |
| DROP WATERFRONT           | India   |
| ELEPHANT TROJAN           | India   |
| FREEDOM CLEOPATRA         | India   |
| HAUNTED ANTITRUST         | India   |
| INSTINCT AIRPORT          | India   |
| LEGALLY SECRETARY         | India   |
| PANIC CLUB                | India   |
| PURE RUNNER               | India   |
| SEVEN SWARM               | India   |
| SPINAL ROCKY              | India   |
| SPLASH GUMP               | India   |
| WEST LION                 | India   |
| ALTER VICTORY             | India   |
| BERETS AGENT              | India   |
| BOULEVARD MOB             | India   |
| BRINGING HYSTERICAL       | India   |
| BULL SHAWSHANK            | India   |
| CASABLANCA SUPER          | India   |
| CASSIDY WYOMING           | India   |
| CAT CONEHEADS             | India   |
| CELEBRITY HORN            | India   |
| CHANCE RESURRECTION       | India   |
| CORE SUIT                 | India   |
| DAY UNFAITHFUL            | India   |
| DETECTIVE VISION          | India   |
| DUDE BLINDNESS            | India   |
| EDGE KISSING              | India   |
| EVOLUTION ALTER           | India   |
| EXORCIST STING            | India   |
| FIDDLER LOST              | India   |
| HALLOWEEN NUTS            | India   |
| HANGING DEEP              | India   |
| JACKET FRISCO             | India   |
| KWAI HOMEWARD             | India   |
| LUCKY FLYING              | India   |
| MOTHER OLEANDER           | India   |
| PEAK FOREVER              | India   |
| PULP BEVERLY              | India   |
| RUSH GOODFELLAS           | India   |
| SASSY PACKER              | India   |
| SHAWSHANK BUBBLE          | India   |
| STEPMOM DREAM             | India   |
| TOMATOES HELLFIGHTERS     | India   |
| WAIT CIDER                | India   |
| ALADDIN CALENDAR          | India   |
| ALASKA PHANTOM            | India   |
| AMADEUS HOLY              | India   |
| CANYON STOCK              | India   |
| CAPER MOTIONS             | India   |
| CARRIE BUNCH              | India   |
| DALMATIONS SWEDEN         | India   |
| DRIFTER COMMANDMENTS      | India   |
| FIREBALL PHILADELPHIA     | India   |
| INTRIGUE WORST            | India   |
| JAWBREAKER BROOKLYN       | India   |
| LAMBS CINCINATTI          | India   |
| LONELY ELEPHANT           | India   |
| MAKER GABLES              | India   |
| MALLRATS UNITED           | India   |
| METROPOLIS COMA           | India   |
| MODEL FISH                | India   |
| PATHS CONTROL             | India   |
| PATIENT SISTER            | India   |
| PREJUDICE OLEANDER        | India   |
| PRIMARY GLASS             | India   |
| STALLION SUNDANCE         | India   |
| STAMPEDE DISTURBING       | India   |
| STRANGER STRANGERS        | India   |
| TOWN ARK                  | India   |
| UNITED PILOT              | India   |
| WEDDING APOLLO            | India   |
| WORKING MICROCOSMOS       | India   |
| YOUTH KICK                | India   |
| AGENT TRUMAN              | India   |
| BOONDOCK BALLROOM         | India   |
| CHICKEN HELLFIGHTERS      | India   |
| CLOSER BANG               | India   |
| CONQUERER NUTS            | India   |
| ENCINO ELF                | India   |
| FLASH WARS                | India   |
| HANOVER GALAXY            | India   |
| HONEY TIES                | India   |
| LADYBUGS ARMAGEDDON       | India   |
| LORD ARIZONA              | India   |
| PLUTO OLEANDER            | India   |
| RIVER OUTLAW              | India   |
| ROAD ROXANNE              | India   |
| SILVERADO GOLDFINGER      | India   |
| SLEEPING SUSPECTS         | India   |
| THIEF PELICAN             | India   |
| TITANS JERK               | India   |
| UNBREAKABLE KARATE        | India   |
| WON DARES                 | India   |
| BACKLASH UNDEFEATED       | India   |
| BETRAYED REAR             | India   |
| CATCH AMISTAD             | India   |
| DIVIDE MONSTER            | India   |
| DOORS PRESIDENT           | India   |
| DRIVER ANNIE              | India   |
| FEATHERS METAL            | India   |
| HILLS NEIGHBORS           | India   |
| INNOCENT USUAL            | India   |
| LUKE MUMMY                | India   |
| MAGNOLIA FORRESTER        | India   |
| MAIDEN HOME               | India   |
| MILLION ACE               | India   |
| MOURNING PURPLE           | India   |
| NUTS TIES                 | India   |
| OKLAHOMA JUMANJI          | India   |
| OPERATION OPERATION       | India   |
| PRINCESS GIANT            | India   |
| RESERVOIR ADAPTATION      | India   |
| SABRINA MIDNIGHT          | India   |
| SINNERS ATLANTIS          | India   |
| STREETCAR INTENTIONS      | India   |
| SUBMARINE BED             | India   |
| ACE GOLDFINGER            | India   |
| CHINATOWN GLADIATOR       | India   |
| CIRCUS YOUTH              | India   |
| CONTROL ANTHEM            | India   |
| DARES PLUTO               | India   |
| DARN FORRESTER            | India   |
| DAZED PUNK                | India   |
| DYNAMITE TARZAN           | India   |
| HOMICIDE PEACH            | India   |
| JUMANJI BLADE             | India   |
| LAWLESS VISION            | India   |
| LEATHERNECKS DWARFS       | India   |
| OSCAR GOLD                | India   |
| PELICAN COMFORTS          | India   |
| PERSONAL LADYBUGS         | India   |
| RAGING AIRPLANE           | India   |
| RUN PACIFIC               | India   |
| RUNNER MADIGAN            | India   |
| SADDLE ANTITRUST          | India   |
| SCORPION APOLLO           | India   |
| TAXI KICK                 | India   |
| ALICE FANTASIA            | India   |
| BILL OTHERS               | India   |
| BONNIE HOLOCAUST          | India   |
| BOWFINGER GABLES          | India   |
| EVERYONE CRAFT            | India   |
| EXPRESS LONELY            | India   |
| EXTRAORDINARY CONQUERER   | India   |
| FRIDA SLIPPER             | India   |
| GROOVE FICTION            | India   |
| HOLIDAY GAMES             | India   |
| HYSTERICAL GRAIL          | India   |
| INSECTS STONE             | India   |
| JAPANESE RUN              | India   |
| JAWS HARRY                | India   |
| LIFE TWISTED              | India   |
| MADIGAN DORADO            | India   |
| MANNEQUIN WORST           | India   |
| MONSOON CAUSE             | India   |
| NOTTING SPEAKEASY         | India   |
| PICKUP DRIVING            | India   |
| SANTA PARIS               | India   |
| SMOKING BARBARELLA        | India   |
| SUSPECTS QUILLS           | India   |
| TOMORROW HUSTLER          | India   |
| WAR NOTTING               | India   |
| WARS PLUTO                | India   |
| AFFAIR PREJUDICE          | India   |
| BIRDCAGE CASPER           | India   |
| COMMAND DARLING           | India   |
| CROSSROADS CASUALTIES     | India   |
| DISTURBING SCARFACE       | India   |
| FARGO GANDHI              | India   |
| REAR TRADING              | India   |
| SONG HEDWIG               | India   |
| TEMPLE ATTRACTION         | India   |
| TRAP GUYS                 | India   |
| USUAL UNTOUCHABLES        | India   |
| VICTORY ACADEMY           | India   |
| WEREWOLF LOLA             | India   |
| CLOCKWORK PARADISE        | India   |
| CLUE GRAIL                | India   |
| DANGEROUS UPTOWN          | India   |
| DRAGON SQUAD              | India   |
| MERMAID INSECTS           | India   |
| MUMMY CREATURES           | India   |
| PANKY SUBMARINE           | India   |
| PILOT HOOSIERS            | India   |
| REBEL AIRPORT             | India   |
| REDS POCUS                | India   |
| SWARM GOLD                | India   |
| WAGON JAWS                | India   |
| WASH HEAVENLY             | India   |
| BEAST HUNCHBACK           | India   |
| BENEATH RUSH              | India   |
| CREATURES SHAKESPEARE     | India   |
| DRIVING POLISH            | India   |
| DURHAM PANKY              | India   |
| EGYPT TENENBAUMS          | India   |
| EVE RESURRECTION          | India   |
| JUMPING WRATH             | India   |
| KARATE MOON               | India   |
| LAWRENCE LOVE             | India   |
| MEMENTO ZOOLANDER         | India   |
| MURDER ANTITRUST          | India   |
| NATURAL STOCK             | India   |
| PANTHER REDS              | India   |
| SAINTS BRIDE              | India   |
| SEARCHERS WAIT            | India   |
| SHINING ROSES             | India   |
| SPIKING ELEMENT           | India   |
| STAR OPERATION            | India   |
| UPTOWN YOUNG              | India   |
| VALLEY PACKER             | India   |
| VANISHING ROCKY           | India   |
| VIDEOTAPE ARSENIC         | India   |
| WIZARD COLDBLOODED        | India   |
| WONDERFUL DROP            | India   |
| WORKER TARZAN             | India   |
| ARMAGEDDON LOST           | India   |
| BUTTERFLY CHOCOLAT        | India   |
| CARIBBEAN LIBERTY         | India   |
| CLASH FREDDY              | India   |
| CLEOPATRA DEVIL           | India   |
| HARPER DYING              | India   |
| HEARTBREAKERS BRIGHT      | India   |
| JINGLE SAGEBRUSH          | India   |
| LOLA AGENT                | India   |
| MONSTER SPARTACUS         | India   |
| NONE SPIKING              | India   |
| NOTORIOUS REUNION         | India   |
| ORANGE GRAPES             | India   |
| PAST SUICIDES             | India   |
| PATRIOT ROMAN             | India   |
| POTLUCK MIXED             | India   |
| RAINBOW SHOCK             | India   |
| RUGRATS SHAKESPEARE       | India   |
| SOUP WISDOM               | India   |
| UNFAITHFUL KILL           | India   |
| BREAKFAST GOLDFINGER      | India   |
| CRANES RESERVOIR          | India   |
| DIVORCE SHINING           | India   |
| HOLLOW JEOPARDY           | India   |
| JEOPARDY ENCINO           | India   |
| MAJESTIC FLOATS           | India   |
| MINDS TRUMAN              | India   |
| OUTLAW HANKY              | India   |
| RIDER CADDYSHACK          | India   |
| WYOMING STORM             | India   |
| BALLROOM MOCKINGBIRD      | India   |
| BARBARELLA STREETCAR      | India   |
| BOOGIE AMELIE             | India   |
| GO PURPLE                 | India   |
| HAROLD FRENCH             | India   |
| HORN WORKING              | India   |
| INDIAN LOVE               | India   |
| MASSACRE USUAL            | India   |
| OZ LIAISONS               | India   |
| PITY BOUND                | India   |
| PIZZA JUMANJI             | India   |
| RUNAWAY TENENBAUMS        | India   |
| SATISFACTION CONFIDENTIAL | India   |
| SATURDAY LAMBS            | India   |
| TREATMENT JEKYLL          | India   |
| APOCALYPSE FLAMINGOS      | India   |
| ARMY FLINTSTONES          | India   |
| BILKO ANONYMOUS           | India   |
| CALIFORNIA BIRDS          | India   |
| FIDELITY DEVIL            | India   |
| GUNFIGHT MOON             | India   |
| GUNFIGHTER MUSSOLINI      | India   |
| KENTUCKIAN GIANT          | India   |
| LICENSE WEEKEND           | India   |
| OLEANDER CLUE             | India   |
| STORY SIDE                | India   |
| SUMMER SCARFACE           | India   |
| TROUBLE DATE              | India   |
| VOLCANO TEXAS             | India   |
| ATLANTIS CAUSE            | India   |
| BLOOD ARGONAUTS           | India   |
| FINDING ANACONDA          | India   |
| GREATEST NORTH            | India   |
| JUNGLE CLOSER             | India   |
| LANGUAGE COWBOY           | India   |
| LEAGUE HELLFIGHTERS       | India   |
| LIBERTY MAGNIFICENT       | India   |
| LOST BIRD                 | India   |
| MAGNIFICENT CHITTY        | India   |
| NORTHWEST POLISH          | India   |
| SHIP WONDERLAND           | India   |
| SONS INTERVIEW            | India   |
| TENENBAUMS COMMAND        | India   |
| TOOTSIE PILOT             | India   |
| TOWERS HURRICANE          | India   |
| BOILED DARES              | India   |
| CHISUM BEHAVIOR           | India   |
| HOPE TOOTSIE              | India   |
| MULAN MOON                | India   |
| OPUS ICE                  | India   |
| POLLOCK DELIVERANCE       | India   |
| RIDGEMONT SUBMARINE       | India   |
| SHANGHAI TYCOON           | India   |
| THEORY MERMAID            | India   |
| ALLEY EVOLUTION           | India   |
| BEVERLY OUTLAW            | India   |
| CANDLES GRAPES            | India   |
| COLOR PHILADELPHIA        | India   |
| DAUGHTER MADIGAN          | India   |
| GOLDMINE TYCOON           | India   |
| INTERVIEW LIAISONS        | India   |
| ISHTAR ROCKETEER          | India   |
| NAME DETECTIVE            | India   |
| NECKLACE OUTBREAK         | India   |
| NEWSIES STORY             | India   |
| PET HAUNTING              | India   |
| PIANIST OUTFIELD          | India   |
| PITTSBURGH HUNCHBACK      | India   |
| QUILLS BULL               | India   |
| ROXANNE REBEL             | India   |
| ACADEMY DINOSAUR          | India   |
| BALLOON HOMEWARD          | India   |
| BUBBLE GROSSE             | India   |
| CADDYSHACK JEDI           | India   |
| DANCING FEVER             | India   |
| DESIRE ALIEN              | India   |
| FICTION CHRISTMAS         | India   |
| FLATLINERS KILLER         | India   |
| FRISCO FORREST            | India   |
| HEAVYWEIGHTS BEAST        | India   |
| LADY STAGE                | India   |
| LESSON CLEOPATRA          | India   |
| MAUDE MOD                 | India   |
| MONTEREY LABYRINTH        | India   |
| SCISSORHANDS SLUMS        | India   |
| SEABISCUIT PUNK           | India   |
| STORM HAPPINESS           | India   |
| BEACH HEARTBREAKERS       | India   |
| BORROWERS BEDAZZLED       | India   |
| DOWNHILL ENOUGH           | India   |
| EARRING INSTINCT          | India   |
| GENTLEMEN STAGE           | India   |
| HELLFIGHTERS SIERRA       | India   |
| HOLY TADPOLE              | India   |
| IRON MOON                 | India   |
| LOCK REAR                 | India   |
| PEARL DESTINY             | India   |
| RULES HUMAN               | India   |
| SLEUTH ORIENT             | India   |
| SPEAKEASY DATE            | India   |
| UNCUT SUICIDES            | India   |
| UNFORGIVEN ZOOLANDER      | India   |
| UPRISING UPTOWN           | India   |
+---------------------------+---------+
452 rows in set (0.00 sec)

```
</details>


<details>
  <summary>Question 5 : How many actors are from United States</summary>
  
  ## QUERY : 
``` 
   SELECT COUNT(actor.actor_id) AS Actors_from_USA FROM actor INNER JOIN address ON actor.address_id = address.address_id INNER JOIN city ON address.city_id=city.city_id INNER JOIN country ON country.country_id=city.country_id WHERE country.country = 'United States';
```

## RESULT

```
+-----------------+
| Actors_from_USA |
+-----------------+
|              18 |
+-----------------+
1 row in set (0.00 sec)

```
</details>


<details>
  <summary>Question 6 : Get all languages in which films are released in the year between 2001 and 2010</summary>
  
  ## QUERY : 
``` 
SELECT DISTINCT language.name FROM language INNER JOIN film ON language.language_id=film.language_id WHERE film.release_year BETWEEN 2001 AND 2010;

```

## RESULT 
```
+----------+
| name     |
+----------+
| English  |
| Italian  |
| Japanese |
| French   |
| Mandarin |
+----------+
5 rows in set (0.00 sec)

```
</details>


<details>
  <summary>Question 7 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 8 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 9 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 10 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 11 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 12 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 13 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 14 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 15 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 16 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 17 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 18 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 19 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 20 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 21 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 22 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>



<details>
  <summary>Question 23 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>



<details>
  <summary>Question 24 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 25 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 26 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 27 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 28 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 29 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>


<details>
  <summary>Question 30 : </summary>
  
  ## QUERY : 
``` 
```

## RESULT 
```


```
</details>
