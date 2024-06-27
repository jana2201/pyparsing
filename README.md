# Report for Assignment 1

## Project chosen

Name: PyParsing

URL: https://github.com/pyparsing/pyparsing 

Number of lines of code and the tool used to count it: 33356, Lizard

Programming language: Python

## Coverage measurement

### Existing tool

We have used coverage.py to measure the test coverage. This was done by issuing the command: coverage run –branch -m unittest discover, followed by: coverage report

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/5142ccff-96be-4d00-8f33-1fc7f59c6214)

### Your own coverage tool

Jovana Vukmirovic

Function 1: _generateDefaultName()

Link to the commit: https://github.com/jana2201/pyparsing/commit/ae9afd14e05a0267e2bcb48ae6b22e599adcea33 

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/7f8ea244-301a-4565-91be-6d6890b569fe)

Function 2: __iand__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/ae9afd14e05a0267e2bcb48ae6b22e599adcea33 

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/e6050016-ba50-47cc-9368-0fd3fb1bd001)


Ana Grbic

Function 1: __init__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/da40a652770049ea1c4bc727503fc5b90ae2a697

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/e6f0c972-24fc-4806-a919-e1935a24fd04)

Function 2: preParse()

Link to the commit:
https://github.com/jana2201/pyparsing/commit/da40a652770049ea1c4bc727503fc5b90ae2a697

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/ee276f42-6bef-47a8-84ef-1d8b61babe6b)


Andreea Ranete

Function 1: __ior__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/e936f232d4c6f1143da2cac17c63885c45b0fe42 

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/47ba34cd-ec35-4643-a83e-d092a79aa9f6)

Function 2: __ixor__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/e936f232d4c6f1143da2cac17c63885c45b0fe42  

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/f35e3c44-5cc3-4fd1-b044-5f78d5df15ac)


Anastasia Brovko

Function 1: __iadd__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/9c39e570a7352339d041637ae38c2f6394b28657

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/0c6a7de8-0ab8-42e0-9e74-715d638294ee)
	
Function 2: __ilshift__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/9c39e570a7352339d041637ae38c2f6394b28657#diff-651b49e05968bd7f42614f05b7e9d94b30f52db27eb692ce20ef87e9799c624f

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/97d40471-3fe4-49a6-b382-7ebaba7819e8)

## Coverage improvement

### Individual tests

Jovana Vukmirovic

Test 1: _generateDefaultName()

Link to the commit: https://github.com/jana2201/pyparsing/commit/9d91088f5330118280d710f2299545fe1532fcd9 

Old coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/7f8ea244-301a-4565-91be-6d6890b569fe)

New coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/5ab9970c-bb56-4216-87c6-df7c0a907f5a)

The branch coverage has increased from 50% to 100%. The enhanced test now also executes the first if-statement of _generateDefaultName(), which led to this improvement. To achieve this, the input parameter for class CharsNotIn needs to be long enough and should contain a wide range of characters. This is because we want to make sure that the function _collapse_string_to_ranges() in _generateDefaultName() returns a string that has a length of at least 17 characters, to trigger the first if-statement.

Test 2: __iand__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/878a19ca82fa6b81e6975466ae0875ec6bfb3d47 

Old coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/e6050016-ba50-47cc-9368-0fd3fb1bd001)

New coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/d21e1b65-9c09-4a96-84de-2b9ee39d54f4)

The branch coverage has increased from 0% to 100%. The new test executes both if-statements. The iand() function is triggered when the “&=” operator is used on an object that belongs to the Each class. The first if-statement is executed when the variable on the right side of the “bitwise AND” is a string type. The second if-statement is executed when the variable on the right side of the operation is neither of a string type nor a ParserElement type. In this case, the function returns NotImplemented and that results in a TypeError that needs to be caught by the test. The third branch is executed during the testing of the first if-statement.

Ana Grbic

Test 1: __init__()

Link to the commit:
https://github.com/jana2201/pyparsing/commit/5c34eda77a57327aa44913274a0019fd3018205d

Old coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/e6f0c972-24fc-4806-a919-e1935a24fd04)

New coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/8fd9f924-8e9f-4676-a2bc-9aaf73d15b1c)

The branch coverage has increased from 33% to 100% in the function __init__(). The function is an initialiser and therefore is executed when an instance of class White is created. Two new tests were created for it within class TestInitWhite. testWhiteMaxValue tests when ‘max’ is bigger than 0 (in the test it is specifically 5) and testWhiteExactValue when ‘exact’ is bigger than 0 (in the test it is specifically 3) by creating an instance of class White where that is the case. When ‘max’ is bigger than 0, the first branch of the function is entered (branch [60]) and ‘self.maxLen’ is set to ‘max’ while ‘minLen’ remains the same, which is then asserted to be true in the test. As for when exact is bigger than 0, the third branch of the function is entered (branch [62]) and ‘self.maxLen’ is set to ‘exact’ and ‘self.minLen’ is set to ‘exact’ as well, both of which are asserted to be true in the test.

Test 2: preParse()

Link to the commit:
https://github.com/jana2201/pyparsing/commit/7994d4d92d879098d3ed861302d3d9265bd76b07

Old coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/ee276f42-6bef-47a8-84ef-1d8b61babe6b)

New coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/59bd9f4f-0d72-42d0-a705-ad16d665b0c5)

The branch coverage has increased from 50% to 100% in the function preParse(). The function processes an input string starting from a specific location (‘loc’). A test was created for it, called testPreParseZero, within class TestPreParse, which tests the function for when the input for ‘loc’ is 0 when creating a LineStart object and calling preParse on it. In function preParse, when ‘loc’ is set to 0, the first branch is entered (branch [70]) and the function returns ‘loc’ which is then asserted to be true in the test.


Andreea Ranete
	
Test 1: __ior__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/e936f232d4c6f1143da2cac17c63885c45b0fe42 

Old coverage results: 

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/47ba34cd-ec35-4643-a83e-d092a79aa9f6)

New coverage results: 

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/dcfb52b4-6782-4a69-8216-1559000de42b)

The branch coverage has increased from 0% to 100%. The new test executes all if-statements. The __ior__ function is triggered when the |= operator is used on an object that belongs to the MatchFirst class. The first if-statement is executed when the variable on the right side of the bitwise OR operation is of a string type. The second if-statement is executed when the variable on the right side of the operation is neither of a string type nor a ParserElement type. In this case, the function returns NotImplemented, which results in a TypeError that needs to be caught by the test. The third branch is executed when the variable on the right side of the operation is a ParserElement type. The function appends the ParserElement to the MatchFirst instance. 

Test 2: __ixor__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/e936f232d4c6f1143da2cac17c63885c45b0fe42 

Old coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/f35e3c44-5cc3-4fd1-b044-5f78d5df15ac)

New coverage results: 

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/ebd2986c-ced2-496e-af47-ff1b80939fae)

The branch coverage has increased from 0% to 100%. The new test executes all if-statements. The __ixor__ function is triggered when the ^= operator is used on an object that belongs to the Or class. The first if-statement is executed when the variable on the right side of the bitwise XOR operation is of a string type. The second if-statement is executed when the variable on the right side of the operation is neither of a string type nor a ParserElement type. In this case, the function returns NotImplemented, which results in a TypeError that needs to be caught by the test. The third branch is executed when the variable on the right side of the operation is a ParserElementtype. The function appends the ParserElementto the Or instance.


Anastasia Brovko

Test 1: __iadd__()

Link to the commit: https://github.com/jana2201/pyparsing/commit/9c39e570a7352339d041637ae38c2f6394b28657#diff-6e0c7d0043d4ff88ba528ad3efafdbf7e9e84d544215cc80b30307c1142cd9b0

Previous coverage: 

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/135d24d5-2e0c-442d-bc22-e3b3a757c1ad)

New coverage:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/8c0e7c94-459c-4b01-9d2d-98d79743b299)

With the new test module TestAddIadd I was able to increase the branch coverage from 50% to 100%.The tests trigger __iadd__ function when “+=” operation is applied to the object of the class Add. The first if-statement is executed when the variable to the right of the in-place addition is string type. 
The second if-statement is executed when the object on the right side of “+=” is neither a string nor ParserElement type. For instance, in my test, this is an element of type int.
The last branch is executed with the testing of the first if-statement

Test 2: __ilshift__() 

Link to the commit: https://github.com/jana2201/pyparsing/commit/9c39e570a7352339d041637ae38c2f6394b28657#diff-6e0c7d0043d4ff88ba528ad3efafdbf7e9e84d544215cc80b30307c1142cd9b0

Previous coverage:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/97d40471-3fe4-49a6-b382-7ebaba7819e8)

Improved coverage:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/c017fc5e-f4f9-4c13-8e51-c540fdbbcd6d)

With my test, the branch coverage increased from 57% to 100%. Function testForwardIlshiftInit tests the behavior of the left-shift operator “<<=”. The first branch is invoked when the element on the right of the operation is a string. The second branch is activated when the object on the right from “<<=” is of type Int.

### Overall

Old coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/f93d4bcb-01ac-4c0c-80b6-283c64b372e6)

New coverage results:

![afbeelding](https://github.com/jana2201/pyparsing/assets/121348797/1f5f6fc0-57e3-4e74-8313-993a31acb0fb)


## Statement of individual contributions

Jovana:
- Found the PyParsing open-source project
- Instrumented the _generateDefaultName() and __iand__ () functions
- Improved the branch coverage of the _generateDefaultName() and __iand__() functions

Ana:
- Instrumented the __init__() and preParse() functions
- Improved the branch coverage of the __init__() and preParse() functions

Anastasia:
- Ran coverage tools
- Instrumented the __iadd__() and __ilshift__() functions
- Created custom tests classes to test  __iadd__() and __ilshift__() functions

Andreea:
- Instrumented the __ior__() and __ixor__() functions
- Improved the branch coverage of the __ior__() and __ixor__() functions
