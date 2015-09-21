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


## Workshop Instructions
* Fork this repository
* Create a new Cloud9 Workspace
* For every exercise in this Workshop:
  * Create a new branch off from "master" named "exercise-n"
  * Create a new file named "exercise-n.txt", containing:
    * The SQL Query used, when applicable
    * The SQL Query results, when applicable
  * Create a pull request

### Exercise 1
* Reflect the data model shown in ```schema/addressbook_normalized.png``` within database ```decodemtl_addressbook```
  * ```Account.id``` is a primary auto-increment key
  * ```AddressBook.id``` is a primary auto-increment key
  * ```Entry.id``` is a primary auto-increment key
  * ```Entry.type``` is an ENUM column permitting ```phone```, ```address``` and ```electronic-mail```
  * ```Address.id``` is a primary auto-increment key
  * ```Address.type``` is an ENUM column permitting ```home```, ```work``` and ```other```
  * ```Email.id``` is a primary auto-increment key
  * ```Email.type``` is an ENUM column permitting ```home```, ```work``` and ```other```
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
* The first and last letters should be capitalized

### Exercise 5
* List all of the emails associated to ```AddressBook.id = 100```

### Exercise 6
* List all of the phone numbers for ```Jenkins, Charlotte```

### Exercise 7
* List all possible domain name values for ```ElectronicMail``` (email@```domain.name```)

### Exercise 8
* List how many phones were landlines, cellular and fax for entries with birthdates between October 1950 and October 1960

### Exercise 9
* List all Account emails with AddressBook containing Phone numbers with a country code

### Exercise 10
* List all of the person names born between 8PM and 9PM but not in the month of February

### Exercise 11
* List all of the cities within the countries of ```Canada```, ```Austria```, ```Isle of Man```, ```Ireland``` and ```Japan```.

### Exercise 12
* List 100 phone numbers in separated parts: country code, area code and line number

### Exercise 13
* List the date difference, in days, between AddressBook creation and modification dates

### Exercise 14
* Reverse all fax phone numbers, keeping the phone numbers in a valid format
* List all of the new fax phone number values

### Exercise 15
* Transform all ```work``` emails into ```home``` emails and vice versa

### Exercise 16
* Randomize the civic number of 10 ```other``` addresses whose primary key value ranges between 715 and 800

### Exercise 17
* Return a list of adresses ordered by length of the combined columns ```addressLine1``` and ```city```

### Exercise 18
* Create an exact copy of ```decodemtl_addressbook.Account``` and its data
* The copy's ```modifiedOn``` column should reflect today's date

### Exercise 19
* Return a list of all accounts with columns ```createdOn``` in the format of ```Sept 20 2016 11:45 AM``` and ```modifiedOn``` in the format ```20th 16 Tue 20 09 Sep 264```

### Exercise 20 (Workshop Challenge)
* Connect to your MySQL instance using the ```root``` user
* Execute this Statement: ```DROP DATABASE mysql; EXIT;```
* Execute this Command ```sudo killall mysqld```
* Execute this Command ```mysql-ctl start```
  * OMG!!! Explain what happened.
  * Find a way to recover the MySQL instance.
