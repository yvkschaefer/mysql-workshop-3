# MySQL Workshop 3 - Advanced Data Manipulation

<img src="http://cdn.meme.am/instances2/500x/1987981.jpg" border="0" width="850">

## Workshop Contents


### Data Manipulation Statements
* [Inner Join](https://dev.mysql.com/doc/refman/5.7/en/join.html) aka Join

### MySQL Built-in Comparison Functions
* [Between](https://dev.mysql.com/doc/refman/5.7/en/comparison-operators.html#operator_between)
* [In](https://dev.mysql.com/doc/refman/5.7/en/comparison-operators.html#function_in)
* [Not In](https://dev.mysql.com/doc/refman/5.7/en/comparison-operators.html#function_not-in)

### MySQL Built-in Numeric Functions
* [Ceil](https://dev.mysql.com/doc/refman/5.7/en/mathematical-functions.html#function_ceil)
* [Floor](https://dev.mysql.com/doc/refman/5.7/en/mathematical-functions.html#function_floor)
* [Power](https://dev.mysql.com/doc/refman/5.7/en/mathematical-functions.html#function_power)
* [Rand](https://dev.mysql.com/doc/refman/5.7/en/mathematical-functions.html#function_rand)
* [Round](https://dev.mysql.com/doc/refman/5.7/en/mathematical-functions.html#function_round)

### MySQL Built-in String Functions
* [Concat](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_concat)
* [Format](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_format)
* [Lower](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_lcase)
* [Length](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_length)
* [Reverse](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_reverse)
* [Substring](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_substring)
* [Substring Index](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_substring-index)
* [Upper](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_upper)

### MySQL Built-in Date & Time Functions
* [Current Date](https://dev.mysql.com/doc/refman/5.7/en/date-and-time-functions.html#function_current-date)
* [Current Time](https://dev.mysql.com/doc/refman/5.7/en/date-and-time-functions.html#function_current-time)
* [Date](https://dev.mysql.com/doc/refman/5.7/en/date-and-time-functions.html#function_date)
* [Date Diff](https://dev.mysql.com/doc/refman/5.7/en/date-and-time-functions.html#function_datediff)
* [Date Format](https://dev.mysql.com/doc/refman/5.7/en/date-and-time-functions.html#function_date-format)
* [Now](https://dev.mysql.com/doc/refman/5.7/en/date-and-time-functions.html#function_now)
* [Time](https://dev.mysql.com/doc/refman/5.7/en/date-and-time-functions.html#function_time)


## Before starting!
With your newly acquired knowledge, go back to mysql-workshop-2 and answer the following questions about the address book schema:

### Exercise 1
* Which Account owns the most Address Books?
* Which Address Book contains the most Entries?

### Exercise 2
* How many Address Book Entries have phones starting with area code ```3XX```?
* How many Address Book Entries have ```home``` phones not containing the digit ```5```?
* How many Address Book Entries are ```work``` phones starting with a country code?

## Workshop Instructions
* Fork this repository
* Create a new Cloud9 Workspace
* For every exercise in this Workshop:
  * Create a new file named "exercise-n.txt", containing:
    * The SQL Statement used, when applicable
    * The SQL Statement results, when applicable
* After the first exercise you commit, do a pull request from your master branch. Then, commit and push after each exercise so that we can see your progress.

### Exercise 1
* Reflect the data model shown in ```schema/addressbook_normalized.png``` within database ```decodemtl_addressbook```
  * ```Account.id``` is a primary auto-increment key
  * ```AddressBook.id``` is a primary auto-increment key
  * ```Entry.id``` is a primary auto-increment key
  * ```Entry.type``` is an ENUM column permitting ```phone```, ```address``` and ```electronic-mail```
  * ```Address.id``` is a primary auto-increment key
  * ```Address.type``` is an ENUM column permitting ```home```, ```work``` and ```other```
  * ```ElectronicMail.id``` is a primary auto-increment key
  * ```ElectronicMail.type``` is an ENUM column permitting ```home```, ```work``` and ```other```
  * ```Phone.id``` is a primary auto-increment key
  * ```Phone.type``` is an ENUM column permitting ```home```, ```work``` and ```other```
  * ```Phone.subtype``` is an ENUM column permitting ```landline```, ```cellular``` and ```fax```

### Exercise 2
* Bulk import data from the source files into ```decodemtl_addressbook```:
  * data/import-account.sql
  * data/import-addressbook.sql
  * data/import-entry.sql

### Exercise 3
* List all of the countries with respective occurence totals in ```DESC``` order
* Country names should all appear lowercase

### Exercise 4
* List all of the first names for ```AddressBook.name="Pharetra Ut Limited"```

### Exercise 5
* List all of the emails associated to ```AddressBook.id = 100```

### Exercise 6
* List all of the phone numbers for ```Jenkins, Charlotte```

### Exercise 7
* List all possible domain name values for ```ElectronicMail``` (email@```domain.name```)

### Exercise 8
* List how many phones were landlines, cellular and fax for entries with birthdates between October 1950 and October 1960

### Exercise 9
* List all of the cities within the countries of ```Canada```, ```Austria```, ```Isle of Man```, ```Ireland``` and ```Japan```.

### Exercise 10
* Transform all ```work``` emails into ```home``` emails and vice versa. BE CAREFUL ;)

### Exercise 11 (Challenge)
* Create a data model representing a Store with Inventory, Customers and Invoices
* This model should provide answers to the following questions:
  * What is the Store's income within a specific date range?
  * What is the Store's top selling Inventory product?
  * Which company produces the top selling Inventory product?
  * What is the top refunded Inventory product?
  * Which products should be taken out from the Store's Inventory?
  * Which companies should the Store stop selling products from?
  * What is the amount of Internal (Canadian) vs. External sales?
  * How many of a specific product remains in Inventory for a specific date?

### Exercise 12 (Workshop Challenge)
* Connect to your MySQL instance using the ```root``` user
* Execute this Statement: ```DROP DATABASE mysql; EXIT;```
* Execute this Command ```sudo killall mysqld```
* Execute this Command ```mysql-ctl start```
  * OMG!!! Explain what happened.
  * Find a way to recover the MySQL instance.
