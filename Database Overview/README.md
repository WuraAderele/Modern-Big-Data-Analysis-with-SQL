# Exploring Structured Data in Hue <img src= "https://user-images.githubusercontent.com/94797745/146965611-910aa20c-8566-430f-9389-9e4273e7d825.jpg" width = "100" height = "100"> 
## 📝 Assignment Objective
For this assessment, we will use Hue (an open-source SQL Assistant for querying Databases & Data Warehouses and collaborating) to examine an existing database, **fun** and its tables and produce a database overview document that serves two common real-world purposes:
* Explore the data in a database that you can subsequently use for analysis.
* The document created can help others quickly gain an overview of the data available in the database, and it can also help whenever you return to this database after some time away.
## 🚀 Solutions (Overview of the Fun Database)
## Adediwura Ayo-Aderele                                                                                                     2021-November-28
### Notes:
* Column and table descriptions are estimates based on examination of the tables, not descriptions from the data sources.
* Column descriptions of PK and references are descriptions of assumed relationships between tables, not database constraints.

### Tables in the FUN database:
* Card_rank Table with information on order of placement of cards
* Card_suit Color of different card categories (suits)
* Game Look-up table with general information about different game types
* Inventory Table showing shops, games in stock, aisle location in shop, and price

#### Table: Card_rank
* Rank: String
* Value: Tiny Int - Order in which cards should be arranged
   #### Sample from Card_rank table
||Rank |Value|
|-|----|-----|
|1| Ace |NULL|
|2| 2| 2|
|3| 3| 3|

#### Table: Card_suit
* Suit: String
* Color: String
   #### Sample from Card_suit table
||Suit| Color|
|-|----|-----|
|1| Clubs| Black|
|2| Diamonds| Red|
|3| Hearts| Red|

#### Table: Game
* Id: Int - PK, Numerical game ID
* Name: String - Names of Games
* Inventor: String
* Year: String
* Min_age: Tiny Int
* Min_players: Tiny Int
* Max_players: Tiny Int
* List_price: Decimal (5,2) - Price of game (assume USD as currency)
   #### Sample from Game table
|Id| Name| Inventor| Year| Min_age| Min_players| Max_players| List_price|
|--|-----|---------|-----|--------|------------|------------|-----------|
|1| Monopoly| Elizabeth Magie| 1903| 8 |2 |6| 19.99|
|2| Scrabble| Alfred Mosher Butts| 1938| 8| 2| 4| 17.99|
 |3| Clue| Anthony E. Pratt| 1944| 8| 2| 6| 9.99|
 
#### Table: Inventory
* Columns
* Shop String
* Game: String - Names of Games, Relates to game.name
* Qty: Int - Amount of corresponding game currently in stock in corresponding shop
* Aisle: Tiny Int
* Price: Decimal (5,2) - Price of game in corresponding shop (assume USD as currency)
   #### Sample from Inventory table
|Shop| Game| Qty| Aisle| Price|
|----|-----|----|------|------|
|1| Dicey| Monopoly| 7| 3| 17.99|
|2| Dicey| Clue| 3 |NULL| 9.99|
|3 |Board ‘Em| Monopoly |11| 2| 25.00|
