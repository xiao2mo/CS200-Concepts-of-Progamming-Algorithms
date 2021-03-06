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
* Dynamic variables
* Dynamic arrays

## Rules

* For **in-class labs**, collaboration is allowed.
    * If you work with another student on an assignment, make sure that you both
    turn in a copy of the work, and also mention in the D2L comments who you worked with.
    * You can also ask classmates questions if you're unsure on something.
    * You can ask the instructor for help at any time.

## Reference

* [How to use Visual Studio](https://github.com/Rachels-Courses/Course-Common-Files/blob/organized/STUDENT_REFERENCE/HOW_TO/Visual_Studio.md)
* [How to use Code::Blocks](https://github.com/Rachels-Courses/Course-Common-Files/blob/organized/STUDENT_REFERENCE/HOW_TO/Code_Blocks.md)
* [How to turn in code](https://github.com/Rachels-Courses/Course-Common-Files/blob/organized/STUDENT_REFERENCE/HOW_TO/Turning_in_code.md)


## Turn in

Once you are finished with a project, zip up the entire folder that contains
all source files and project/solution files. Turn in this zip file to **Desire2Learn**.

Also make sure to turn in a text file with your answers to the [question](#questions) section.







![horizontal rule](images/hr.png)

---

# Lab

## Program 1: Dynamic variables and arrays

### Part 1: Variables

In your program, create three pointers:

* myInt, an integer pointer.
* myStr, a string pointer.
* myFloat, a float pointer.

Afterward, you will allocate memory for each of these variables with the **new**
keyword. Note that the data-type that goes after new must match the pointer type. (See
the reference for sample code).

Then, assign values to each of the variables. Make sure to use the de-reference
operator!

* myInt = 20
* myStr = (your name)
* myFloat = 199.99

Display the value of each of the variables. You will also need a de-reference operator
here.

Finally, free the memory for each pointer using the delete keyword.

**Sample Output:**

        20        yourname      199.99


### Part 2: Arrays

Next, create three additional pointer variables:

* myIntArr, an integer pointer.
* myStrArr, a string pointer.
* myFloatArr, a float pointer.

Also create an integer variable named **size**.

Ask the use how big the arrays should be, and store their response in **size**.

For each of these "my____Arr" pointers, create a new **dynamic array** and
initialize its size to the value stored in the **size** variable.

Use a for-loop to iterate from *0* to *size*, asking the user to enter
a value for each element of myIntArr, myFloatArr, and myStrArr.

After they enter values for these, display them back.

Finally, after the for loop is finished, make sure to free the memory of all your dynamic arrays.

**Sample Output:**

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

### Hints

<details>
<summary><strong>
        Using the new command for a dynamic variable
</strong></summary>

```c++
int * myInt = new int;
```

Make sure to open the [helper doc](https://github.com/Rachels-Courses/CS200-Concepts-of-Progamming-Algorithms/blob/2017-06-Summer/Assignments/In-class%20Labs/Lab%2004b%20-%20Dynamic%20arrays%20-%20Helper.md)
for help.

</details>

<details>
<summary><strong>
        Using the delete command for a dynamic variable
</strong></summary>

```c++
delete myInt;
```

Note that this is how you delete a dynamic variable, **not** a dynamic array.

</details>


---

## Program 2:  Lotto numbers

![Lottery balls](images/lottoballs.png)

You will use a random number generator for this program, so you will need the
following libraries:

```c++
#include <cstdlib>      // to use rand()
#include <ctime>        // to use time()
```
        
Seed the random number generator with:

```c++
srand( time( NULL ) ); // (At the beginning of main())
```

**Seed the random number generator:** 
You only need to seed the generator **once** -- at the beginning of the program.

**Get the *size* of the dynamic array:** 
Then, ask the user to enter the amount of lotto balls there will be.
Store the value in an integer variable to keep track of the **size**.

**Create the dynamic array:** 
Create a dynamic array of **integers** called ```lottoNumbers```. It will be the **size** that the user specified above.

**Iterate through the array:**
Create a for loop that goes from *0* to the size of your ```lottoNumbers``` array. Inside the loop...

* Set each element's value to a random number between 0 and 100.
   * To generate a random number, you need to use the rand() function: ```rand()```.
   * To generate a number between 0 and 9, you will use: ```rand() % 10;```
   * Make sure you're assigning it to a variable...  ```int example = rand() % 10;```
* Display the value of each lotto ball while generating.

At the end of the program, delete the dynamic array before the program ends. (Before the return 0;)

**Sample Output:**

        How many lotto balls will there be? 
        >> 5
        57      11      74      91      35



### Hints

<details>
<summary><strong>
        Using the new command for a dynamic array
</strong></summary>

```c++
int numberCount = 10;
int* numberList = new int[ numberCount ];
```

</details>

<details>
<summary><strong>
        Using the delete command for a dynamic array
</strong></summary>

```c++
delete [] numberList;
```

</details>

<details>
<summary><strong>
        Iterating through each element of the dynamic array
</strong></summary>

Use your variable that stores the size of the array to use in your for loop.

```c++
for ( int i = 0; i < numberCount; i++ )
{
        cout << numberList[i] << "\t";
}
```

</details>


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
    
    string cityName;

    ifstream input;

    if ( city == 1 )
    {
        input.open( "from_kc.txt" );
        cityName = "Kansas City";
    }
    else
    {
        input.open( "from_seattle.txt" );
        cityName = "Seattle";
    }

    int locationCount = 0;
    string * locations;
    int * distances;

    // Load in amount of locations

    // Allocate memory for locations and distances

    // Use a for loop to load in all the data from text files

    // Display all the data to the screen with cout

    // After the for loop, free the memory of locations and distances.

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

* AssignManagers - pass in ```managerNames``` and ```employeeManagers```.
* DisplayEmployees - pass in ```employeeNames``` and ```employeeManagers```.




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



### Example output

        Employee 0	Serena	 Manager: Artemis
        Employee 1	Amy	 Manager: Artemis
        Employee 2	Raye	 Manager: Luna
        Employee 3	Lita	 Manager: Artemis
        Employee 4	Mina	 Manager: Artemis

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

