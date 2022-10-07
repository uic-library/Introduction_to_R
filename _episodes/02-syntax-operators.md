---
title: "R syntax and operators"
teaching: 0
exercises: 0

objectives:
 - "perform basic arithematic functions"
 - "Understand the basic logical operators"


---
## R syntax and Logical operators 
Codes can be directly run in the R console. Try running the below code to perform basic 
arithmetic operations of Addition (+), Subtraction (-), Multiplication (*), Division (/) and Modulo (%%) 
operation directly in the console.
 ~~~
 > 2+2
 [1] 4
 > 2-2
 [1] 0
 >2*2
 [1] 4
 > 2/2
 [1] 1
 > 3%%2
 [1] 1

 ~~~
{: .language-r}

Implementing the same code in the script area. If you do not see a file open in the script 
area select **File → New File → R Script** from the menu and then type the code in the new file that appears.
Now the code in the script area (or R File) does not execute automatically, instead place 
the cursor on the line which needs to be executed and select **RUN** option or press **Ctrl + Enter**(for windows). 
To run multiple lines of code, select all the lines first and then select **RUN** option or press **Ctrl + Enter**.

![Rstudio run command](../fig/02-Rstudio-Run-command.PNG)

Values can be assigned to variables in R using the “<-” symbol. The variable is written on the left 
and is assigned the value on the right side. For example, to assign a value of 3 to x we can type the below code, 
x <- 3 

Assigning values to variables are quite useful especially if these values would be used again. 
Similar to the previous examples, operations can be performed on the variables to get output 
directly (or) the output can be stored in a different variable. 
Once a variable is created it will be visible under the environment section
~~~
> x <- 3
> y <- 5
> x+y
[1] 8
> z <- x+y
> z
[1] 8

 ~~~
{: .language-r}


One thing to be aware of is that R is **case-sensitive**. Hence variable “a” is different from “A”

### LOGICAL OPERATORS
Provides a list of Boolean results based on operation performed 
- < Less than

- <= Less than or equal to 

- \>  Greater than

- \>= Greater than or equal to
 
- ==  Equal to

- ! = Not equal to

- x&y  AND operation

- x\|y  OR operation 

- !x  NOT operation

Please note that in R the Boolean values “TRUE” & “FALSE” can also be written as “T” &” F”.

#### Function in R
A key feature of R is functions. Functions are “self contained” modules of code that accomplish a specific task. Functions usually take in some sort of data structure (value, vector, dataframe etc.), process it, and return a result.
The general usage for a function is the name of the function followed by parentheses:**function_name(input)**

#### Comments in R 
Comments can be used to explain R code, and to make it more readable. It can also be used to prevent execution when testing alternative code.
Comments starts with a **#** When executing the R-code, **R will ignore anything that starts with #**.

Example:- **# This is a comment**
"Hello World!"

