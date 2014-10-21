# How to Pseudocode

You should have tests already created (whether it's RSpec tests, JavaScript tests, or your own driver test code/assert statements)

The first thing you should do (before even starting to pseudocode) is to run the tests. Each test should fail. 

Then, in the pseudocode section of your `my_solution` file, identify what you are inputting to the class/method/code and what you need the code to output (what you expect to get).

From there, look at each test and write specific step-by-step ideas in code-like English to pass each of the tests. 

Each line should be something you can easily translate into code.

For example, if you are trying to convert every letter in a string to a number based on its location in the alphabet, you would probably want more info than this:

```ruby
# PSEUDOCODE
# Input = string with letters
# Output = string with numbers

# Convert all letters into their numbers
```

Instead, you would probably want something more like:

```ruby
#PSEUDOCODE
# Create array all letters
# Split input of letters into array
# Iterate through the input array 
# Check index of letter in all_letters array
# index = index + 1
# Push index to new array
# Convert finished array of numbers to string
```

You should feel free to supplement your pseudocoding with trying things out in IRB.

If you would like guidance or an some ideas on how to write pseudocode, take a look at this [pseudocode standard](http://users.csc.calpoly.edu/~jdalbey/SWE/pdl_std.html) example.

Pseudocode is for you. It may seem trivial and silly  for simple challenges, but it's an important and necessary step when you are working on more complex problems. You will want to get into practice of pseudocoding early so you are prepared for organizing your thoughts when it's required. 

