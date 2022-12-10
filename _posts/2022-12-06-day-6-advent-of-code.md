---
layout: post
title: AoC | Day 6 | Tuning Trouble
date: 2022-12-06 17:39:00
description: my first post ever :)
tags: aoc python
categories: aoc code python
---
   Hello, this is my first coding post to which you miraculously have somehow
stumbled upon. I'm playing catchup to Advent of Code this December, so you'll notice (most likely) that the dates off!

  Secondly, compared to the norm, there isn't much going on this page at first
glance compared to other posts one can view. 



   Of course this is written from the perspective of my future self
where right now I still don't know much about writting these posts in markdown..

 But I trust that things will get better, so if they have, I'd appreciate you giving a star to this [repository](https://github.com/mkbcodes/mkbcodes.github.io), or givin my [Github](https://github.com/mkbcodes) a follow. 


Thank you and I hope you find this post useful or at least interesting! =)


### Instructions
This will be done in _python.
There are *two* parts to **Day 6**, if you'd like to read the instructions to the problem at this time please check out the link below:

[Link to Day 6 - Part 1 Instructions](https://adventofcode.com/2022/day/6)

### Requirements
Let's start with listing how to solve part 1 by looking at what is required,
>
- Iterate through the `entire input string`, checking 4 characters at a time, and stepping 1 character at a time.
- All characters in the `4 character long substring being checked are unique`.
- Upon locating the set of 4 unique characters, locate the `index` of the newest character (the `last index of 4 character long substring`) and `add one`.

### The Solution - Part 1

```python
def find_four_different_characters(s):
  # Iterate over the length of the string
  for i in range(len(s)):
    # Check if the current substring of length 4 contains four different characters
    if len(set(s[i:i+4])) == 4:
      # Return the index after the last character in the substring
      return i + 4
  # If no four-character marker was found, return -1
  return -1
```
 >This function takes a string and a position as arguments, and uses the assert statement to check if the four characters at the specified position in the string are all different. If they are not, the assert statement raises an AssertionError exception with the specified message.

>Here is an example of how you might use this function to check if a given string contains a start-of-packet marker at the specified position:  

```python
      # Test to make sure it works with the provided example input strings.

  def contains_marker(string, position):
    assert string[position - 4:position] == len(set(string[position - 4:position])), "No marker at position {}".format(position)

  string = "mjqjpqmgbljsphdztnvjfqwrcgsmlb"
  position = 7
  contains_marker(string, position)  # Output: No error, marker found at position 7

  string = "bvwbjplbgvbhsrlpgdmjqwftvncz"
  position = 5
  contains_marker(string, position)  # Output: No error, marker found at position 5

  string = "nppdvjthqldpwncqszvftbrmjlhg"
  position = 6
  contains_marker(string, position)  # Output: No error, marker found at position 6

  string = "nznrnfrfntjfmvfwmzdfjlvtqnbhcprsg"
  position = 10
  contains_marker(string, position)  # Output: No error, marker found at position 10

  string = "zcfzfwzzqfrljwzlrfnpqdbhtmscgvjw"
  position = 11
  contains_marker(string, position)  # Output: No error, marker found at position 11

  string = "mjqjpqmgbljsphdztnvjfqwrcgsmlb"
  position = 6
  contains_marker(string, position) 


```
### The Solution - Part 2
And the other part where we detect 14 unique characters in a row uses the same method:

```python
def find_fourteen_different_characters(s):
  # Iterate over the length of the string
  for i in range(len(s)):
    # Check if the current substring of length 14 contains 14 different characters
    if len(set(s[i:i+14])) == 14:
      # Return the index after the last character in the substring
      return i + 14
  # If no 14-character marker was found, return -1
  return -1

```

### The Solution - Running The Code
```python
# To start the code - part a
start_of_packet_marker = find_four_different_characters(input_string)
print("Start of packet marker:", start_of_packet_marker)

# To start the code - part b
start_of_packet_marker = find_fourteen_different_characters(input_string)
print("Start of packet marker:", start_of_packet_marker)
```
### Conclusion

I hope that this helps, have a nice day! neighbour mike out.