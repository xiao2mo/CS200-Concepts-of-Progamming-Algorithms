# CS 200 Lab 04b: Pointers and dynamic variables and arrays 

---

[Information](#information) |
[Helper](https://github.com/Rachels-Courses/CS200-Concepts-of-Progamming-Algorithms/blob/2017-06-Summer/Assignments/In-class%20Labs/Lab%2004b%20-%20Dynamic%20arrays%20-%20Helper.md) |
[Lab](#lab) | [
Questions](#questions)

---

# Information

## Lab topics

* Pointers

## Rules

* For **in-class labs**, collaboration is allowed.
    * If you work with another student on an assignment, make sure that you both
    turn in a copy of the work, and also mention in the D2L comments who you worked with.
    * You can also ask classmates questions if you're unsure on something.
    * You can ask the instructor for help at any time.

## Reference

* [Creating a new project in Visual Studio](https://github.com/Rachels-Courses/Course-Common-Files/blob/master/Visual-Studio/New%20project%20howto.md)

## Turn in

Once you are finished with a project, zip up the entire folder that contains
all source files and project/solution files. Turn in this zip file to **Desire2Learn**.

Also make sure to turn in a text file with your answers to the [question](#questions) section.







![horizontal rule](images/hr.png)

---

# Lab

## Program 1a: Dynamic variables

### A. Create three pointers

Declaring a pointer works like this:

```c++
// Declaring an integer pointer
int * myInt;
```

In your program, create three pointers:

* myInt, an integer pointer.
* myStr, a string pointer.
* myFloat, a float pointer.

### B. Allocate memory using each pointer

Allocating memory for a dynamic variable with a pointer works like this:

```c++
// Allocating memory for a dynamic variable
myInt = new int;
```

Using ```myInt```, ```myStr```, and ```myFloat```, you will use the **new** keyword to allocate memory for each one.

### C. Assign values to the variables

To assign a value to an item via its pointer, you must de-reference it first:

```c++
// Assignment statement with a pointer variable:
*myInt = 20;
```

For the three variables, ```myInt```, ```myStr```, and ```myFloat``` assign the following values:

* myInt = 20
* myStr = (your name)
* myFloat = 199.99

### D. Display the variable values

To display the value stored at an address, you must de-reference the pointer:

```c++
cout << *myInt << endl;
```

Display the values of each of the three variables, ```myInt```, ```myStr```, and ```myFloat```.

### E. Free the memory for the dynamic variables

To free the memory of a dynamic variable, you need to use the **delete** keyword:

```c++
// De-allocate (free) memory of a dynamic variable:
delete myInt;
```

Free the memory for all three variables: ```myInt```, ```myStr```, and ```myFloat```



### Example output

        20        yourname      199.99

---

## Program 1b: Dynamic arrays

Declaring a pointer works like this:

```c++
// Declaring an integer pointer
int * myInt;
```

In your program, create three pointers:

* myIntArr, an integer pointer.
* myStrArr, a string pointer.
* myFloatArr, a float pointer.


### B. Ask the user for the array size

Using ```cout```, display a message asking the user to enter the size of the arrays.

Create an **integer** variable named ```size```.

Get the user's input with ```cin``` and store it in ```size```.


### C. Allocate memory using each pointer

Allocating memory for a dynamic array with a pointer works like this:

```c++
// Allocating memory for a dynamic array, with some size SIZE
myInt = new int[ SIZE ];
```

Using ```myIntArr```, ```myStrArr```, and ```myFloatArr```, you will use the **new** keyword to allocate memory for each one.
Their sizes should all be the value stored in ```size```.


### D. Iterate through the arrays

Since each of our arrays' sizes are specified by the ```size``` variable,
we can use this in a **for loop** to iterate over each **element** of the arrays.

First, declare a counter variable. It should be an **integer** named ```i```.

Create a **for loop**.

1. First parameter: Initialize ```i``` to ```0```.
2. Second parameter: Loop while ```i``` is less than ```size```.
3. Third parameter: Increment ```i``` by one each time.

<details><summary><strong> More help </strong></summary>

```c++
int i;
for ( i = 0; i < size; i++ )
{
}
```

</details>

### E. Assign values to the elements of the array

You will do this step inside the **for loop**.

Using ```cout```, display the following text:

```c++
// Display "i" and the value of i.
cout << "i = " << i << endl;
```

* First, with ```cout```, you will ask the user to enter an integer value.

* Use ```cin``` to get their integer input, and store it in ```myIntArr``` at position ```i```.

* Second, with ```cout```, you will ask the user to enter a string value.

* Use ```cin``` to get their string input, and store it in ```myStringArr``` at position ```i```.

* Third, with ```cout```, you will ask the user to enter a float value.

* Use ```cin``` to get their float input, and store it in ```myFloatArr``` at position ```i```.

<details><summary><strong> More help </strong></summary>

```c++
cout << "Enter an int value: ";
cin >> myIntArr[i];
```

</details>



### F. Iterate through the arrays again

After the for loop is over, use ```cout``` to display a message, "Here is your data:".

You will need to create **another for loop**, with the same values as in step (D):

1. First parameter: Initialize ```i``` to ```0```.
2. Second parameter: Loop while ```i``` is less than ```size```.
3. Third parameter: Increment ```i``` by one each time.

<details><summary><strong> More help </strong></summary>

```c++
cout << myIntArr[i] << "\t" << myStringArr[i] << "\t" << myFloatArr[i] << endl;
```

</details>

### G. Display the array elements

Inside the **for loop**, you will display the elements of the arrays:

* Using ```cout```, display the value of ```myIntArr``` at position ```i```.
* Using ```cout```, display the value of ```myStringArr``` at position ```i```.
* Using ```cout```, display the value of ```myFloatArr``` at position ```i```.



### H. Free the memory for the dynamic variables

To free the memory of a dynamic variable, you need to use the **delete** keyword:

```c++
// De-allocate (free) memory of a dynamic array:
delete [] myInt;
```

After the **for loop** has completed, you will free the memory of the three arrays.

Free the memory for all three variables: ```myIntArr```, ```myStrArr```, and ```myFloatArr```


### Example output

        Enter array size:       3

        i = 0
                Enter int value:        2
                Enter string value:     cheese
                Enter float value       2.10

        i = 1
                Enter int value:        5
                Enter string value:     horse
                Enter float value:      9.92
                
        i = 2
                Enter int value:        1
                Enter string value:     cow
                Enter float value:      10.2

        Here is your data:

        2       cheese          2.10
        5       horse           9.92
        1       cow             10.2



---

## Program 2:  Lotto numbers

![Lottery balls](images/lottoballs.png)

Start out with the following code:

```c++
#include <iostream>
#include <cstdlib>      // to use rand()
#include <ctime>        // to use time()

int main()
{
    return 0;
}
```

### A. Seed the random number generator

We are going to be generating random numbers for this program.

To seed the random number generator, use the following code:

```c++
srand( time( NULL ) ); // (At the beginning of main())
```

You only need to seed the generator **once** -- at the beginning of the program.

This makes it so that each time we run the program, we will get different random values.


### B. Ask for the amount of lotto balls

Each lotto ball will have its own number, between 0 and 99, but that is for a later step.

Create an integer variable called ```size```.

Ask the user how many lotto balls they want.

Get the user's input with ```cin``` and store it in ```size```.

<details><summary><strong> More help </strong></summary>

```c++
int * lottoBalls;
```

</details>


### C. Allocate memory for the dynamic array of lottery balls

Create an integer pointer called ```lottoBalls```.

Using the ```lottoBalls``` pointer, **allocate memory for a dynamic array**.
Use the value of ```size``` as the array's size.

<details><summary><strong> More help </strong></summary>

```c++
lottoBalls = new int[ size ];
```

</details>


### D. Iterate through the array of lotto balls

Create a counter variable. It should be an integer, and its name should be ```i```.

To iterate through all of the lotto balls, we need a **for loop**.

1. First parameter: Initialize ```i``` to ```0```.
2. Second parameter: Loop while ```i``` is less than ```size```.
3. Third parameter: Increment ```i``` by one each time.


### E. Assign random numbers to each lotto ball

To generate a random number between *0* and *n*, we could use the following code:

```c++
// Random number example - generate a number between 0 and n-1.
int randomNumber = rand() % n;
```

Inside the **for loop**, we are going to use an **assignment statement**
to assign a random number to each lotto ball in the ```lottoBalls``` array.

Generate a **random number** between **0 and 99**, and store that random number
in ```lottoBalls``` at position ```i```.

*In other words, you are writing an assignment statement. ```lottoBalls[i]``` goes
on the Left Hand Side of the assignment statement, and the ```rand()``` call goes on the Right Hand Side.*



<details><summary><strong> More help </strong></summary>

```c++
lottoBalls[i] = rand() % 100;
```

</details>



### F. Display the value of each lotto ball

This will also go in the for loop, after you've assigned a value to the lotto ball at position ```i```.

After the assignment statement, use ```cout``` to display the value of ```lottoBall``` at position ```i```.


<details><summary><strong> More help </strong></summary>

```c++
cout << lottoBall[i] << "\t";
```

</details>


### G. Free the memory

After the **for loop** is over, you will need to **free up the memory** through the ```lottoBalls``` pointer.

This is a dynamic array, so make sure you use ```delete []``` when freeing its memory.


<details><summary><strong> More help </strong></summary>

```c++
delete [] lottoBalls;
```

</details>


### Example output

        Enter the amount of lottery balls to use: 5
        
        57      11      74      91      35




---

## Program 3: Build a buddy

Start with the following code:

```c++
string ears[3]      = { "   ^ ^   ",   "  n   n ",     "  *   *  " };
string heads[3]     = { " ( o_o ) ",   " ( x_x )" ,    " ( >_< ) " };
string bodies[3]    = { "/(     )\\",  "\\(     )/",   "o(     )o" };
string feet[3]      = { "  d   b   ",  "  @   @ ",     "  () () "  };

string * ptrEars;
string * ptrHead;
string * ptrBody;
string * ptrFeet;
```

For each body part, ask the user to enter a choice between 0 and 2.
With this index, assign the corresponding **pointer** to the address of the
**body part element chosen from the array**.

Once the user has chosen all parts, de-reference and output each pointer.

**Example output:**

        Enter ears (0 - 2): 0
        Enter head (0 - 2): 1
        Enter body (0 - 2): 2
        Enter feet (0 - 2): 1

           ^ ^   
         ( x_x )
        o(     )o
          @   @ 

        Again? (y/n):

### Hints


<details>
<summary><strong>
        Assigning the pointers
</strong></summary>

```c++
cin >> index;
ptrEars = &ears[ index ];
```

</details>


<details>
<summary><strong>
        Outputting the dereferenced pointers
</strong></summary>

```c++
cout << endl << *ptrEars << endl << *ptrHead << endl << *ptrBody << endl << *ptrFeet << endl;
```

</details>

---

## Program 4: Reading in data from a text file

Sometimes you will need to read in data, and you can't know how much data
there is at compile-time (that is, *while* you're writing the program.)
Dynamic arrays can come in handy here.

In your project folder, create two text files.

**from_kc.txt:**

                7
                Omaha           189
                St_Louis        248
                Wichita         200
                Oklahoma_City   353
                Branson         209
                Columbia        127
                Des_Moines      193

**from_seattle.txt:**

                5
                Portland        174
                Olympia         60
                Eugene          283
                Vancouver       143
                Sacramento      752

And begin your program with the following:

```c++
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main()
{
    cout << "Choose a starting point:" << endl
        << "1. Kansas City" << endl
        << "2. Seattle" << endl;

    int city;
    cin >> city;

    ifstream input;

    if ( city == 1 )
    {
        input.open( "from_kc.txt" );
    }
    else
    {
        input.open( "from_seattle.txt" );
    }

    int locationCount = 0;
    string * locations;
    int * distances;

    input.close();


    
    return 0;
}

```

The first item in each file is the **amount of cities** from the starting point (Kansas City or Seattle).
Each file has a different maount of locations, so you'll have to read in the first number
**before** you create your ```locations``` and ```distances``` arrays.

Read in the first number of the text file into ```locationCount```.

After you've read in the size, set up your two dynamic arrays with the size stored in locationCount.

The rest of the data in the file is in the format:

        CITY_NAME       DISTANCE

Use the following code to load in the city data:

```c++
for ( int i = 0; i < locationCount; i++ )
{
        input >> locations[i] >> distances[i];
}
```

Finally, once everything has been loaded in, display all the locations
and distances in a nice format.

**Make sure to delete your dynamic arrays at the end of the program!**

**Example output:**

        Choose a starting point:
        1. Kansas City
        2. Seattle
        1

        DISTANCE FROM KANSAS CITY TO...
        * 189 miles - Distance from Kansas City to Omaha
        * 248 miles - Distance from Kansas City to St_Louis
        * 200 miles - Distance from Kansas City to Wichita
        * 353 miles - Distance from Kansas City to Oklahoma_City
        * 209 miles - Distance from Kansas City to Branson
        * 127 miles - Distance from Kansas City to Columbia
        * 193 miles - Distance from Kansas City to Des_Moines


### Hints


<details>
<summary><strong>
        Reading the amount of locations from the text file
</strong></summary>

```c++
input >> locationCount;
```

</details>


<details>
<summary><strong>
        Creating the dynamic arrays
</strong></summary>

```c++
locations = new string[ locationCount ];
distances = new int[ locationCount ];
```

</details>

---

## Program 5: Array of pointers

An array can also store pointers. Just like we can have a single
pointer variable that points to the address of another variable,
we can also have an array of pointers which each point to different
(or the same) addresses.

For this program, start with the following code:

```c++
#include <iostream>
#include <string>
#include <cstdlib>      // for srand and rand
#include <ctime>        // for time
using namespace std;

const int MANAGER_COUNT = 2;
const int EMPLOYEE_COUNT = 5;

void AssignManagers( string managerNames[ MANAGER_COUNT ], string * employeeManagers[ EMPLOYEE_COUNT ] )
{
}

void DisplayEmployees( string employeeNames[ EMPLOYEE_COUNT ], string * employeeManagers[ EMPLOYEE_COUNT ] )
{
}

int main()
{
    srand( time( NULL ) );




    while ( true );
    return 0;
}

```

#### main()

We will have three arrays in this program:

* managerNames, a string array of managers' names
* employeeNames, a string array of employees' names
* employeeManagers, a string-pointer array, one for each employee, that is meant to point to a manager.

Declare the ```managerNames``` string array - its size should be the ```MANAGER_COUNT```. Then initialize the two manager names in this array.

Declare the ```employeeNames``` string array - its size should be the ```EMPLOYEE_COUNT```. Initialize five employee names in this array.

Declare the ```employeeManagers``` string-pointer array - its size should be ```EMPLOYEE_COUNT```. Do not initialize this array.

Afterward, call the two functions:

* AssignManagers - pass in ```managerNames``` and ```meployeeManagers```.
* DisplayEmployees - pass in ```employeeNames``` and ```meployeeManagers```.



***Example output:***

        Employee 0	Serena	 Manager: Artemis
        Employee 1	Amy	 Manager: Artemis
        Employee 2	Raye	 Manager: Luna
        Employee 3	Lita	 Manager: Artemis
        Employee 4	Mina	 Manager: Artemis


#### AssignManagers()

We will use a random number generator to randomly select managers for each employee.

To get a number between 0 and 9, we would do ```int number = rand() % 10```.

Create a for-loop to iterate from 0 to ```EMPLOYEE_COUNT```:

* Create a variable called ```index```. Assign it the value of ```rand() % MANAGER_COUNT```.
* Get the **address** of ```managerNames[ index ]``` and assign it to the ```employeeManagers[i]``` item (if *i* is your for-loop counter.)

#### DisplayEmployees()

Use another for-loop, going over all the employees (use ```EMPLOYEE_COUNT``` again).

Each cycle of the loop, you will display:

* The value of the counter
* The employee name at this index (via ```employeeNames```)
* The manager for this employee (via ```employeeManagers```)

Note that you have to **de-reference** the employeeManagers element in order
to get the actual manager's name instead of the address of that variable.

### Hints

<details>
<summary><strong>
        Creating non-pointer arrays and initializing them
</strong></summary>

```c++
string managerNames[ MANAGER_COUNT ] = { "Artemis", "Luna" };
string employeeNames[ EMPLOYEE_COUNT ] = { "Serena", "Amy", "Raye", "Lita", "Mina" };
```

</details>

<details>
<summary><strong>
        Creating an array of pointers
</strong></summary>

```c++
string * employeeManagers[ EMPLOYEE_COUNT ];
```

</details>


<details>
<summary><strong>
        AssignManagers
</strong></summary>

```c++
void AssignManagers( string managerNames[ MANAGER_COUNT ], string * employeeManagers[ EMPLOYEE_COUNT ] )
{
    for ( int i = 0; i < EMPLOYEE_COUNT; i++ )
    {
        int index = rand() % MANAGER_COUNT;
        employeeManagers[i] = &managerNames[ index ];
    }
}
```

</details>


<details>
<summary><strong>
        DisplayEmployees
</strong></summary>

```c++
void DisplayEmployees( string employeeNames[ EMPLOYEE_COUNT ], string * employeeManagers[ EMPLOYEE_COUNT ] )
{
    for ( int i = 0; i < EMPLOYEE_COUNT; i++ )
    {
        cout << "Employee " << i << "\t" << employeeNames[i] << "\t Manager: " << *employeeManagers[i] << endl;
    }
}
```

</details>





![horizontal rule](images/hr.png)


# Questions

1. Using a pointer, how do you allocate memory for a new dynamic variable?
1. Using a pointer, how do you allocate memory for a new dynamic array?
1. How do you deallocate memory for a dynamic variable?
1. How do you deallocate memory for a dynamic array?
