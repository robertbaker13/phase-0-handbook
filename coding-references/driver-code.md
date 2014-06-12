# Driver Test Code with Ruby

As a student at DBC, you will probably encounter a few different ways of writing Driver code.

###1) Driver Code
Driver code simply calls a method or creates an object. It takes your code and actually makes it run. 
```ruby
separate_comma(1000)

nike = shoe.new("air jordan")

```

###2) Driver Code with Comments
Driver code that has an expected result commented out. You will have to do a mental check to see whether the output is what you expected.
```ruby
separate_comma(1000)    # => "1,000"
```

###3) Driver Test Code 
Driver test code uses the equality operator (==) to check whether the method call is equal to what you expected. If the code worked properly, it will return `true`. If it is not functioning as you expected, it will return false.
```ruby 
puts separate_comma(1000) == "1,000"
```

###What format of test code is best?

You are a human and you are smart! Much smarter than a computer. But it takes a lot of brain power to remember exactly what you want something to look like. Let's take a Roman Numeral converter, for instance. It would get really easy to get a bit boggled down in the details or miss an error. 

```ruby

num_to_roman(25) == "XXV"
num_to_roman(1999) == "MCMXCIX"

```

So simply calling the method isn't the best option because you have to remember, and manually check, whether your expected output is what you got. 
That's a lot of work for you, and it's conveniently what computers are good at! 

Moreover, since other programmers are lazy and don't care what the output should be, you should make it as simple as possible to know whether something is working properly. To do this, you'll want to write Driver Test Code (#3) that returns a simple `true` if it's working, `false ` otherwise. 

When you are debugging it may be useful to use the second option because seeing the actual output of the tests is much more helpful than seeing a `true` or `false`. However, after your code is working correctly and passing your tests, you shouldn't leave the expectation in a comment. Imagine if you were another programmer and you ran this test code. You'd see (in this case) a long list of numbers, and it would be unclear whether the code was actually working correctly.

```shell
> ruby separate_commas.rb
7
883
1,233
89,434
100,334,555
1,893,320,493,894,578
```

Option 3 helps dramatically.  When running this format of test code, all the tests return `true` or `false`.  Another programmer immediately knows if the program is correctly working.  And a quick look at the test code makes the input and output clear.

```shell
> ruby separate_commas.rb
true
true
true
true
true
true
```

It's important to test as many cases as possible where your code could mess up, we call these "edge cases" to make sure any little exception is covered. Otherwise you could end up not testing all the cases you thought. 

```ruby
nums_to_words(1) == "one"
nums_to_words(10) == "ten"
nums_to_words(100) == "one hundred"
nums_to_words(150) == "one hundred fifty"
nums_to_words(199) == "one hundred ninety nine"
nums_to_words(213) == "two hundred thirteen" #=> This could easily return something like "two hundred ten three".

``

###An optimal test code format
So this isn't a perfect form of tests, and there are testing frameworks that help. You'll encounter testing frameworks in various weeks in phase 0. For now, using driver test code is a good start, but you can also challenge yourself to write tests that provide more clarity. 

You can write Driver test code to help immediately  answer questions like:
* "What is the actual test that is passing or failing?"  
* "What is the context of the test?"
* "What did the code return if it failed?"
* "If there was an error when the code ran, what was it?"

In a future challenge, try writing some test code that answers some of these questions!  While it's not mandatory for your solutions, (only Option 3 is at this point), investigating how to create a good testing suite is a very worthwhile endeavor.

Later, when we dealve into [Rspec](http://en.wikipedia.org/wiki/RSpec), you'll understand just how much work went into making the industry standard testing suite for ruby and rails.