# Eloquent Ruby -- Digging in to Arrays and Strings

## Part 1: Taking Advantage of Ruby's Smart Collections

First, read chapter 3 (pages 29 through 42).

Next, use what you've learned to solve these short
challenges:

### 1. Using Variable Method Arguments

Write a method that takes _any number of arguments_,
and prints the value of the first and last arguments,
ignoring any middle ones.

For example, using this method from IRB or Pry
might look like:

```ruby
variable("first", "second", "third")
first
third
nil
```

```
name = ["Charles", "John", "Edward", "Kaminer"]
name.first
name.last
```

### 2. Using Map and Join

1. Create an array containing the strings "dog", "cat", "goat", and "capybara"
2. Transform this array into a new array where each string is
capitalized ("Dog", "Cat", "Goat", "Capybara")

```
task = %w{dog cat goat capybara}
task_upper = task.map(&:capitalize)
```

3. Combine this collection of capitalized strings into a single
string, with each element separated by a comma and a space
("Dog, Cat, Goat, Capybara")

```
task_one = task_upper.join(", ")
```

### 3. Dangers of `!` Methods

* Summarize in your own words the conventions around methods
whose names end in a `!`
  - Methods whose names end in a '!' are methods that change the actual collection as opposed to making and printing a modified copy of the collection.  A '!' signifies that if you were to recall the collection it would now appear with the modifications as opposed to the original version.
* Describe in your own words the advantages and disadvantages
of these methods. When would you want to use one and when
would you want to avoid using one.
  - An advantage of these methods is that the change being made is permanent so you do not need to create a new variable. A disadvantage is the opposite, you may want to call on the orginal collection later on in the code or want to create a modified version to compare to the original.  If you use a '!' method, you will not be able to do this.  You might want to use this method if you need a collection to be sorted before running through a program or if there are formatting fixes that need to be made.  You would want to avoid using this in a scenario where you may only need part of the collection for certain pieces of the code but will need the whole thing later.  Any time you will need to go back to the original you should avoid these methods and instead opt to create a new variable with the modifications.

## Part 2: Taking Advantage of Ruby's Smart Strings

First, read chapter 4 (pages 43 through 52).

Next, use what you've learned to solve these short
challenges:

### 1. Special Characters in Strings

* What does it mean to "escape" a character within a string?
* List 3 characters that have to be "escaped" when written
in a string.
* Use escape strings to generate a string containing your
name and, on a separate line, your height in inches and feet.

For example, mine, when printed, would look like:

```
Horace
5'9"
```

### 2. Splitting Strings

Take the string of your name and height you generated
in the previous section and split it into an array
containing your name (as the first element) and
height (as the second element).

For example my example from above would generate:

```
["Horace", "5'9\""]
```

Don't forget that `split` takes an _optional_ argument specifying
the character on which you'd like to split your string.

### 3. Poking at Bytes

We know that ultimately all data on our computers has to get
represented as numbers (numbers encoded as 1's and 0's, to
be precise). So how does text fit into this representation?

In short, the machine uses tables that map characters to
specific numeric values.

Use the `each_byte` method on a string to discover which numeric
byte values correlate to each character in your name.

For example, "Horace" translates to:

```ruby
[72, 111, 114, 97, 99, 101]
```
