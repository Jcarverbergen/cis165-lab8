# cis165-lab8
cis165-lab8/   geometry.cpp   README.md   AI_REFLECTION.md

Program Description
This program is a Geometry Calculator that allows the user to calculate the area of a circle, rectangle, or triangle. It displays a menu with four choices. The user selects an option, enters the required dimensions, and the program calculates and displays the area.

The program also includes input validation. Negative dimensions are not allowed, but zero is accepted. If the user selects option 4, the program exits without asking for dimensions or calculating an area. Invalid menu choices display an error message.

Initial Plan
I will create a Geometry Calculator that displays a menu with four choices: circle, rectangle, triangle, and quit.

I will use an integer variable to store the menu choice and floating-point variables to store the dimensions and calculated area. I will also create a named constant called PI with the value 3.14159.

I will use if, else if, and else statements to determine which calculation the user wants. For a circle, I will multiply PI by the radius twice. For a rectangle, I will multiply the length by the width. For a triangle, I will multiply the base by the height and then multiply by 0.5.

Before calculating an area, I will check that the dimensions are not negative. Zero will be allowed. If the user enters an invalid menu choice, the program will display an error. If the user chooses 4, the program will display a goodbye message and end.

Variables Used

Variable	Purpose
PI	Stores the constant value 3.14159.
choice	Stores the user's menu selection.
radius	Stores the circle's radius.
length	Stores the rectangle's length.
width	Stores the rectangle's width.
base	Stores the triangle's base.
height	Stores the triangle's height.
area	Stores the calculated area.
Formulas Used
Circle:

Area = PI * radius * radius

Rectangle:

Area = length * width

Triangle:

Area = base * height * 0.5

The program uses 3.14159 for PI and floating-point calculations for accurate decimal results.

How to Compile and Run
The program uses C++17.

To compile with g++, use:


bash
g++ -std=c++17 -Wall -Wextra geometry.cpp -o geometry
To run on Mac or Linux:


bash
./geometry
On Windows:


bash
geometry.exe
Testing and Results
The expected results were calculated before testing. I ran the program using the required test cases and compared the actual output with the expected output.

The program displays calculated areas to five decimal places.

Test 1: Circle
Input:

Choice: 1
Radius: 2
Expected Calculation:

3.14159 * 2 * 2 = 12.56636

Expected Output:

Area of the circle: 12.56636
Actual Output:

Area of the circle: 12.56636
Status: PASS

Test 2: Rectangle
Input:

Choice: 2
Length: 3
Width: 4.5
Expected Calculation:

3 * 4.5 = 13.5

Expected Output:

Area of the rectangle: 13.50000
Actual Output:

Area of the rectangle: 13.50000
Status: PASS

Test 3: Triangle
Input:

Choice: 3
Base: 5
Height: 3
Expected Calculation:

5 * 3 * 0.5 = 7.5

Expected Output:

Area of the triangle: 7.50000
Actual Output:

Area of the triangle: 7.50000
Status: PASS

Test 4: Quit
Input:

Choice: 4
Expected Result:

The program displays a goodbye message and ends without asking for dimensions or calculating an area.

Actual Result:

The program displayed the goodbye message and ended without requesting dimensions.

Status: PASS

Test 5: Invalid Menu Choices
First Run Input:

Choice: 0
Expected Result:

Display an invalid-choice error.

Actual Result:

The program displayed an invalid-choice error.

Status: PASS

Second Run Input:

Choice: 5
Expected Result:

Display an invalid-choice error.

Actual Result:

The program displayed an invalid-choice error.

Status: PASS

Test 6: Negative Circle Radius
Input:

Choice: 1
Radius: -1
Expected Result:

Display an error explaining that the radius cannot be negative.

Actual Result:

The program displayed the negative-radius error.

Status: PASS

Test 7: Negative Rectangle Length
Input:

Choice: 2
Length: -1
Expected Result:

Display an error explaining that the length cannot be negative.

Actual Result:

The program displayed the negative-length error.

Status: PASS

Test 8: Negative Rectangle Width
Input:

Choice: 2
Length: 3
Width: -1
Expected Result:

Display an error explaining that the width cannot be negative.

Actual Result:

The program displayed the negative-width error.

Status: PASS

Test 9: Negative Triangle Base
Input:

Choice: 3
Base: -1
Expected Result:

Display an error explaining that the base cannot be negative.

Actual Result:

The program displayed the negative-base error.

Status: PASS

Test 10: Negative Triangle Height
Input:

Choice: 3
Base: 5
Height: -1
Expected Result:

Display an error explaining that the height cannot be negative.

Actual Result:

The program displayed the negative-height error.

Status: PASS

Test 11: Zero Radius
Input:

Choice: 1
Radius: 0
Expected Calculation:

3.14159 * 0 * 0 = 0

Expected Output:

Area of the circle: 0.00000
Actual Output:

Area of the circle: 0.00000
Status: PASS

Test 12: Additional Valid Calculation
Input:

Choice: 2
Length: 6
Width: 2.5
Expected Calculation:

6 * 2.5 = 15

Expected Output:

Area of the rectangle: 15.00000
Actual Output:

Area of the rectangle: 15.00000
Status: PASS

This additional test checks whether the rectangle calculation works correctly with decimal dimensions.

Code Explanation
1. How does your selection logic send each choice to the right calculation?
The program uses if, else if, and else statements to check the user's menu selection. Each choice has its own section of code. Choice 1 calculates a circle, choice 2 calculates a rectangle, choice 3 calculates a triangle, and choice 4 exits the program. Any other number displays an error.

2. Why is radius * radius correct while radius ^ 2 is not?
In C++, the * operator performs multiplication. Multiplying the radius by itself correctly squares the number. The ^ operator is actually a bitwise XOR operator in C++, not an exponent operator.

3. Why does the triangle calculation use 0.5 rather than integer division 1 / 2?
The value 0.5 represents one-half as a floating-point number. Using 1 / 2 with integers would produce zero because integer division removes the decimal portion. Using 0.5 makes sure the triangle calculation produces the correct area.

4. Where do you check negative dimensions, and how do you handle zero and choice 4?
The program checks each dimension using an if statement before calculating the area. If a dimension is negative, an error message is displayed and the calculation is skipped. Zero is accepted because the condition only checks whether the dimension is less than zero. Choice 4 displays a goodbye message and ends without asking for dimensions.

Final Testing and Submission
The program was tested using the required test cases and an additional valid calculation.

The tests check that the program:

Displays all four menu choices.
Calculates circle, rectangle, and triangle areas correctly.
Uses the correct value for PI.
Accepts floating-point dimensions.
Rejects negative dimensions.
Accepts zero.
Displays an error for invalid menu choices.
Exits correctly when choice 4 is selected.
