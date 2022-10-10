---
title: "Intoduction to strings and data structures "

objectives:
- "understand basics of strings and string manipulation"
- " understanding different data structure"
- "learn about functions of each data structure"
keypoints:
- "understanding strings and vectors"

---

## Strings

- Strings are made of a single character or contain a collection of characters.
- Strings can be created by either single quotes (‘ ‘) or double quotes (“ “)

**Rule for String in R**

-	String starts and ends with a single quote. Double quotes (“ “), and through the escape sequence (‘/’), single quote can become a part of the string.
Example- ‘buses’, ‘merry”s’, ‘ merry\’s’


~~~
# input code string concatenation
Count number of characters 
x1 <- "Olivia"
x2 <- "Jhon"
x3 <- "William"

#checking number of characters
nchar(x1)
nchar(x2)
nchar(x3)

# Letters using vector function in R
# Check the sequence of letters
letters
letters[4]
letters[1:5]

# String Concatenation
# Paste function is used with syntax below:

x <- paste("Hello","World","!",sep = " ")
x

y <- paste(x1,x2,x3,"is happy.")
y

z<- paste("Hello","everyone","!", sep =" ")
z
# Vectors

c() # concatenate function

x4 <- c("Olivia","Jhon","William")
y1 <- paste(x4,"is happy.")
y1

z1 <- c("Please bring me","a few ")
z2 <- c("some vegetables","fruits")
z <- paste(z1,z2,collapse = " and ")
z
~~~
{: .language-r}

~~~
# output
 # input code string concatenation
> Count number of characters 
Error: unexpected symbol in "Count number"
> x1 <- "Olivia"
> x2 <- "Jhon"
> x3 <- "William"
> 
> #checking number of characters
> nchar(x1)
[1] 6
> nchar(x2)
[1] 4
> nchar(x3)
[1] 7
> 
> # Letters using vector function in R
> # Check the sequence of letters
> letters
 [1] "a" "b" "c" "d" "e" "f" "g" "h" "i" "j" "k" "l" "m" "n" "o" "p" "q" "r" "s" "t" "u" "v" "w" "x"
[25] "y" "z"
> letters[4]
[1] "d"
> letters[1:5]
[1] "a" "b" "c" "d" "e"
> 
> # String Concatenation
> # Paste function is used with syntax below:
> 
> x <- paste("Hello","World","!",sep = " ")
> x
[1] "Hello World !"
> 
> y <- paste(x1,x2,x3,"is happy.")
> y
[1] "Olivia Jhon William is happy."
> 
> z<- paste("Hello","everyone","!", sep =" ")
> z
[1] "Hello everyone !"
> 
> x4 <- c("Olivia","Jhon","William")
> y1 <- paste(x4,"is happy.")
> y1
[1] "Olivia is happy."  "Jhon is happy."    "William is happy."
> 
> z1 <- c("Please bring me","a few ")
> z2 <- c("some vegetables","fruits")
> z <- paste(z1,z2,collapse = " and ")
> z
[1] "Please bring me some vegetables and a few  fruits"

~~~
{: .output}

### String Manipulation 

-it’s the process of corecing, slicing, pasting, or analyzing strings

~~~
x <- "William is happy today"
x

# Converting all words to upper case using toupper() function
toupper(x)

# Converting all words to lower case using tolower() function
tolower(x)

x1 <- "Henry is A hardworker. He owns A house and A car."
x1
chartr("A", "a", x1)

z <- "I widd gq tq market tqmqrrqw."
chartr("dq","lo", z)

x2 <- "Henry puts in all his good efforts"
x2
substr(x2, start = 22, stop = 27)

#split function

x4 <- "Henry puts in all his good efforts"
class(x4)
y1 <- strsplit(x4, split = " ")
y1
class(y1)
#either create a variable like y1 or direct use the function in case of Mason 
strsplit("Mason", split ="") 
x4
y2 <- unlist(strsplit(x4, split = " "))
y2
class(y2)

~~~
{: .language-r}

~~~
#output 
> x <- "William is happy today"
> x
[1] "William is happy today"
> 
> # Converting all words to upper case using toupper() function
> toupper(x)
[1] "WILLIAM IS HAPPY TODAY"
> 
> # Converting all words to lower case using tolower() function
> tolower(x)
[1] "william is happy today"
> 
> x1 <- "Henry is A hardworker. He owns A house and A car."
> x1
[1] "Henry is A hardworker. He owns A house and A car."
> chartr("A", "a", x1)
[1] "Henry is a hardworker. He owns a house and a car."
> 
> z <- "I widd gq tq market tqmqrrqw."
> chartr("dq","lo", z)
[1] "I will go to market tomorrow."
> 
> x2 <- "Henry puts in all his good efforts"
> x2
[1] "Henry puts in all his good efforts"
> substr(x2, start = 22, stop = 27)
[1] " good "
> 
> #split function
> 
> x4 <- "Henry puts in all his good efforts"
> class(x4)
[1] "character"
> y1 <- strsplit(x4, split = " ")
> y1
[[1]]
[1] "Henry"   "puts"    "in"      "all"     "his"     "good"    "efforts"

> class(y1)
[1] "list"
> #either create a variable like y1 or direct use the function in case of Mason 
> strsplit("Mason", split ="") 
[[1]]
[1] "M" "a" "s" "o" "n"

> x4
[1] "Henry puts in all his good efforts"
> y2 <- unlist(strsplit(x4, split = " "))
> y2
[1] "Henry"   "puts"    "in"      "all"     "his"     "good"    "efforts"
> class(y2)
[1] "character"

~~~
{: .output}


## Data Structure
A data structure is essentially a way to organize data in a system to facilitate effective usage of the same.Data structures are the objects that are manipulated regularly in R. They are used to store data in an organized fashion to make data manipulation and other data operations more efficient. R has many data structure which are as follows

- Vectors
- Matrices
- Factors
- Data Frames
- Arrays
- Lists

#### Vector

Vectors are the basic data structure of R. Vectors can hold multiple values together using the concatenate **c()** function. The type of data inside a vector can be determined by using the **type of()** function and the length (or) number of elements in a vector can be found with the **length()** function.
R uses **one indexing** unlike python, hence the position of the first component in a vector can be accessed by vector name [1]
A vector will always **contain** data of the **same data type**. If a vector contains multiple data types the vector will convert all its values to the same data type in the below order of precedence:
- Character
- Double (Float / Decimals)
- Integers (Round whole numbers)

Technically, vectors can be one of two types:
- atomic vectors
- lists
although the term “vector” most commonly refers to the atomic types not to lists.

#### Matrices and Array

Adding a dim attribute to an atomic vector allows it to behave like a multi-dimensional array. A special case of the array is the matrix, which has two dimensions. Matrices are used commonly as part of the mathematical machinery of statistics. Arrays are much rarer, but worth being aware of.
Matrices and arrays are created with matrix() and array(), or by using the assignment form of dim()

#### Data Frames
A data frame is a very important data type in R. It’s pretty much the de facto data structure for most tabular data and what we use for statistics (explained in detail in the next section)
**Some additional information on data frames**:
Usually created by read.csv() and read.table(), i.e. when importing the data into R.
Assuming all columns in a data frame are of same type, data frame can be converted to a matrix with data.matrix() (preferred) or as.matrix(). Otherwise type coercion will be enforced and the results may not always be what you expect.
Can also create a new data frame with data.frame() function.
Find the number of rows and columns with nrow(dat) and ncol(dat), respectively.
Rownames are often automatically generated and look like 1, 2, …, n. Consistency in numbering of rownames may not be honored when rows are reshuffled or subset.

#### Lists 
In R lists act as containers. Unlike atomic vectors, the contents of a list are not restricted to a single mode and can encompass any mixture of data types. Lists are sometimes called generic vectors, because the elements of a list can by of any type of R object, even lists containing further list. You can create lists using list() or coerce other objects using as.list()


~~~

# DATA STRUCTURES ##########################################

## Vector ##################################################

v1 <- c(1, 2, 3, 4, 5)
v1
is.vector(v1)

v2 <- c("a", "b", "c")
v2
is.vector(v2)

v3 <- c(TRUE, TRUE, FALSE, FALSE, TRUE)
v3
is.vector(v3)

## Matrix ##################################################

m1 <- matrix(c(T, T, F, F, T, F), nrow = 2)
m1

m2 <- matrix(c("a", "b", 
               "c", "d"), 
               nrow = 2,
               byrow = T)
m2

## Array ###################################################

# Give data, then dimemensions (rows, columns, tables)
a1 <- array(c( 1:24), c(4, 3, 2))
a1

## Data frame ##############################################

# Can combine vectors of the same length

vNumeric   <- c(1, 2, 3)
vCharacter <- c("a", "b", "c")
vLogical   <- c(T, F, T)

dfa <- cbind(vNumeric, vCharacter, vLogical)
dfa  # Matrix of one data type

df <- as.data.frame(cbind(vNumeric, vCharacter, vLogical))
df  # Makes a data frame with three different data types

## List ####################################################

o1 <- c(1, 2, 3)
o2 <- c("a", "b", "c", "d")
o3 <- c(T, F, T, T, F)

list1 <- list(o1, o2, o3)
list1

list2 <- list(o1, o2, o3, list1)  # Lists within lists!
list2

# COERCING TYPES ###########################################

## Automatic coercion ######################################

# Goes to "least restrictive" data type

(coerce1 <- c(1, "b", TRUE))
# coerce1  # Parenthese around command above make this moot
typeof(coerce1)

## Coerce numeric to integer ###############################

(coerce2 <- 5)
typeof(coerce2)

(coerce3 <- as.integer(5))
typeof(coerce3)

## Coerce character to numeric #############################

(coerce4 <- c("1", "2", "3"))
typeof(coerce4)

(coerce5 <- as.numeric(c("1", "2", "3")))
typeof(coerce5)

## Coerce matrix to data frame #############################

(coerce6 <- matrix(1:9, nrow= 3))
is.matrix(coerce6)

(coerce7 <- as.data.frame(matrix(1:9, nrow= 3)))
is.data.frame(coerce7)

# CLEAN UP #################################################

# Clear environment
rm(list = ls()) 

# Clear console
cat("\014")  # ctrl+L

# Clear mind :)


~~~
{: .language-r}








