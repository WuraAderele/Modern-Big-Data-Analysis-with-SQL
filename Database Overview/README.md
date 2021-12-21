# Exploring Structured Data in Hue <img src= "https://user-images.githubusercontent.com/94797745/146965611-910aa20c-8566-430f-9389-9e4273e7d825.jpg" width = "100" height = "100"> 
## 📝 Assignment Objective
For this assessment, we will use Hue (an open-source SQL Assistant for querying Databases & Data Warehouses and collaborating) to examine an existing database, **fun** and its tables and produce a database overview document that serves two common real-world purposes:
* Explore the data in a database that you can subsequently use for analysis.
* The document created can help others quickly gain an overview of the data available in the database, and it can also help whenever you return to this database after some time away.
## 🚀 Solutions (Overview of the Fun Database)
### Notes:
* Column and table descriptions are estimates based on examination of the tables, not descriptions from the data sources.
* Column descriptions of PK and references are descriptions of assumed relationships between tables, not database constraints.

### Tables in the FUN database:
* Card_rank Table with information on order of placement of cards
* Card_suit Color of different card categories (suits)
* Game Look-up table with general information about different game types
* Inventory Table showing shops, games in stock, aisle location in shop, and price

#### Table: Card_rank
    * Columns
          * Rank: String
          * Value: Tiny Int - Order in which cards should be arranged
   #### Sample from Card_rank table
||Rank |Value|
|-|----|-----|
|1| Ace |NULL|
|2| 2| 2|
|3| 3| 3|
