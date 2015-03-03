# Driver Test Code with Ruby

## What is Driver Code?

You may hear people at DBC talk about driver code. This is a term that pretty much exists inside the scope of Dev Bootcamp. Everyone else in the software development industry calls this 'testing'. The purpose of driver code is two-fold: to make your program run and to test that it is working as you intended.

## Driver code makes things run.

Say you create a really cool ruby method that took you a long time to write.

Let's say that I have a file called start_up.rb
```ruby

def algorithm_for_my_start_up
  puts "Hey! You should consider signing up for my product."
  puts "What is your name?"
  name = gets.chomp
  puts "What is your bank account number?"
  money = gets.chomp
end
```
Now I go in to the terminal and run my program.

```shell
$ ruby start_up.rb
```
Nothing happened! Why? We defined our method but have not __called__ our method yet. We need to add some code to make our code run.

```ruby
def algorithm_for_my_start_up
  puts "Hey! You should consider signing up for my product."
  puts "What is your name?"
  name = gets.chomp
  puts "What is your bank account number?"
  money = gets.chomp
end

algoritm_for_my_start_up
```

Now when you run the code in the terminal, it will execute the method. This makes our code run, but what about methods that don't automatically print to the screen?

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

You have the option to use `p` or `puts` or `print` here. Here is a handy chart to see the difference:

| Name of method | Does it return the value of the method or variable | Does it print to the console | Does it automatically add a newline at the end of the return value |
|---------------|-------------------------------------------------------|-----------------------------|------------------------------------------------------------------------------|
| `puts`   |  No, returns nil |  Yes  | Yes |
| `p`      | Yes | Yes | Yes |
| `print` | No, returns nil | Yes | No |

If you are looking to return a value and print it to the console, `p` is your choice. If you just want to print to the console then you can use `puts`. `print` is more of a specialized method.

Now when you run this code, you will see the number 10 on the terminal.

## Driver Test Code

Now that you know how to run the code and see what is being returned, you want to set up a set of expectations to see if our code is behaving like you expect it to. Testing is a core concept in programming and you will be doing plenty of it in your career. In Phase 0, you will use your own Ruby knowledge to "test," which basically means using `==` to see if what you got was what you expected. Testing answers the question "What do I want my code to do?" There are tons of testing libraries to help you structure your tests, but for now you will focus on creating a set of simple expectations using what you know in Ruby. 

(The most popular testing framework for Ruby is called RSpec, and the most popular testing framework for JavaScript is called Jasmine, you will see RSpec in Phase 0, but we aren't asking you to learn RSpec)

Take this code:

```ruby
def divide_number(dividend, divisor)
  quotient = dividend / divisor
end

divide_number(8920, 34) # This is driver code. It simply calls the method.
```

This is math that most of us can not do in our head. Can you trust the computer to do what you expect it to? Let's write some tests to see.

```ruby
def divide_number(dividend, divisor)
  quotient = dividend / divisor
end

p divide_number(1000, 25) == 40 # returns true

p divide_number(8920, 34) == 262.35294 # returns false

```

If you run this code, it will return one true and one false. This tells us that our expected output (262.35294) for the second test is not what is ACTUALLY being output. You can see what is  output by removing or commenting out the '== 262.35294'. From there you can change how our method works to reach the desired output.

Generally, you want to write tests for all of the outputs of your methods. You can also try and find inputs that will break your code. These inputs are called edge cases. For example, an edge case for the divide_number method could be divide_number(10, 0). This would result in an error and crash your program because you cannot divide by 0.

## RSpec

Some of the challenges you will complete have a panel of RSpec tests you will execute to test your expectations for you. You can use the RSpec on its own, and you can write your own test code (like you did above, not in RSpec) to help you reach the correct output.

RSpec is daunting to beginners, so I will break down a simple RSpec example to give you an idea of what is going on. You do not have to have ANY knowledge about how to write RSpec tests during Phase 0.

```ruby
# this is called a describe block. It allows us to encapsulate different responsibilities of tests.
# You can assume that everything between this do..end will have to do with the variable old_string.

describe "old_string" do

  it "has the value 'Ruby is cool'" do         # it block. This is the start of the test. you can write a string to
                                               # describe what this test is going to be testing. In this case you want
                                               # old_string to have the value of 'Ruby is cool'.

    expect(old_string).to eq "Ruby is cool"    # this is the expectation. Code gets executed inside the expect method
                                               # and the output is compared to the string "Ruby is cool". There are many
                                               # ways you can compare like .to eq, .to be, .to not_be etc.

  end                                          # end of the it block

end                                            # end of the describe block
```

Again, don't waste your time learning RSpec now. The only thing you have to know is that you need to run RSpec files with `$ rspec file_name.rb` You will spend plenty of time learning and writing RSpec tests on site.
