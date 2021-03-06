# Working with Strings and Integers

Complete the following exercises to solidify your understandings of strings and integers.

## Just Strings

### 1. First & Last

If you have the strings `"First"` and `"Last"` in the following variables:

```ruby
f = "First"
l = "Last"
```

Use *only* the "string concatenation" technique to complete the following:

1. What code can you write to output the string `"FirstLast"`?

cat = f + l
strint = "#{f}#{l}"

2. What code can you write to output the string `"LastFirst"`?

cat = l + f
strint = "#{l}#{f}

3. What code can you write to output the string `"First Last"`?

cat = f + " " + l
strint = "#{f} #{l}"

4. What code can you write to output the string `"Last First Last First"`?

cat = l + " " + f + " " + l + " " + f
strint = "#{l} #{f} #{l} #{f}"


Then repeat 1-4 using only the "string interpolation" technique.

### 2. Names

Start with this string:

```ruby
name_1 = "Megan Smith"
name_2 = "Todd Park"
```

1. Can you come up with *two* ways to output just the fragment `"Megan"` from `name_1`?

name_1[0..4]
name_1.split[0]

2. Would either of your techniques from A would work to output `"Todd"` from `name_2`? Why or why not?

Technique one would not technically work because it would include the space after Todd (the 4th index), it would need to be name_2[0..3], but the second technique would.

3. Write code that can output the initials of `name_2`.

initials = name_2.split[0][0] + name_2.split[1][0]

## Just Integers

Start with these numbers:

```ruby
a = 12
b = 65
c = 31
d = 98
```

1. Write code to find the average of these four numbers.

array = [a, b, c, d]
avg = (a + b + c + d)/array.length

2. Find the average yourself using paper or a calculator. Is your answer different than you found in A? Why?

The average on the calculator was 51.5, but with code it's only 51. That's because the class of the variables is an integer

3. Say you have the operation `a + b * c / d`. What result do you get out from Ruby? What other outputs can you get out by adding one or more pairs of parentheses to the equation?

You get 32, because of order of operations. PEMDAS. So first it multiplies b * c (65 * 31 = 2015), then it divides that by d (2015 / 98 = 20.56...) and then you add that to a (12 + 20.56.. = 32.56..). Since we're working with fixnums, then the output is 32. 

You can add a parentheses as follows to get other values:

(a + b) * c / d = 24

a + b * (c / d) = 12

## Strings & Integers

### People

Say we have these people:

```ruby
a = "Ezra"
b = "Ada"
c = "Yukihiro"
d = "Grace"
```

Write code to output both the total characters in all the names together and the average length of the names.

total_char = a.length + b.length + c.length + d.length
puts "The total length of character of all four names is #{total_char} and the average length of these names is #{total_char/4} characters."

### Happy Birthday

In our family we like to say "Happy" once for every year of your age when we say "Happy birthday!". So when you turn
four we'd say "Happy happy happy happy birthday!" Note the capitalization.

Say you have an `age` variable that holds the person's age. Write code to output the appropriate greeting.

puts "Happy" + (" happy"*(age-1)) + " birthday!"


### String Compression

There's a silly compression algorithm that outputs the first letter, the number of letters in the middle,
and the last letter. So for the string `"Kalamazoo"` it'd output `"K7o"` or `"Denver"` would be `"D4r"`.
Can you write code to implement that?

middle = city[1...-1]
output = city[0] + middle.length.to_s + city[-1]

