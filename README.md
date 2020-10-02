# Week 7

In this week's lab we will practice:
* string manipulation,
* recursion, 
* sorting, and 
* linked lists

Given an *linked list* of Strings, use *quicksort* (as described in class) to sort the strings in order of **increasing length**. 

You should use the code we developed in class on [September 28rd](https://github.com/CS2401-Fall2020/September28-inClass).

Do not change the method signatures. **Do not use helper methods**. 

## Tasks
### static method `mergeSortLengths(StringLL left)`

This *recursive* method will use merge sort to sort the elements in the list who's head is `left` by their **string lengths**. 
The method will be implemented by creating two linked lists each containing half the elements 
(with odd sized arrays having one extra element on the half containing the lower indexes)
and making recursive calls on those. 
The resulting lists will then concatenated and the head pointer of the front of the combined list returned. 
In the case of ties in the length of the string they will be put in alphabetical order.  

***Example 1:***
Given the Strings `"DeBlasio" --> "Gastelum" --> "Flores" --> "Alvorado" --> "Berkowitz" --> null` the returned array would be: 
```
"Flores" --> "Alvorado" --> "DeBlasio" --> "Gastelum" --> "Berkowitz" --> null
```
The string lengths in the result are 6, 8, 8, 8, 9. 
For the strings with ties in length they are sorted alphabetically. 


***Example 2:***
Given the Strings `"AAAAA" --> "BBBB" --> "CCC" --> "DD" --> "E"  --> null` the returned array would be: 
```
"E" --> "DD" --> "CCC" --> "BBBB" --> "AAAAA" --> null
```
The string lengths in the result are 1, 2, 3, 4, 5.  

### non static method `countElements()`

This method acts on an instance of a linked list node and returns how many linked lists nodes are in the list that starts at the current node. 
This is a recursive method that will use the number produced by the node at the next pointer (if its not null) and manipulate that result. 

***Example 3:*** 
If the list contains `"A" --> "B" --> "C" --> null`. 
* When you call `countElements()` on the first element (containing "A") the value will be `3`.
* When you call `countElements()` on the second element (containing "B") the value will be `2`.
* When you call `countElements()` on the third element (containing "C") the value will be `1`.


### non static method `toString()`

This method acts on an instance of a linked list node and returns a string containing all of the strings in the list separated by commas (without a comma at the end). 
This is a recursive method that will use the number produced by the node at the next pointer (if its not null) and manipulate that result. 

***Example 4:*** 
If the list contains `"A" --> "B" --> "C" --> null`. 
* When you call `toString()` on the first element (containing "A") the value will be `A, B, C`.
* When you call `toString()` on the second element (containing "B") the value will be `B, C`.
* When you call `toString()` on the third element (containing "C") the value will be `C`.
(note that none of these end in a comma after the "C"). 

### non static method `append(StringLL inNode)`
This is a **recursive** method that appends inNode at the end of the linked list. 
Hint: if the current node is the end the next pointer should be changed from null to point to inNode, 
if its not the end you have a linked list node in next so you need to ask that node to do it. 

### Testing
You should provide 15 unit tests in your main method in the `QSLenTester.java` file that show your new methods satisfy all of the requirements. 
These can be formatted using print statements or java assert statements (no need to use JUnit).
Each test should be clearly labeled within the main method, and accompanied by text explaining the expected value for the test and why that test is included.

**Note**
I have provided a utility function `cut()` which returns the pointer of the second element and sets the next pointer of the first to null. For example is the list `myList` is `"A" --> "B" --> "C" --> null`, and I run `myList = myList.cut()`, then `myList` is now `"B" --> "C" --> null`

## Grading
* `mergeSortLengths` -- 40 pts
* `append` -- 15 pts
* `countElements` -- 10 pts
* `toString` -- 10 pts
* unit tests -- 15 pts (1 pts each) 

Lateness rule: -10 pts for 1 day of lateness / - 20 pts for 2 days of lateness / 0 after that, but you still have to turn in your work

