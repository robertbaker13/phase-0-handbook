# Driver Test Code with Ruby

## What is Driver test code?

You may hear people at DBC talk about driver code, this is a term that pretty much exists inside the scope of dev bootcamp. Everyone else in the software development industry calls this 'testing'. The purpose of driver test code is two-fold. To make your program run and to test that it is working as you intend.

## Making things run.

Say you create a really swell ruby method that took you a long time to write.

```ruby
def algorithm_for_my_start_up
  puts "Hey! You should consider signing up for my product."
  puts "What is your name?"
  name = gets.chomp
  puts "What is your bank account number?"
  money = gets.chomp
end
```
Now if I go into the terminal and run my program

```shell
$ ruby start_up.rb
```
Nothing will happen! Why? We defined our method but have not __called__ our method yet. We need to add some code to make our code run.

```ruby
def algorithm_for_my_start_up
  puts "Hey! You should consider signing up for my product."
  puts "What is your name?"
  name = gets.chomp
  puts "What is your bank account number?"
  money = gets.chomp
end

algoritm_for_my_start_up # this is called calling the method
```

Now when we run the code in the terminal, it will execute the method. This makes our code go, what about methods that dont automatically print to the screen?

```ruby
def business_logic(number)
  sum = number + 5
end

business_logic(5)
```

This code will execute, but nothing gets put to the console. We need to dress up our method call to view what is going on.

```ruby
def business_logic(number)
  sum = number + 5
end

p business_logic(5)
```

We added the 'p' in front of the business_logic call. p returns the value of the method AND prints the value to the console. Puts will only print the value to the console and return nil, so we generally want to use 'p'.

Now when we run this code, we will see the number 10 on the terminal.


##Testing our expectations

Now that we know how to run the code and see what is being returned, we want to set up a set of expectations to see if our code is behaving like we expect it to. Testing is a core concept in programming and you will be doing plenty of it in your career.

Testing basically answers the question "What do I want my code to do?". There are tons of testing libraries to help you structure your tests, but for now we will focus on creating a set of simple expectations using the '==' comparator.

Take this code:

```ruby
def divide_number(dividend, divisor)
  quotient = dividend / divisor
end

divide_number(8920, 34)
```

This is math that most of us can not do in our head, can we trust the computer to do what we expect it to? Lets write some tests to see.

```ruby
def divide_number(dividend, divisor)
  quotient = dividend / divisor
end

p divide_number(8920, 34) == 262.35294

```
If you run this code, it will return false.