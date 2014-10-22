# How to Write your Initial Solution

Now you actually get to code! Your entire goal here is to translate your pseudocode into code. This should be easy if you took your time to pseudocode well.

If your pseudocode is not easy to implement, modify it and re-attempt to code it. 

Run your code often to check whether you are successfully passing your tests. 

When you've passed each test, give yourself a pat on the back! Then take a break before trying to refactor. It's good to give your eyes a rest so they can more easily see places to improve.

####NOTE:
If you can't get your code to pass after spending too much time for comfort on it, take a break or move on. Simply write in the comments that you couldn't get it fully working. Try to identify where the problem was, and ask for help on the community. 

We do not recommend working 8 hours straight on one challenge (or even 3 hours). The point of these challenges is to challenge yourself and recognize when you need help or have hit a wall.


### Debugging
Some tips for finding where your code isn't working

- Include `puts` or `console.log` statements to find out what your code is doing - but remember, `puts` is a stupid method. It spits it out and immediately forgets what it did (i.e. `puts` does not return a value).
- Use string interpolation (for Ruby) in your puts statements - Make it clear what you want the code to be doing at that point.
- Check whether the methods are doing what you expect in IRB.

For example:

```ruby
def convert_letters_to_nums(my_word)
  alphabet = ("a".."z").to_a
  my_word = my_word.downcase.split(//)
  num_array = []

  my_word.each do |letter|
  puts "the current letter I'm looking for is #{letter}"
    alphabet.each_with_index do |ref_letter, index|
      if letter == ref_letter
        number_equivalent = index + 1
        puts "I've found a match for #{letter}!"
        num_array << number_equivalent
        puts "I'm pushing #{number_equivalent} to the array for #{letter}\n"
      end
    end
  end
  p num_array.join
end

convert_letters_to_nums("hoobastank")  
```
