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
  <summary>Question 7 : The film ALONE TRIP (id:17) was actually released in Mandarin, update the info</summary>
  
  ## QUERY : 
``` 
 UPDATE film SET film.language_id=(SELECT language_id from language WHERE language.name='Mandarin') WHERE film_id=17;
```

## RESULT 
```
Query OK, 1 row affected (0.02 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from film where film_id=17;
+---------+------------+-------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+----------------------------+---------------------+
| film_id | title      | description                                                                                           | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features           | last_update         |
+---------+------------+-------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+----------------------------+---------------------+
|      17 | ALONE TRIP | A Fast-Paced Character Study of a Composer And a Dog who must Outgun a Boat in An Abandoned Fun House |         2016 |           4 |                 NULL |               3 |        0.99 |     82 |            14.99 | R      | Trailers,Behind the Scenes | 2022-12-24 12:06:16 |
+---------+------------+-------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+----------------------------+---------------------+
1 row in set (0.00 sec)

```
</details>


<details>
  <summary>Question 8 : Fetch cast details of films released during 2005 and 2015 with PG rating</summary>
  
  ## QUERY : 
``` 
   SELECT CONCAT(actor.first_name, ' ',actor.last_name) AS Actor_Name, film.title AS Film_Name, film.release_year, film.rating FROM actor INNER JOIN film_actor ON film_actor.actor_id=actor.actor_id INNER JOIN film ON film.film_id=film_actor.film_id WHERE rating='PG' AND release_year BETWEEN 2005 AND 2015 ORDER BY film.release_year;

```

## RESULT 
```
+----------------------+------------------------+--------------+--------+
| Actor_Name           | Film_Name              | release_year | rating |
+----------------------+------------------------+--------------+--------+
| FRANCES DAY-LEWIS    | BRINGING HYSTERICAL    |         2005 | PG     |
| ANGELA WITHERSPOON   | BRINGING HYSTERICAL    |         2005 | PG     |
| RIP CRAWFORD         | BUCKET BROTHERHOOD     |         2005 | PG     |
| TIM HACKMAN          | BUCKET BROTHERHOOD     |         2005 | PG     |
| GARY PHOENIX         | BUCKET BROTHERHOOD     |         2005 | PG     |
| CHARLIZE DENCH       | BUCKET BROTHERHOOD     |         2005 | PG     |
| KIRSTEN AKROYD       | BUCKET BROTHERHOOD     |         2005 | PG     |
| BURT TEMPLE          | BUCKET BROTHERHOOD     |         2005 | PG     |
| JULIA MCQUEEN        | EFFECT GLADIATOR       |         2007 | PG     |
| ALEC WAYNE           | EFFECT GLADIATOR       |         2007 | PG     |
| NICK STALLONE        | EFFECT GLADIATOR       |         2007 | PG     |
| JULIA BARRYMORE      | EFFECT GLADIATOR       |         2007 | PG     |
| RENEE TRACY          | EFFECT GLADIATOR       |         2007 | PG     |
| OLYMPIA PFEIFFER     | EFFECT GLADIATOR       |         2007 | PG     |
| LISA MONROE          | EFFECT GLADIATOR       |         2007 | PG     |
| LUCILLE TRACY        | EGG IGBY               |         2007 | PG     |
| TOM MCKELLEN         | EGG IGBY               |         2007 | PG     |
| NATALIE HOPKINS      | EGG IGBY               |         2007 | PG     |
| MERYL GIBSON         | EGG IGBY               |         2007 | PG     |
| OPRAH KILMER         | EGG IGBY               |         2007 | PG     |
| WARREN NOLTE         | POTTER CONNECTICUT     |         2007 | PG     |
| WARREN JACKMAN       | POTTER CONNECTICUT     |         2007 | PG     |
| CATE MCQUEEN         | POTTER CONNECTICUT     |         2007 | PG     |
| JANE JACKMAN         | POTTER CONNECTICUT     |         2007 | PG     |
| WHOOPI HURT          | POTTER CONNECTICUT     |         2007 | PG     |
| AL GARLAND           | POTTER CONNECTICUT     |         2007 | PG     |
| AUDREY BAILEY        | POTTER CONNECTICUT     |         2007 | PG     |
| CUBA OLIVIER         | EGYPT TENENBAUMS       |         2007 | PG     |
| GARY PENN            | EGYPT TENENBAUMS       |         2007 | PG     |
| KENNETH TORN         | EGYPT TENENBAUMS       |         2007 | PG     |
| SUSAN DAVIS          | EGYPT TENENBAUMS       |         2007 | PG     |
| CHRIS DEPP           | EGYPT TENENBAUMS       |         2007 | PG     |
| GOLDIE BRODY         | EVERYONE CRAFT         |         2007 | PG     |
| MICHELLE MCCONAUGHEY | EVERYONE CRAFT         |         2007 | PG     |
| WOODY JOLIE          | EVERYONE CRAFT         |         2007 | PG     |
| JAMES PITT           | EVERYONE CRAFT         |         2007 | PG     |
| MINNIE ZELLWEGER     | EVERYONE CRAFT         |         2007 | PG     |
| GRACE MOSTEL         | OPEN AFRICAN           |         2007 | PG     |
| JULIA MCQUEEN        | OPEN AFRICAN           |         2007 | PG     |
| SISSY SOBIESKI       | OPEN AFRICAN           |         2007 | PG     |
| JUDE CRUISE          | OPEN AFRICAN           |         2007 | PG     |
| MILLA KEITEL         | OPEN AFRICAN           |         2007 | PG     |
| GINA DEGENERES       | OPEN AFRICAN           |         2007 | PG     |
| ADAM HOPPER          | OPEN AFRICAN           |         2007 | PG     |
| VIVIEN BASINGER      | OPEN AFRICAN           |         2007 | PG     |
| JULIA ZELLWEGER      | OPEN AFRICAN           |         2007 | PG     |
| ZERO CAGE            | OLEANDER CLUE          |         2007 | PG     |
| SANDRA KILMER        | OLEANDER CLUE          |         2007 | PG     |
| PENELOPE PINKETT     | OLEANDER CLUE          |         2007 | PG     |
| SEAN WILLIAMS        | OLEANDER CLUE          |         2007 | PG     |
| GREG CHAPLIN         | OLEANDER CLUE          |         2007 | PG     |
| JIM MOSTEL           | OLEANDER CLUE          |         2007 | PG     |
| WARREN JACKMAN       | OLEANDER CLUE          |         2007 | PG     |
| EWAN GOODING         | OLEANDER CLUE          |         2007 | PG     |
| OPRAH KILMER         | OLEANDER CLUE          |         2007 | PG     |
| RUSSELL CLOSE        | OLEANDER CLUE          |         2007 | PG     |
| PENELOPE GUINESS     | OKLAHOMA JUMANJI       |         2007 | PG     |
| JENNIFER DAVIS       | OKLAHOMA JUMANJI       |         2007 | PG     |
| KARL BERRY           | OKLAHOMA JUMANJI       |         2007 | PG     |
| CUBA OLIVIER         | OKLAHOMA JUMANJI       |         2007 | PG     |
| RIP CRAWFORD         | OKLAHOMA JUMANJI       |         2007 | PG     |
| CHRISTIAN AKROYD     | OKLAHOMA JUMANJI       |         2007 | PG     |
| CARY MCCONAUGHEY     | OKLAHOMA JUMANJI       |         2007 | PG     |
| RICHARD PENN         | OKLAHOMA JUMANJI       |         2007 | PG     |
| BELA WALKEN          | OKLAHOMA JUMANJI       |         2007 | PG     |
| FRANCES DAY-LEWIS    | OTHERS SOUP            |         2007 | PG     |
| NATALIE HOPKINS      | OTHERS SOUP            |         2007 | PG     |
| BURT POSEY           | OTHERS SOUP            |         2007 | PG     |
| OLYMPIA PFEIFFER     | OTHERS SOUP            |         2007 | PG     |
| GOLDIE BRODY         | POLLOCK DELIVERANCE    |         2007 | PG     |
| CARMEN HUNT          | POLLOCK DELIVERANCE    |         2007 | PG     |
| DUSTIN TAUTOU        | POLLOCK DELIVERANCE    |         2007 | PG     |
| GROUCHO SINATRA      | POLLOCK DELIVERANCE    |         2007 | PG     |
| BURT TEMPLE          | POLLOCK DELIVERANCE    |         2007 | PG     |
| JULIA FAWCETT        | POLLOCK DELIVERANCE    |         2007 | PG     |
| VIVIEN BERGEN        | POLISH BROOKLYN        |         2007 | PG     |
| ELVIS MARX           | POLISH BROOKLYN        |         2007 | PG     |
| KEVIN BLOOM          | POLISH BROOKLYN        |         2007 | PG     |
| RIP CRAWFORD         | POLISH BROOKLYN        |         2007 | PG     |
| JAYNE NEESON         | POLISH BROOKLYN        |         2007 | PG     |
| RALPH CRUZ           | POLISH BROOKLYN        |         2007 | PG     |
| MORGAN WILLIAMS      | POLISH BROOKLYN        |         2007 | PG     |
| FAY WINSLET          | POLISH BROOKLYN        |         2007 | PG     |
| IAN TANDY            | POLISH BROOKLYN        |         2007 | PG     |
| ALAN DREYFUSS        | POLISH BROOKLYN        |         2007 | PG     |
| HUMPHREY WILLIS      | PIRATES ROXANNE        |         2007 | PG     |
| KIRSTEN PALTROW      | PINOCCHIO SIMON        |         2007 | PG     |
| REESE KILMER         | PINOCCHIO SIMON        |         2007 | PG     |
| RALPH CRUZ           | PINOCCHIO SIMON        |         2007 | PG     |
| ELLEN PRESLEY        | PINOCCHIO SIMON        |         2007 | PG     |
| CAMERON ZELLWEGER    | PINOCCHIO SIMON        |         2007 | PG     |
| MORGAN HOPKINS       | PINOCCHIO SIMON        |         2007 | PG     |
| RIVER DEAN           | PINOCCHIO SIMON        |         2007 | PG     |
| BEN HARRIS           | PINOCCHIO SIMON        |         2007 | PG     |
| MERYL GIBSON         | PINOCCHIO SIMON        |         2007 | PG     |
| LAURA BRODY          | PINOCCHIO SIMON        |         2007 | PG     |
| JOHN SUVARI          | PINOCCHIO SIMON        |         2007 | PG     |
| JULIA MCQUEEN        | PILOT HOOSIERS         |         2007 | PG     |
| WOODY HOFFMAN        | PILOT HOOSIERS         |         2007 | PG     |
| HENRY BERRY          | PILOT HOOSIERS         |         2007 | PG     |
| SPENCER PECK         | PILOT HOOSIERS         |         2007 | PG     |
| CAMERON ZELLWEGER    | PILOT HOOSIERS         |         2007 | PG     |
| DEBBIE AKROYD        | PILOT HOOSIERS         |         2007 | PG     |
| AUDREY BAILEY        | PILOT HOOSIERS         |         2007 | PG     |
| JODIE DEGENERES      | PET HAUNTING           |         2007 | PG     |
| GROUCHO SINATRA      | PET HAUNTING           |         2007 | PG     |
| MORGAN HOPKINS       | PET HAUNTING           |         2007 | PG     |
| BEN HARRIS           | PET HAUNTING           |         2007 | PG     |
| LAURA BRODY          | PET HAUNTING           |         2007 | PG     |
| NICK DEGENERES       | PET HAUNTING           |         2007 | PG     |
| JOHN SUVARI          | PET HAUNTING           |         2007 | PG     |
| BOB FAWCETT          | PELICAN COMFORTS       |         2007 | PG     |
| JULIA BARRYMORE      | PELICAN COMFORTS       |         2007 | PG     |
| GROUCHO SINATRA      | PELICAN COMFORTS       |         2007 | PG     |
| WHOOPI HURT          | PELICAN COMFORTS       |         2007 | PG     |
| RUSSELL TEMPLE       | PELICAN COMFORTS       |         2007 | PG     |
| AUDREY OLIVIER       | PEAK FOREVER           |         2007 | PG     |
| KENNETH PESCI        | PEAK FOREVER           |         2007 | PG     |
| ANGELA WITHERSPOON   | PEAK FOREVER           |         2007 | PG     |
| DEBBIE AKROYD        | PEAK FOREVER           |         2007 | PG     |
| GREGORY GOODING      | PEAK FOREVER           |         2007 | PG     |
| JOHNNY LOLLOBRIGIDA  | PATTON INTERVIEW       |         2007 | PG     |
| TOM MIRANDA          | PATTON INTERVIEW       |         2007 | PG     |
| HENRY BERRY          | PATTON INTERVIEW       |         2007 | PG     |
| RIP WINSLET          | PATTON INTERVIEW       |         2007 | PG     |
| SEAN WILLIAMS        | PATTON INTERVIEW       |         2007 | PG     |
| CATE MCQUEEN         | PATTON INTERVIEW       |         2007 | PG     |
| WHOOPI HURT          | PATTON INTERVIEW       |         2007 | PG     |
| GEOFFREY HESTON      | PATTON INTERVIEW       |         2007 | PG     |
| MICHAEL BOLGER       | PATTON INTERVIEW       |         2007 | PG     |
| CARMEN HUNT          | PATRIOT ROMAN          |         2007 | PG     |
| ALBERT NOLTE         | PATRIOT ROMAN          |         2007 | PG     |
| KIM ALLEN            | PATRIOT ROMAN          |         2007 | PG     |
| RENEE BALL           | PATRIOT ROMAN          |         2007 | PG     |
| VAL BOLGER           | PATHS CONTROL          |         2007 | PG     |
| ANNE CRONYN          | PATHS CONTROL          |         2007 | PG     |
| KIRSTEN AKROYD       | PATHS CONTROL          |         2007 | PG     |
| SUSAN DAVIS          | PATHS CONTROL          |         2007 | PG     |
| ROCK DUKAKIS         | PATHS CONTROL          |         2007 | PG     |
| RIVER DEAN           | PARTY KNOCK            |         2007 | PG     |
| CHRIS DEPP           | PARTY KNOCK            |         2007 | PG     |
| MEG HAWKE            | PAPI NECKLACE          |         2007 | PG     |
| MORGAN HOPKINS       | PAPI NECKLACE          |         2007 | PG     |
| CUBA ALLEN           | PAPI NECKLACE          |         2007 | PG     |
| BOB FAWCETT          | OSCAR GOLD             |         2007 | PG     |
| RIP CRAWFORD         | OSCAR GOLD             |         2007 | PG     |
| DUSTIN TAUTOU        | OSCAR GOLD             |         2007 | PG     |
| ELLEN PRESLEY        | OSCAR GOLD             |         2007 | PG     |
| HARVEY HOPE          | OSCAR GOLD             |         2007 | PG     |
| AL GARLAND           | OSCAR GOLD             |         2007 | PG     |
| CHRISTIAN NEESON     | OPPOSITE NECKLACE      |         2007 | PG     |
| MATTHEW LEIGH        | OPPOSITE NECKLACE      |         2007 | PG     |
| GROUCHO DUNST        | OPPOSITE NECKLACE      |         2007 | PG     |
| LUCILLE DEE          | OPPOSITE NECKLACE      |         2007 | PG     |
| GROUCHO WILLIAMS     | OPPOSITE NECKLACE      |         2007 | PG     |
| DEBBIE AKROYD        | OPPOSITE NECKLACE      |         2007 | PG     |
| GROUCHO SINATRA      | DYING MAKER            |         2007 | PG     |
| MICHAEL BOLGER       | DYING MAKER            |         2007 | PG     |
| KIRK JOVOVICH        | RUSH GOODFELLAS        |         2011 | PG     |
| MAE HOFFMAN          | RUSH GOODFELLAS        |         2011 | PG     |
| SYLVESTER DERN       | RUSH GOODFELLAS        |         2011 | PG     |
| ANGELA WITHERSPOON   | RUSH GOODFELLAS        |         2011 | PG     |
| ALAN DREYFUSS        | RUSH GOODFELLAS        |         2011 | PG     |
| KEVIN BLOOM          | SABRINA MIDNIGHT       |         2011 | PG     |
| CHRISTIAN AKROYD     | SABRINA MIDNIGHT       |         2011 | PG     |
| MEG HAWKE            | SABRINA MIDNIGHT       |         2011 | PG     |
| CHRIS DEPP           | SABRINA MIDNIGHT       |         2011 | PG     |
| LUCILLE TRACY        | BEDAZZLED MARRIED      |         2011 | PG     |
| GARY PHOENIX         | BEDAZZLED MARRIED      |         2011 | PG     |
| DAN HARRIS           | BEDAZZLED MARRIED      |         2011 | PG     |
| PENELOPE MONROE      | BEDAZZLED MARRIED      |         2011 | PG     |
| JAYNE NOLTE          | BEDAZZLED MARRIED      |         2011 | PG     |
| LAURENCE BULLOCK     | BEDAZZLED MARRIED      |         2011 | PG     |
| REESE WEST           | BEDAZZLED MARRIED      |         2011 | PG     |
| TIM HACKMAN          | BEHAVIOR RUNAWAY       |         2011 | PG     |
| REESE KILMER         | BEHAVIOR RUNAWAY       |         2011 | PG     |
| DARYL WAHLBERG       | BEHAVIOR RUNAWAY       |         2011 | PG     |
| RITA REYNOLDS        | BEHAVIOR RUNAWAY       |         2011 | PG     |
| ED GUINESS           | BEHAVIOR RUNAWAY       |         2011 | PG     |
| DUSTIN TAUTOU        | BILL OTHERS            |         2011 | PG     |
| MINNIE ZELLWEGER     | BILL OTHERS            |         2011 | PG     |
| CHRIS BRIDGES        | BILL OTHERS            |         2011 | PG     |
| RUSSELL TEMPLE       | BILL OTHERS            |         2011 | PG     |
| AL GARLAND           | BILL OTHERS            |         2011 | PG     |
| LAURENCE BULLOCK     | BILL OTHERS            |         2011 | PG     |
| JOE SWANK            | BIRCH ANTITRUST        |         2011 | PG     |
| WOODY HOFFMAN        | BIRCH ANTITRUST        |         2011 | PG     |
| DARYL WAHLBERG       | BIRCH ANTITRUST        |         2011 | PG     |
| EWAN GOODING         | BIRCH ANTITRUST        |         2011 | PG     |
| ALAN DREYFUSS        | BIRCH ANTITRUST        |         2011 | PG     |
| MATTHEW CARREY       | BIRCH ANTITRUST        |         2011 | PG     |
| SANDRA KILMER        | BLACKOUT PRIVATE       |         2011 | PG     |
| CARY MCCONAUGHEY     | BLACKOUT PRIVATE       |         2011 | PG     |
| CAMERON ZELLWEGER    | BLACKOUT PRIVATE       |         2011 | PG     |
| KENNETH HOFFMAN      | BLACKOUT PRIVATE       |         2011 | PG     |
| MATTHEW CARREY       | BLACKOUT PRIVATE       |         2011 | PG     |
| MARY TANDY           | QUEEN LUKE             |         2011 | PG     |
| RIP WINSLET          | QUEEN LUKE             |         2011 | PG     |
| SPENCER PECK         | QUEEN LUKE             |         2011 | PG     |
| EWAN GOODING         | QUEEN LUKE             |         2011 | PG     |
| RIVER DEAN           | QUEEN LUKE             |         2011 | PG     |
| JAYNE SILVERSTONE    | QUEEN LUKE             |         2011 | PG     |
| JULIA MCQUEEN        | PRESIDENT BANG         |         2011 | PG     |
| CUBA ALLEN           | PRESIDENT BANG         |         2011 | PG     |
| LUCILLE DEE          | PRESIDENT BANG         |         2011 | PG     |
| DEBBIE AKROYD        | PRESIDENT BANG         |         2011 | PG     |
| AUDREY BAILEY        | PRESIDENT BANG         |         2011 | PG     |
| NICK STALLONE        | PRIVATE DROP           |         2011 | PG     |
| KIRSTEN AKROYD       | PRIVATE DROP           |         2011 | PG     |
| ELLEN PRESLEY        | PRIVATE DROP           |         2011 | PG     |
| CAMERON ZELLWEGER    | PRIVATE DROP           |         2011 | PG     |
| JON CHASE            | PRIVATE DROP           |         2011 | PG     |
| CHRISTIAN GABLE      | PUNK DIVORCE           |         2011 | PG     |
| GOLDIE BRODY         | PUNK DIVORCE           |         2011 | PG     |
| CHRISTIAN NEESON     | PUNK DIVORCE           |         2011 | PG     |
| JAMES PITT           | PUNK DIVORCE           |         2011 | PG     |
| HARRISON BALE        | PUNK DIVORCE           |         2011 | PG     |
| MORGAN WILLIAMS      | PUNK DIVORCE           |         2011 | PG     |
| GEOFFREY HESTON      | PUNK DIVORCE           |         2011 | PG     |
| TOM MIRANDA          | RAINBOW SHOCK          |         2011 | PG     |
| DUSTIN TAUTOU        | RAINBOW SHOCK          |         2011 | PG     |
| KENNETH TORN         | RAINBOW SHOCK          |         2011 | PG     |
| JANE JACKMAN         | RAINBOW SHOCK          |         2011 | PG     |
| KIM ALLEN            | RAINBOW SHOCK          |         2011 | PG     |
| GRETA MALDEN         | RAINBOW SHOCK          |         2011 | PG     |
| RIP CRAWFORD         | RANGE MOONWALKER       |         2011 | PG     |
| BURT DUKAKIS         | RANGE MOONWALKER       |         2011 | PG     |
| PENELOPE MONROE      | RANGE MOONWALKER       |         2011 | PG     |
| RUSSELL CLOSE        | RANGE MOONWALKER       |         2011 | PG     |
| JAYNE NEESON         | RECORDS ZORRO          |         2011 | PG     |
| BEN WILLIS           | RECORDS ZORRO          |         2011 | PG     |
| MORGAN HOPKINS       | RECORDS ZORRO          |         2011 | PG     |
| RITA REYNOLDS        | RECORDS ZORRO          |         2011 | PG     |
| EWAN GOODING         | RECORDS ZORRO          |         2011 | PG     |
| CHRISTOPHER WEST     | RECORDS ZORRO          |         2011 | PG     |
| WILLIAM HACKMAN      | RECORDS ZORRO          |         2011 | PG     |
| MERYL ALLEN          | RECORDS ZORRO          |         2011 | PG     |
| MENA TEMPLE          | RESURRECTION SILVERADO |         2011 | PG     |
| MAE HOFFMAN          | RESURRECTION SILVERADO |         2011 | PG     |
| KEVIN GARLAND        | RESURRECTION SILVERADO |         2011 | PG     |
| RICHARD PENN         | RESURRECTION SILVERADO |         2011 | PG     |
| KENNETH HOFFMAN      | RESURRECTION SILVERADO |         2011 | PG     |
| UMA WOOD             | RIDER CADDYSHACK       |         2011 | PG     |
| ANNE CRONYN          | RIDER CADDYSHACK       |         2011 | PG     |
| SCARLETT DAMON       | RIDER CADDYSHACK       |         2011 | PG     |
| JAMES PITT           | RIDER CADDYSHACK       |         2011 | PG     |
| WHOOPI HURT          | RIDER CADDYSHACK       |         2011 | PG     |
| BEN HARRIS           | RIDER CADDYSHACK       |         2011 | PG     |
| WILLIAM HACKMAN      | RIDER CADDYSHACK       |         2011 | PG     |
| JEFF SILVERSTONE     | RIDER CADDYSHACK       |         2011 | PG     |
| JULIA ZELLWEGER      | RIDER CADDYSHACK       |         2011 | PG     |
| WOODY HOFFMAN        | ROOM ROMAN             |         2011 | PG     |
| SEAN WILLIAMS        | ROOM ROMAN             |         2011 | PG     |
| UMA WOOD             | CHINATOWN GLADIATOR    |         2012 | PG     |
| DAN TORN             | CHINATOWN GLADIATOR    |         2012 | PG     |
| BOB FAWCETT          | CHINATOWN GLADIATOR    |         2012 | PG     |
| JUDE CRUISE          | CHINATOWN GLADIATOR    |         2012 | PG     |
| JESSICA BAILEY       | CHINATOWN GLADIATOR    |         2012 | PG     |
| SEAN WILLIAMS        | CHINATOWN GLADIATOR    |         2012 | PG     |
| PENELOPE MONROE      | CHINATOWN GLADIATOR    |         2012 | PG     |
| GEOFFREY HESTON      | CHINATOWN GLADIATOR    |         2012 | PG     |
| JEFF SILVERSTONE     | CHINATOWN GLADIATOR    |         2012 | PG     |
| JAYNE SILVERSTONE    | CHINATOWN GLADIATOR    |         2012 | PG     |
| VAL BOLGER           | ALASKA PHANTOM         |         2012 | PG     |
| BURT POSEY           | ALASKA PHANTOM         |         2012 | PG     |
| SIDNEY CROWE         | ALASKA PHANTOM         |         2012 | PG     |
| SYLVESTER DERN       | ALASKA PHANTOM         |         2012 | PG     |
| ALBERT JOHANSSON     | ALASKA PHANTOM         |         2012 | PG     |
| GENE MCKELLEN        | ALASKA PHANTOM         |         2012 | PG     |
| JEFF SILVERSTONE     | ALASKA PHANTOM         |         2012 | PG     |
| BETTE NICHOLSON      | COAST RAINBOW          |         2012 | PG     |
| CAMERON STREEP       | COAST RAINBOW          |         2012 | PG     |
| SISSY SOBIESKI       | COAST RAINBOW          |         2012 | PG     |
| REESE KILMER         | COAST RAINBOW          |         2012 | PG     |
| FRANCES DAY-LEWIS    | COAST RAINBOW          |         2012 | PG     |
| ANGELA WITHERSPOON   | COAST RAINBOW          |         2012 | PG     |
| OPRAH KILMER         | COAST RAINBOW          |         2012 | PG     |
| LISA MONROE          | COAST RAINBOW          |         2012 | PG     |
| BURT TEMPLE          | COAST RAINBOW          |         2012 | PG     |
| REESE WEST           | COAST RAINBOW          |         2012 | PG     |
| JULIA MCQUEEN        | CIDER DESIRE           |         2012 | PG     |
| JODIE DEGENERES      | CIDER DESIRE           |         2012 | PG     |
| FRANCES DAY-LEWIS    | CIDER DESIRE           |         2012 | PG     |
| PENELOPE PINKETT     | CIDER DESIRE           |         2012 | PG     |
| JON CHASE            | CIDER DESIRE           |         2012 | PG     |
| MARY TANDY           | CHILL LUCK             |         2012 | PG     |
| BURT POSEY           | CHILL LUCK             |         2012 | PG     |
| WOODY JOLIE          | CHILL LUCK             |         2012 | PG     |
| MEG HAWKE            | CHILL LUCK             |         2012 | PG     |
| WARREN JACKMAN       | CHILL LUCK             |         2012 | PG     |
| KIRSTEN PALTROW      | CHICKEN HELLFIGHTERS   |         2012 | PG     |
| HENRY BERRY          | CHICKEN HELLFIGHTERS   |         2012 | PG     |
| CARY MCCONAUGHEY     | ALI FOREVER            |         2012 | PG     |
| CHRISTOPHER BERRY    | ALI FOREVER            |         2012 | PG     |
| KENNETH TORN         | ALI FOREVER            |         2012 | PG     |
| MORGAN MCDORMAND     | ALI FOREVER            |         2012 | PG     |
| JON CHASE            | ALI FOREVER            |         2012 | PG     |
| RIP CRAWFORD         | BRANNIGAN SUNRISE      |         2013 | PG     |
| KENNETH HOFFMAN      | BRANNIGAN SUNRISE      |         2013 | PG     |
| KARL BERRY           | BOUND CHEAPER          |         2013 | PG     |
| CUBA OLIVIER         | BOUND CHEAPER          |         2013 | PG     |
| KIRSTEN PALTROW      | BORN SPINAL            |         2013 | PG     |
| SISSY SOBIESKI       | BORN SPINAL            |         2013 | PG     |
| NICK STALLONE        | BORN SPINAL            |         2013 | PG     |
| DUSTIN TAUTOU        | BORN SPINAL            |         2013 | PG     |
| RAY JOHANSSON        | BORN SPINAL            |         2013 | PG     |
| KENNETH PALTROW      | BORN SPINAL            |         2013 | PG     |
| DAN STREEP           | BORN SPINAL            |         2013 | PG     |
| RITA REYNOLDS        | BORN SPINAL            |         2013 | PG     |
| MERYL ALLEN          | BORN SPINAL            |         2013 | PG     |
| JOHNNY CAGE          | GRAFFITI LOVE          |         2013 | PG     |
| CHRISTIAN NEESON     | GRAFFITI LOVE          |         2013 | PG     |
| KENNETH PALTROW      | GRAFFITI LOVE          |         2013 | PG     |
| GARY PENN            | GRAFFITI LOVE          |         2013 | PG     |
| SEAN GUINESS         | GRAFFITI LOVE          |         2013 | PG     |
| AUDREY BAILEY        | GRAFFITI LOVE          |         2013 | PG     |
| SISSY SOBIESKI       | GREEK EVERYONE         |         2013 | PG     |
| BURT DUKAKIS         | GREEK EVERYONE         |         2013 | PG     |
| RIP WINSLET          | GREEK EVERYONE         |         2013 | PG     |
| CATE HARRIS          | GREEK EVERYONE         |         2013 | PG     |
| JULIA MCQUEEN        | GLADIATOR WESTWARD     |         2013 | PG     |
| KIRK JOVOVICH        | GLADIATOR WESTWARD     |         2013 | PG     |
| ADAM GRANT           | GLADIATOR WESTWARD     |         2013 | PG     |
| CAMERON ZELLWEGER    | GLADIATOR WESTWARD     |         2013 | PG     |
| IAN TANDY            | GLADIATOR WESTWARD     |         2013 | PG     |
| JAYNE SILVERSTONE    | GLADIATOR WESTWARD     |         2013 | PG     |
| DAN TORN             | BOILED DARES           |         2013 | PG     |
| TIM HACKMAN          | BOILED DARES           |         2013 | PG     |
| NICK STALLONE        | BOILED DARES           |         2013 | PG     |
| PENELOPE PINKETT     | BOILED DARES           |         2013 | PG     |
| JIM MOSTEL           | BOILED DARES           |         2013 | PG     |
| MORGAN HOPKINS       | BOILED DARES           |         2013 | PG     |
| GREGORY GOODING      | BOILED DARES           |         2013 | PG     |
| JULIA FAWCETT        | BOILED DARES           |         2013 | PG     |
| GRACE MOSTEL         | GASLIGHT CRUSADE       |         2013 | PG     |
| JULIA BARRYMORE      | GASLIGHT CRUSADE       |         2013 | PG     |
| WALTER TORN          | GASLIGHT CRUSADE       |         2013 | PG     |
| RICHARD PENN         | GASLIGHT CRUSADE       |         2013 | PG     |
| FAY WINSLET          | GASLIGHT CRUSADE       |         2013 | PG     |
| FRED COSTNER         | GABLES METROPOLIS      |         2013 | PG     |
| RIP CRAWFORD         | GABLES METROPOLIS      |         2013 | PG     |
| FRANCES DAY-LEWIS    | GABLES METROPOLIS      |         2013 | PG     |
| RAY JOHANSSON        | GABLES METROPOLIS      |         2013 | PG     |
| GROUCHO DUNST        | GABLES METROPOLIS      |         2013 | PG     |
| CATE MCQUEEN         | GABLES METROPOLIS      |         2013 | PG     |
| ADAM HOPPER          | GABLES METROPOLIS      |         2013 | PG     |
| GROUCHO WILLIAMS     | GABLES METROPOLIS      |         2013 | PG     |
| NICK WAHLBERG        | GOODFELLAS SALUTE      |         2013 | PG     |
| JOHNNY LOLLOBRIGIDA  | GOODFELLAS SALUTE      |         2013 | PG     |
| ELVIS MARX           | GOODFELLAS SALUTE      |         2013 | PG     |
| BEN WILLIS           | GOODFELLAS SALUTE      |         2013 | PG     |
| GINA DEGENERES       | GOODFELLAS SALUTE      |         2013 | PG     |
| SUSAN DAVIS          | GOODFELLAS SALUTE      |         2013 | PG     |
| FRANCES TOMEI        | GOODFELLAS SALUTE      |         2013 | PG     |
| REESE WEST           | GOODFELLAS SALUTE      |         2013 | PG     |
| RIP WINSLET          | DAWN POND              |         2014 | PG     |
| SCARLETT DAMON       | DAWN POND              |         2014 | PG     |
| MATTHEW LEIGH        | DAWN POND              |         2014 | PG     |
| VIVIEN BASINGER      | DAWN POND              |         2014 | PG     |
| GROUCHO WILLIAMS     | DAWN POND              |         2014 | PG     |
| MERYL ALLEN          | DAWN POND              |         2014 | PG     |
| ANNE CRONYN          | DANGEROUS UPTOWN       |         2014 | PG     |
| MARY TANDY           | DANGEROUS UPTOWN       |         2014 | PG     |
| RALPH CRUZ           | DANGEROUS UPTOWN       |         2014 | PG     |
| SPENCER PECK         | DANGEROUS UPTOWN       |         2014 | PG     |
| KIRSTEN AKROYD       | DANGEROUS UPTOWN       |         2014 | PG     |
| DARYL WAHLBERG       | DANGEROUS UPTOWN       |         2014 | PG     |
| CATE HARRIS          | DANGEROUS UPTOWN       |         2014 | PG     |
| ALBERT JOHANSSON     | DANGEROUS UPTOWN       |         2014 | PG     |
| JOE SWANK            | DALMATIONS SWEDEN      |         2014 | PG     |
| KEVIN BLOOM          | DALMATIONS SWEDEN      |         2014 | PG     |
| VAL BOLGER           | DALMATIONS SWEDEN      |         2014 | PG     |
| GROUCHO DUNST        | DALMATIONS SWEDEN      |         2014 | PG     |
| ALBERT NOLTE         | DALMATIONS SWEDEN      |         2014 | PG     |
| AL GARLAND           | DALMATIONS SWEDEN      |         2014 | PG     |
| HELEN VOIGHT         | CYCLONE FAMILY         |         2014 | PG     |
| RIP CRAWFORD         | CYCLONE FAMILY         |         2014 | PG     |
| JUDY DEAN            | CYCLONE FAMILY         |         2014 | PG     |
| SISSY SOBIESKI       | CRAZY HOME             |         2015 | PG     |
| WOODY JOLIE          | CRAZY HOME             |         2015 | PG     |
| MEG HAWKE            | CRAZY HOME             |         2015 | PG     |
| RUSSELL BACALL       | CRAZY HOME             |         2015 | PG     |
| MORGAN MCDORMAND     | CRAZY HOME             |         2015 | PG     |
| ALBERT NOLTE         | CRAZY HOME             |         2015 | PG     |
| CATE HARRIS          | CRAZY HOME             |         2015 | PG     |
| RUSSELL TEMPLE       | CRAZY HOME             |         2015 | PG     |
| VIVIEN BASINGER      | CRAZY HOME             |         2015 | PG     |
| HARVEY HOPE          | CRAZY HOME             |         2015 | PG     |
| WILL WILSON          | CRAZY HOME             |         2015 | PG     |
| ALAN DREYFUSS        | CRAZY HOME             |         2015 | PG     |
| GENE MCKELLEN        | CRAZY HOME             |         2015 | PG     |
| ED CHASE             | COWBOY DOOM            |         2015 | PG     |
| MILLA KEITEL         | COWBOY DOOM            |         2015 | PG     |
| JULIANNE DENCH       | COWBOY DOOM            |         2015 | PG     |
| WHOOPI HURT          | COWBOY DOOM            |         2015 | PG     |
| GREGORY GOODING      | COWBOY DOOM            |         2015 | PG     |
| KIRSTEN PALTROW      | AGENT TRUMAN           |         2015 | PG     |
| SANDRA KILMER        | AGENT TRUMAN           |         2015 | PG     |
| JAYNE NEESON         | AGENT TRUMAN           |         2015 | PG     |
| WARREN NOLTE         | AGENT TRUMAN           |         2015 | PG     |
| MORGAN WILLIAMS      | AGENT TRUMAN           |         2015 | PG     |
| KENNETH HOFFMAN      | AGENT TRUMAN           |         2015 | PG     |
| REESE WEST           | AGENT TRUMAN           |         2015 | PG     |
| CAMERON STREEP       | CROW GREASE            |         2015 | PG     |
| JODIE DEGENERES      | CROW GREASE            |         2015 | PG     |
| SCARLETT DAMON       | CROW GREASE            |         2015 | PG     |
| CHRIS BRIDGES        | CROW GREASE            |         2015 | PG     |
| WALTER TORN          | CROW GREASE            |         2015 | PG     |
| GROUCHO DUNST        | CROW GREASE            |         2015 | PG     |
| CAMERON ZELLWEGER    | CROW GREASE            |         2015 | PG     |
| MORGAN MCDORMAND     | CROW GREASE            |         2015 | PG     |
| FRANCES TOMEI        | CROW GREASE            |         2015 | PG     |
| LISA MONROE          | CROW GREASE            |         2015 | PG     |
+----------------------+------------------------+--------------+--------+
413 rows in set (0.00 sec)

```
</details>


<details>
  <summary>Question 9 : In which year most films were released?</summary>
  
  ## QUERY : 
``` 
   SELECT release_year, COUNT(release_year) AS Total_Films FROM film GROUP BY release_year ORDER BY COUNT(release_year) DESC LIMIT 1;

```

## RESULT 
```
+--------------+-------------+
| release_year | Total_Films |
+--------------+-------------+
|         2017 |         110 |
+--------------+-------------+
1 row in set (0.00 sec)

```
</details>


<details>
  <summary>Question 10 : In which year least number of films were released ?</summary>
  
  ## QUERY : 
``` 
   SELECT release_year, COUNT(release_year) AS Total_Films FROM film GROUP BY release_year ORDER BY COUNT(release_year) ASC LIMIT 1;

```

## RESULT 
```
+--------------+-------------+
| release_year | Total_Films |
+--------------+-------------+
|         2010 |           1 |
+--------------+-------------+
1 row in set (0.00 sec)

```
</details>


<details>
  <summary>Question 11 : Get the details of the films with maximum length released in 2014 ?</summary>
  
  ## QUERY : 
``` 

   SELECT *, language.name AS language_name FROM film INNER JOIN language ON language.language_id=film.language_id WHERE film.release_year=2014 ORDER BY film.length DESC LIMIT 1;

```

## RESULT 
```
+---------+----------------+-----------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+------------------+---------------------+-------------+--------+---------------------+---------------+
| film_id | title          | description                                                                                   | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features | last_update         | language_id | name   | last_update         | language_name |
+---------+----------------+-----------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+------------------+---------------------+-------------+--------+---------------------+---------------+
|     212 | DARN FORRESTER | A Fateful Story of a A Shark And a Explorer who must Succumb a Technical Writer in A Jet Boat |         2014 |           5 |                 NULL |               7 |        4.99 |    185 |            14.99 | G      | Deleted Scenes   | 2020-07-30 18:07:53 |           5 | French | 2020-07-30 18:07:56 | French        |
+---------+----------------+-----------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+------------------+---------------------+-------------+--------+---------------------+---------------+
1 row in set (0.00 sec)

```
</details>


<details>
  <summary>Question 12 : Get all Sci-Fi movies with NC-17 rating and language they are screend in</summary>
  
  ## QUERY : 
``` 
      SELECT film.title, language.name, film.rating FROM film 
      INNER JOIN language ON film.language_id=language.language_id 
      INNER JOIN film_category ON film_category.film_id=film.film_id
      INNER JOIN category ON category.category_id=film_category.category_id
      WHERE category.name='Sci-Fi' AND film.rating='NC-17';
```

## RESULT 
```
+----------------------+----------+--------+--------------+
| title                | name     | rating | release_year |
+----------------------+----------+--------+--------------+
| CAMELOT VACATION     | Japanese | NC-17  |         2005 |
| CINCINATTI WHISPERER | Mandarin | NC-17  |         2012 |
| HANKY OCTOBER        | German   | NC-17  |         2019 |
| HOLLOW JEOPARDY      | German   | NC-17  |         2020 |
| LICENSE WEEKEND      | German   | NC-17  |         2017 |
| NEMO CAMPUS          | Mandarin | NC-17  |         2003 |
| NONE SPIKING         | Mandarin | NC-17  |         2003 |
| PANTHER REDS         | Mandarin | NC-17  |         2007 |
| RANDOM GO            | Mandarin | NC-17  |         2011 |
+----------------------+----------+--------+--------------+
9 rows in set (0.00 sec)

```
</details>


<details>
  <summary>Question 13 : The actor FRED COSTNER(id:16) shifted to new address: 
  `055, Piazzale Michelangelo, Postal Code - 50125, District - Rifredi at Florence, Italy.` Insert the new city and update the address of the actor.
  </summary>
  
  ## QUERY : 
``` 
      INSERT INTO city(city, country_id) VALUE('Florence',(SELECT country.country_id FROM country WHERE country.country='Italy'));
      UPDATE address SET address.address='055, Piazzale Michelangelo', address.district='Rifredi', address.postal_code='50125', 
      address.city_id=(SELECT city.city_id FROM city WHERE city.city='Florence') WHERE address_id=(SELECT address_id FROM actor WHERE actor_id=16);

```

## RESULT 
```
Query OK, 1 row affected (0.00 sec)

Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

```
</details>


<details>
  <summary>Question 14 : A new film "No Time to Die" is releasing in 2020 whose details are 
  ```
  Title: No Time to Die
  Description: Recruited to rescue a kidnapped scientist, globe-trootting spy James Bond finds himself hot and the trail of a mysterious villain, who's armed with a dangerous new technology.
  Language: English
  Org. Language: English
  Length: 100
  Rental duration: 6
  Rental rate: 3.99
  Rating: PG-13
  Replacement cost: 20.99
  Special Features: Trailers, Deleted Scenes
  ```
  </summary>
  
  ## QUERY : 
``` 
 INSERT INTO film(title, description, release_year, language_id, original_language_id, rental_duration, rental_rate, length, replacement_cost, rating, special_features) 
 VALUE('No Time to Die', "Recruited to rescue a kidnapped scientist, globe-trootting spy James Bond finds himself hot and the trail of a mysterious villain, who's armed with a dangerous new technology.", 2020, (SELECT language_id FROM language WHERE name='English'), 
 (SELECT language_id FROM language WHERE name='English'), 6, 3.99, 100, 20.99, 'PG-13',
  'Trailers,Deleted Scenes')

```

## RESULT 
```
Database changed
Query OK, 1 row affected (0.00 sec)

mysql> select * from film where title='No Time to Die';
+---------+----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-------------------------+---------------------+       
| film_id | title          | description                                                                                                                                                       
              | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features        | last_update         |       
+---------+----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-------------------------+---------------------+       
|    1002 | No Time to Die | Recruited to rescue a kidnapped scientist, globe-trootting spy James Bond finds himself hot and the trail of a mysterious villain, who's armed with a dangerous new technology. |         2020 |           1 |                    1 |               6 |        3.99 |    100 |            20.99 | PG-13  | Trailers,Deleted Scenes | 2022-12-25 07:41:49 |
+---------+----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-------------------------+---------------------+       
1 row in set (0.00 sec)

```
</details>


<details>
  <summary>Question 15 : Assign the category Action,Classics,Drama to the movie "No Time to Die".</summary>
  
  ## QUERY : 
``` 
      INSERT INTO film_category(film_id,category_id) VALUE 
      ((SELECT film_id FROM film WHERE title='No Time to Die'),(SELECT category_id FROM category WHERE name='Action')),
      ((SELECT film_id FROM film WHERE title='No Time to Die'),(SELECT category_id FROM category WHERE name='Classics')),
      ((SELECT film_id FROM film WHERE title='No Time to Die'),(SELECT category_id FROM category WHERE name='Drama'));

```

## RESULT 
```
Query OK, 3 rows affected (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 0

```
</details>


<details>
  <summary>Question 16 : Assign the cast: PENELOPE GUINESS, NICK WAHLBERG, JOE SWANK to the movie "NO Time to Die".</summary>
  
  ## QUERY : 
``` 
      INSERT INTO film_actor(film_id,actor_id) VALUE 
      ((SELECT film_id FROM film WHERE title='No Time to Die'),(SELECT actor_id FROM actor WHERE CONCAT(first_name,' ',last_name)='PENELOPE GUINESS')),
      ((SELECT film_id FROM film WHERE title='No Time to Die'),(SELECT actor_id FROM actor WHERE CONCAT(first_name,' ',last_name)='NICK WAHLBERG')),
      ((SELECT film_id FROM film WHERE title='No Time to Die'),(SELECT actor_id FROM actor WHERE CONCAT(first_name,' ',last_name)='JOE SWANK'));
      
```

## RESULT 
```

Query OK, 3 rows affected (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 0

```
</details>


<details>
  <summary>Question 17 : Assign a new category Thriller to the movie ANGELS LIFE</summary>
  
  ## QUERY : 
``` 

      INSERT INTO category(name) VALUE('Thriller');
      INSERT INTO film_category(film_id,category_id) VALUE ((SELECT film_id FROM film WHERE title='ANGELS LIFE'),(SELECT category_id FROM category WHERE name='Thriller'));

```

## RESULT 
```
Query OK, 1 row affected (0.01 sec)

Query OK, 1 row affected (0.00 sec)

```
</details>


<details>
  <summary>Question 18 : Which actor acted in most movies?</summary>
  
  ## QUERY : 
``` 

      SELECT CONCAT(actor.first_name, ' ', actor.last_name) AS Actor_name, COUNT(film_actor.film_id) AS Total_Films FROM actor 
      INNER JOIN film_actor ON actor.actor_id=film_actor.actor_id GROUP BY film_actor.actor_id ORDER BY COUNT(film_actor.actor_id) DESC LIMIT 1;
      
```

## RESULT 
```
+----------------+-------------+
| Actor_name     | Total_Films |
+----------------+-------------+
| GINA DEGENERES |          42 |
+----------------+-------------+
1 row in set (0.02 sec)

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
