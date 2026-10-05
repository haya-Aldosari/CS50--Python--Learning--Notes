## video 1: Python Syntax

## Python Syntax

Python has a simpler syntax compared with C.

A basic Python program can be written with much less code because we do not need things such as:

```text
#include
main()
;
{}
```

---

## Printing

In C:

```c
printf("Hello, world\n");
```

In Python:

```python
print("Hello, world")
```

Python uses the built-in:

```python
print()
```

function to display output.

---

## No Semicolon

In C, statements usually end with:

```c
;
```

In Python, we normally write:

```python
print("Hello")
```

without a semicolon.

---

## No Curly Braces

C uses curly braces to define blocks of code:

```c
{
    // code
}
```

Python does not use `{}` for this purpose.

Instead, Python uses **indentation**.

---

## Indentation

Indentation is an important part of Python syntax.

Example:

```python
if x > 0:
    print("Positive")
```

The indented line belongs to the `if` block.

---

## Variables

In C, we specify the variable type:

```c
int x = 10;
```

In Python:

```python
x = 10
```

We assign the value directly without writing the type before the variable name.

---

## Comments

Comments in Python use:

```python
# This is a comment
```

instead of:

```c
// This is a comment
```

---

## Python vs C Syntax

```text
C                         Python

printf()                  print()
;                         not required
{ }                       indentation
// comment                # comment
int x = 10;               x = 10
```

Python removes much of the extra syntax used in C, making the code shorter and easier to read.

---

## video 2: Python Data Types

Python has different data types used to represent different kinds of values.

Common examples include:

```python
x = 10          # int
y = 3.5         # float
name = "Haya"   # str
active = True   # bool
```

---

## Integer

`int` represents whole numbers.

```python
x = 10
y = -5
```

```text
int → whole numbers
```

---

## Float

`float` represents numbers with decimal points.

```python
price = 10.5
```

```text
float → decimal numbers
```

---

## String

`str` represents text.

```python
name = "Haya"
```

Strings are written inside quotation marks.

```text
str → text
```

---

## Boolean

`bool` represents a value that can be:

```python
True
False
```

Example:

```python
is_student = True
```

---

## List

A `list` can store multiple values together.

```python
numbers = [1, 2, 3, 4]
```

Values are accessed using an index:

```python
numbers[0]
```

---

## Tuple

A `tuple` stores multiple values together, similar to a list.

```python
numbers = (1, 2, 3)
```

A tuple is **immutable**, meaning its values cannot be changed after it is created.

---

## Set

A `set` stores a collection of **unique values**.

```python
numbers = {1, 2, 3}
```

Duplicate values are removed automatically.

Example:

```python
numbers = {1, 2, 2, 3}

print(numbers)
```

Result:

```text
{1, 2, 3}
```

---

## Dictionary

A dictionary stores data using **keys and values**.

```python
person = {
    "name": "Haya",
    "age": 21
}
```

A value can be accessed using its key:

```python
person["name"]
```

---

## Checking the Type

Python can identify the data type of a value using:

```python
type()
```

Example:

```python
x = 10

print(type(x))
```

## video 3: Input

Python provides the built-in:

```python
input()
```

to receive input from the user.

Example:

```python
name = input("What's your name? ")
print(name)
```

---

## `input()` Returns a String

The value returned by `input()` is treated as a **string**, even when the user enters a number.

```python
age = input("Age: ")
```

So if we need an integer, we convert it using:

```python
age = int(input("Age: "))
```

---

## Type Conversion

Python can convert values between data types.

```python
int()
float()
str()
```

Example:

```python
x = int(input("x: "))
y = int(input("y: "))

print(x + y)
```

---

## CS50 Input Functions

Input can also be taken using functions from the CS50 library.

```python
from cs50 import get_string, get_int
```

Examples:

```python
name = get_string("Name: ")
age = get_int("Age: ")
```

---

## video 4: Python Exceptions

## Exceptions

An **exception** is an error that happens while the program is running.

For example, converting invalid input to an integer can cause an error.

```python
x = int(input("x: "))
```

If the user enters text instead of a number, Python raises an exception.

---

## `try`

Python allows us to test code that might cause an error using:

```python
try:
```

Example:

```python
try:
    x = int(input("x: "))
```

---

## `except`

If an error happens, we can handle it using:

```python
except:
```

Example:

```python
try:
    x = int(input("x: "))
except:
    print("Invalid input")
```

This prevents the program from stopping immediately when an error occurs.

---

## `ValueError`

One common exception is:

```text
ValueError
```

It can happen when a value has the wrong format for an operation.

Example:

```python
try:
    x = int(input("x: "))
except ValueError:
    print("Not an integer")
```

---

## Handling Errors

Instead of allowing the program to crash:

```text
Error
↓
Program stops
```

we can handle the exception:

```text
try
↓
Run code
↓
Error?
↓
except
↓
Handle the error
```

---


## video 5: – Functions in Python

A **function** is a reusable block of code that performs a specific task.

Python already provides built-in functions such as:

```python
print()
input()
int()
```

---

## Creating a Function

A function is created using:

```python
def
```

Example:

```python
def hello():
    print("Hello")
```

---

## Calling a Function

Defining a function does not run it automatically.

To execute it, we call the function by its name:

```python
hello()
```

---

## Passing Values

A function can receive values when it is called.

```python
def hello(name):
    print(f"Hello, {name}")
```

Then:

```python
hello("Haya")
```

The value is passed into the function and used inside it.

---

## Returning a Value

A function can send a result back using:

```python
return
```

Example:

```python
def square(n):
    return n * n
```

Then:

```python
x = square(5)
```

The returned value can be stored and used later.

---

## Video 10: Mario3 and Nested Loops

This lesson continues the Mario exercise in Python and introduces **nested loops**, where one loop runs inside another loop.

Nested loops are useful when a program needs to repeat something across multiple rows and columns, such as creating patterns, grids, or shapes.

## Nested Loops

A nested loop consists of:

- An **outer loop**, which controls the number of rows.
- An **inner loop**, which controls what happens inside each row.

Example:

```python
for i in range(3):
    for j in range(3):
        print("#", end="")
    print()
```

Output:

```text
###
###
###
```

The outer loop runs three times, creating three rows.

For every iteration of the outer loop, the inner loop also runs three times and prints three `#` characters.

## Using `end=""`

Normally, Python's `print()` function moves to a new line after printing.

```python
print("#")
```

However, using:

```python
print("#", end="")
```

keeps the next output on the same line.

After the inner loop finishes, a normal:

```python
print()
```

is used to move to the next line.

## Video 11: Average in Python

This lesson demonstrates how Python lists can be used to store multiple values and calculate their average.

It also shows how Python provides built-in functions that simplify operations that would require more manual work in languages such as C.

## Python Lists

A list can store multiple values inside one variable.

Example:

```python
scores = [72, 73, 33]
```

Unlike arrays in C, Python lists can grow dynamically, so their size does not need to be defined in advance.

An empty list can be created using:

```python
scores = []
```

## Adding Elements with `append()`

The `append()` method is used to add a new element to the end of a list.

Example:

```python
scores.append(72)
scores.append(73)
scores.append(33)
```

The list will become:

```python
[72, 73, 33]
```

This makes it easy to collect values dynamically from the user.

## Using a Loop to Collect Values

Instead of writing every value manually, a loop can be used.

```python
from cs50 import get_int

scores = []

for i in range(3):
    scores.append(get_int("Score: "))
```

The loop runs three times and adds every entered score to the `scores` list.

## `sum()` Function

Python provides the built-in `sum()` function to calculate the total of all numeric elements in a list.

```python
sum(scores)
```

For example:

```python
scores = [72, 73, 33]
print(sum(scores))
```

Output:

```text
178
```

## `len()` Function

The `len()` function returns the number of elements in a list.

```python
len(scores)
```

For:

```python
scores = [72, 73, 33]
```

the result is:

```text
3
```

## Calculating the Average

The average can be calculated by dividing the total of the values by the number of values.

```python
average = sum(scores) / len(scores)
```

Then the result can be displayed using an f-string:

```python
print(f"Average: {average}")
```

Complete example:

```python
from cs50 import get_int

scores = []

for i in range(3):
    scores.append(get_int("Score: "))

average = sum(scores) / len(scores)

print(f"Average: {average}")
```

## F-Strings

Python f-strings allow variables and expressions to be included directly inside strings.

Example:

```python
average = 85

print(f"Average: {average}")
```

They can also contain expressions directly:

```python
print(f"Average: {sum(scores) / len(scores)}")
```

However, storing the result in a variable can make the code easier to read.

## Video 12: Uppercase in Python

This lesson demonstrates how to work with strings in Python and convert text from lowercase to uppercase.

Python provides built-in string methods that make text manipulation much simpler compared to implementing the same logic manually.

## Getting Text from the User

A string can be received from the user using `input()`:

```python
text = input("Before: ")
```

The entered value is stored as a string and can then be processed character by character or using Python's built-in string methods.

## Iterating Through a String

Python allows us to loop directly through the characters of a string.

```python
for c in text:
    print(c)
```

If the user enters:

```text
hello
```

the loop processes each character separately:

```text
h
e
l
l
o
```

There is no need to manually access every character using its index.

## Converting Characters to Uppercase

Python strings provide the `.upper()` method.

```python
letter = "h"

print(letter.upper())
```

Output:

```text
H
```

## Using `.upper()` on the Entire String

Instead of converting one character at a time, Python can convert the entire string directly:

```python
text = input("Before: ")

print("After:", text.upper())
```

This produces the same result with much less code.

For example:

```text
Before: hello world
After: HELLO WORLD
```

## Video 13: Command Line Arguments

Command line arguments allow us to give values to the program when we run it from the terminal instead of asking for them later using `input()`.

For example:

```python
python argv.py Haya
```

Here, `Haya` is a command line argument.

## `sys` Module

To work with command line arguments, Python provides the `sys` module.

We can import `argv` from it:

```python
from sys import argv
```

## `argv`

`argv` stores the command line arguments in a list.

For example, if we run:

```python
python argv.py Haya
```

the list contains the program name and the argument.

```python
argv[0]
```

contains the name of the Python file:

```text
argv.py
```

and:

```python
argv[1]
```

contains:

```text
Haya
```

## Using `len()`

Because `argv` is a list, `len()` can be used to check how many elements it contains.

```python
from sys import argv

if len(argv) == 2:
    print(f"hello, {argv[1]}")
else:
    print("hello, world")
```

If one argument is provided, the program prints it.

## Looping Through `argv`

Since `argv` is a list, we can also loop through it.

```python
from sys import argv

for arg in argv:
    print(arg)
```

The loop goes through the command line arguments one by one.

It can also be written using indexes:

```python
from sys import argv

for i in range(len(argv)):
    print(argv[i])
```

## List Slicing

We can use slicing if we do not want to include the first element of `argv`.

```python
from sys import argv

for arg in argv[1:]:
    print(arg)
```

`argv[1:]` starts from index `1`, so the program filename stored in `argv[0]` is skipped.

## Video 14: sys exit

Instead of importing only `argv`, the entire `sys` module can be imported:

```python
import sys
```

When importing the whole module, `argv` is accessed using:

```python
sys.argv
```

## Checking Command Line Arguments

The program can check the number of command line arguments using `len()`:

```python
if len(sys.argv) != 2:
    print("Missing command-line argument")
```

`sys.argv` contains the command line arguments, so `len(sys.argv)` tells us how many elements were provided.

## `sys.exit()`

`sys.exit()` is used to stop the program.

```python
sys.exit(1)
```

For example:

```python
import sys

if len(sys.argv) != 2:
    print("Missing command-line argument")
    sys.exit(1)

print(f"hello, {sys.argv[1]}")
```

If the required argument is missing, the program prints the message and stops immediately.

## Exit Codes

An exit code indicates whether the program finished successfully or encountered a problem.

```python
sys.exit(0)
```

`0` indicates that the program finished successfully.

```python
sys.exit(1)
```

`1` indicates that something went wrong.

Example:

```python
import sys

if len(sys.argv) != 2:
    print("Missing command-line argument")
    sys.exit(1)

print(f"hello, {sys.argv[1]}")
sys.exit(0)
```

## Video 15: Linear Search

Linear search is used to search for a value inside a collection of values.

In Python, we can create a list:

```python
numbers = [4, 6, 8, 2, 7, 5, 0]
```

## Searching Using `in`

Python allows us to check whether a value exists inside a list using the `in` keyword.

```python
if 0 in numbers:
    print("Found")
```

If the value exists in the list, the condition becomes `True`.

## Using `sys.exit()`

The search can be combined with `sys.exit()`:

```python
import sys

numbers = [4, 6, 8, 2, 7, 5, 0]

if 0 in numbers:
    print("Found")
    sys.exit(0)

print("Not found")
sys.exit(1)
```

If the number is found:

```python
sys.exit(0)
```

is used.

If the number is not found:

```python
sys.exit(1)
```

is used.

## Searching in a List of Strings

The same idea can be used with strings:

```python
names = ["Bill", "Charlie", "Fred", "George", "Ginny", "Percy", "Ron"]

if "Ron" in names:
    print("Found")
else:
    print("Not found")
```

Python searches the list to determine whether the value exists.

## Video 16: Phonebook

## Dictionary

A dictionary in Python stores data as **key-value pairs**.

For example, a phonebook can store a person's name as the key and their phone number as the value:

```python
people = {
    "Brian": "1000",
    "David": "2750"
}
```

In this dictionary:

- `"Brian"` and `"David"` are the keys.
- Their phone numbers are the corresponding values.

## Dictionary Syntax

Dictionaries are created using curly braces:

```python
{}
```

Each key is connected to its value using `:`:

## Searching the Phonebook

The program can ask the user for a name:

```python
from cs50 import get_string

name = get_string("Name: ")
```

Then `in` can be used to check whether the name exists in the dictionary:

```python
if name in people:
    print(f"Number: {people[name]}")
```

## Complete Example

```python
from cs50 import get_string

people = {
    "Brian": "1000",
    "David": "2750"
}

name = get_string("Name: ")

if name in people:
    print(f"Number: {people[name]}")
```

## Video 17: Pointers in Python

In C, comparing strings required dealing with how strings are stored in memory and using functions such as `strcmp`.

In Python, strings can be compared directly using `==`.

```python
s = input("s: ")
t = input("t: ")

if s == t:
    print("Same")
else:
    print("Different")
```

Python handles the comparison without requiring us to work with pointers manually.

## Swapping Values

In C, swapping two variables required more steps and an additional temporary variable.

In Python, values can be swapped directly:

```python
x = 1
y = 2

print(f"x is {x}, y is {y}")

x, y = y, x

print(f"x is {x}, y is {y}")
```

The line:

```python
x, y = y, x
```

swaps the values of `x` and `y`.

## Video 18: Files in Python

Instead of keeping the phonebook data inside the program, Python can save the data in a file.

In this example, the data is stored in a CSV file.

## Importing `csv`

Python provides the `csv` library for working with CSV files.

```python
import csv
```

## Opening a File

The `open()` function is used to open a file:

```python
file = open("phonebook.csv", "a")
```

`phonebook.csv` is the file name.

The opened file is stored in the variable:

```python
file
```

## Getting the Data

The program asks the user for a name and phone number:

```python
from cs50 import get_string

name = get_string("Name: ")
number = get_string("Number: ")
```

## `csv.writer()`

A writer is created for the opened file:

```python
writer = csv.writer(file)
```

This allows the program to write data into the CSV file.

## `writerow()`

The name and number are written as one row:

```python
writer.writerow([name, number])
```

The values are passed as a list:

```python
[name, number]
```

The resulting CSV data looks like:

```text
Carter,1000
```

## Closing the File

After finishing with the file, it is closed using:

```python
file.close()
```

## Complete Example

```python
import csv
from cs50 import get_string

file = open("phonebook.csv", "a")

name = get_string("Name: ")
number = get_string("Number: ")

writer = csv.writer(file)
writer.writerow([name, number])

file.close()
```

## Video 20: `with`, `r+`, `w+`, `a+` in Python

## Using `with`

Instead of opening a file and closing it manually:

```python
file = open("file.txt", "r")

# work with the file

file.close()
```

Python can use `with`:

```python
with open("file.txt", "r") as file:
    # work with the file
```

When using `with`, the file is closed automatically after finishing the block.

## `r+`

`r+` allows the file to be opened for both reading and writing.

```python
with open("file.txt", "r+") as file:
    ...
```

The file must already exist.

## `w+`

`w+` allows both writing and reading.

```python
with open("file.txt", "w+") as file:
    ...
```

If the file already contains data, its existing content is removed.

If the file does not exist, a new file is created.

## `a+`

`a+` allows reading and appending data to a file.

```python
with open("file.txt", "a+") as file:
    ...
```

New data is added to the end of the file instead of replacing the existing content.

If the file does not exist, it can be created.

## Video 23: Text to Speech in Python

Text to Speech allows a Python program to convert written text into spoken audio.

The main library used is:

```python
pyttsx3
```

---

## Install the Required Library

Install `pyttsx3` using:

```bash
pip install pyttsx3
```

---

## Import the Library

```python
import pyttsx3
```

---

## Initialize the Speech Engine

Create a text-to-speech engine using:

```python
engine = pyttsx3.init()
```

The engine is responsible for converting the text into spoken audio.

---

## Make Python Speak

Use `say()` to specify the text that should be spoken:

```python
engine.say("Hello World")
```

Then run the speech engine using:

```python
engine.runAndWait()
```

---

## Complete Example

```python
import pyttsx3

# Initialize the text-to-speech engine
engine = pyttsx3.init()

# Add text to be spoken
engine.say("Hello World")

# Run the speech engine
engine.runAndWait()
```

---

## Video 24: Speech Recognition in Python

Speech Recognition allows a Python program to listen to spoken audio through the microphone and convert it into text.

The main library used is:

```python
speech_recognition
```

`PyAudio` is also needed to access the microphone.

---

## Install the Required Libraries

Install SpeechRecognition:

```bash
pip install SpeechRecognition
```

Install PyAudio:

```bash
pip install PyAudio
```

---

## Import the Library

```python
import speech_recognition as sr
```

---

## Create a Recognizer

Create an object that will recognize the spoken audio:

```python
listener = sr.Recognizer()
```

---

## Access the Microphone

Use `Microphone()` to receive audio from the microphone:

```python
with sr.Microphone() as source:
    voice = listener.listen(source)
```

`listen()` waits for the user to speak and stores the recorded audio.

---

## Convert Speech to Text

The recorded audio can be converted into text using:

```python
command = listener.recognize_google(voice)
```

Then the recognized text can be printed:

```python
print(command)
```

---

## Complete Example

```python
import speech_recognition as sr

# Create the speech recognizer
listener = sr.Recognizer()

# Access the microphone
with sr.Microphone() as source:
    print("Listening...")

    # Listen to the user's voice
    voice = listener.listen(source)

    # Convert speech to text
    command = listener.recognize_google(voice)

    # Print the recognized text
    print(command)
```

---

## Video 25: Pillow in Python

`Pillow` is a Python library used for working with images.

It allows us to:

- Open images
- Display images
- Save images
- Apply filters
- Convert images
- Crop images

---

## Install Pillow

```bash
pip install pillow
```

---

## Import Pillow

To work with images:

```python
from PIL import Image
```

If we want to use image filters:

```python
from PIL import Image, ImageFilter
```

---

## Open an Image

First, we can store the image in a variable:

```python
img = Image.open("image.jpg")
```

`Image.open()` opens the image file using its name and extension.

For example:

```python
img = Image.open("before.jpg")
```

---

## Show an Image

To display the image:

```python
img.show()
```

This opens the image so we can see it.

---

## Save an Image

To save an image:

```python
img.save("new_image.jpg")
```

Inside `save()`, we specify the new image name and its extension.

---

# Image Filters

Pillow provides different types of image filters.

To use them:

```python
from PIL import Image, ImageFilter
```

In the example, a blur filter was applied to an image to compare the **before** and **after** results.

---

## Box Blur

One of the available filters is:

```python
ImageFilter.BoxBlur()
```

Example:

```python
filtered_img = img.filter(ImageFilter.BoxBlur(5))
```

The number inside `BoxBlur()` controls the strength of the blur.

A larger number produces a stronger blur effect.

The new image can then be saved:

```python
filtered_img.save("after.jpg")
```

This makes it possible to compare the original image with the filtered image.

---

# Convert an Image

The `convert()` method can be used to change the image mode.

Example:

```python
converted_img = img.convert("L")
```

`"L"` converts the image into a grayscale image.

The converted image can also be displayed or saved.

```python
converted_img.show()
```

---

# Crop an Image

The `crop()` method is used to select and keep only a specific part of an image.

First, a variable called `box` can be created:

```python
box = (100, 100, 400, 400)
```

Then it can be passed to `crop()`:

```python
cropped_img = img.crop(box)
```

---

## Understanding the Box Values

The `box` contains four numbers:

```python
(left, upper, right, lower)
```

For example:

```python
box = (100, 100, 400, 400)
```

means:

- `100` → Left position
- `100` → Upper position
- `400` → Right position
- `400` → Lower position

These values define the area of the image that will be kept.

The crop starts from the **left and upper coordinates** and ends at the **right and lower coordinates**.

---

## Example

```python
from PIL import Image, ImageFilter

img = Image.open("before.jpg")

img.show()

filtered_img = img.filter(ImageFilter.BoxBlur(5))

filtered_img.save("after.jpg")

converted_img = img.convert("L")

box = (100, 100, 400, 400)

cropped_img = img.crop(box)

cropped_img.show()
```

---

## Video 26: QR Code Generation in Python

This lesson explains how to generate a QR code in Python using the `qrcode` library and work with the generated image using `Pillow`.

Both libraries need to be installed before using them.

```bash
pip install qrcode
pip install pillow
```

## Importing the Libraries

```python
import qrcode
from PIL import Image
```

- `qrcode` is used to generate the QR code.
- `Pillow` is used to work with the generated image.

## Creating the QR Code

A variable can be created to store the generated QR code:

```python
img = qrcode.make("Hello World")
```

Here:

```python
qrcode.make()
```

creates the QR code.

The value written inside `make()` is the content that the QR code will contain.

For example:

```python
img = qrcode.make("https://example.com")
```

When the QR code is scanned, it will open or display the value stored inside it.

## Showing the QR Code

The generated QR code can be displayed using:

```python
img.show()
```

This opens the generated image so we can see the QR code.

## Saving the QR Code

The QR code can also be saved as an image:

```python
img.save("qrcode.png")
```

The file name and image extension are written inside `save()`.

## Complete Example

```python
import qrcode
from PIL import Image

img = qrcode.make("Hello World")

img.show()
img.save("qrcode.png")
```


