# Programming with JavaScript
#### This chapter describes JavaScript's expressions and operators, including assignment, comparison, arithmetic, bitwise, logical, string, ternary and more.

## Expressions and operators

### **Operators**:
#### **JavaScript** has the following types of operators. This section describes the operators and contains information about operator precedence. **for more visit**: [operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#assignment_operators)
- Assignment operators
- Comparison operators
- Arithmetic operators
- Bitwise operators
- Logical operators
- String operators
- Conditional (ternary) operator
- Comma operator
- Unary operators
- Relational operators


#### Example of Assignment operators:

| *Name*      | *Shorthand operator	* |
| ----------- | ----------- |
| Assignment | x = y |
|Addition assignment | x += y |
|Subtraction assignment | x -= y |
|Logical AND assignment | x &&= y |
|Division assignment | x /= y |


##### **for more visit**: [operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)


#### Example of Comparison operators:

| *Operator*      | *Description	* |
| ----------- | ----------- |
| Equal (==) | Returns true if the operands are equal.|
|Not equal (!=) | Returns true if the operands are not equal.|
|Greater than (>) |Returns true if the left operand is greater than the right operand. |
|Less than (<)|Returns true if the left operand is less than the right operand. |


##### **for more visit**: [operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)


### **Expressions**:
##### **JavaScript** has the following expression categories:
- Arithmetic: evaluates to a number, for example 3.14159. (Generally uses arithmetic operators.)
- String: evaluates to a character string, for example, "Fred" or "234". (Generally uses string operators.)
- Logical: evaluates to true or false. (Often involves logical operators.)
- Primary expressions: Basic keywords and general expressions in JavaScript.
- Left-hand-side expressions: Left values are the destination of an assignment.
## Functions
#### Functions are one of the fundamental building blocks in JavaScript. A function in JavaScript is similar to a procedure—a set of statements that performs a task or calculates a value, but for a procedure to qualify as a function, it should take some input and return an output where there is some obvious relationship between the input and the output. To use a function, you must define it somewhere in the scope from which you wish to call it.
### **Function declarations**
#### A function definition (also called a function declaration, or function statement) consists of the function keyword, followed by:
- The name of the function.
- A list of parameters to the function, enclosed in parentheses and separated by commas.
- The JavaScript statements that define the function, enclosed in curly brackets, {...}.
#### For example, the following code defines a simple function named square:

#### - function square(number){ return number * number;}
#### The function square takes one parameter, called number. The function consists of one statement that says to return the parameter of the function (that is, number) multiplied by itself. The statement return specifies the value returned by the function:
return number * number;
### **Calling functions**
#### Calling the function actually performs the specified actions with the indicated parameters. For example, if you define the function square, you could call it as follows:
square(5); [The preceding statement calls the function with an argument of 5. The function executes its statements and returns the value 25.]
## Control flow
#### The control flow is the order in which the computer executes statements in a script.

#### Code is run in order from the first line in the file to the last line, unless the computer runs across the (extremely frequent) structures that change the control flow, such as conditionals and loops. 

#### For example, imagine a script used to validate user data from a webpage form. The script submits validated data, but if the user, say, leaves a required field empty, the script prompts them to fill it in. To do this, the script uses a conditional structure or if...else, so that different code executes depending on whether the form is complete or not:
if (field==empty) {
    promptUser();
} else {
    submitForm();
}
#### A typical script in JavaScript or PHP (and the like) includes many control structures, including conditionals, loops and functions. Parts of a script may also be set to execute when events occur.

#### For example, the above excerpt might be inside a function that runs when the user clicks the Submit button for the form. The function could also include a loop, which iterates through all of the fields in the form, checking each one in turn. Looking back at the code in the if and else sections, the lines promptUser and submitForm could also be calls to other functions in the script. As you can see, control structures can dictate complex flows of processing even with only a few lines of code.

#### Control flow means that when you read a script, you must not only read from start to finish but also look at program structure and how it affects order of execution.



