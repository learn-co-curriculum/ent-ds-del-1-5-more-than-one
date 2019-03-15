
# More than One - Python Collection Types


## Introduction
So far we've focused on cleaning up one piece of data at a time. In practice, that isn't much use. You could probably clean up one piece of data manually as quickly as your code could. What we want is a way to store a **collection** continaining many pieces of data so we can loop over it and clean up all of the pieces of information efficiently. Then we can start to load up csv files or even write web scrapers to retrieve collections of data and automatically clean them up with our code.

In this lesson we'll look at some of the more common types of collections (variables for storing multiple pieces of data) available in Python so we can pick the right kind for a given type of data and write code that will loop over and then 

## Objectives
You will be able to:
* Explain what a collection is and why it's useful
* Explain the difference between mutable and immutable collections
* Explain the differences between common collection types in Python
* Pick the appropriate collection type(s) for a given type of data

## An Introduction to Immutability
Before we start we should mention the concept of "immutability". In a programming language, a variable that is immutable can't be changed. You can set the value - but you can't ever change the value once it's been set. 

In terms of both performance and utility, there are subtle benefits in picking immutable vs mutable variables for certain problems (in some programming languages they are called "constants" and "variables" to distinguish the fact that a mutable "variable" can't actually vary, so it's really a constant). In practice, you probably won't need to care very often about whether you use mutable or immutable variables, but you will need to know which is which, so you don't get surprised by the way they work.

## Keeping Order
Another concept you'll need to understand to make sense of collections is the difference between ordered and unordered collections. In an ordered collection you get to decide the order of the elements (hmm, lets put Minneapolis after Chicago in the list of cities). In an ordered collection you can also do things like add an element to the start or the end of the collection or even reference the nth item (lets get the first five cities in the collection - or the last three).

In an unordered collection you can simply add or remove elements but you can't control the order in which they are stored in the collection.


## Key Collection Types
Four of the most common collection types in Python are Lists, Tuples, Sets and Dictionaries.
* A **List** is an *ordered*, *mutable* collection. So it's a collection of items that you control the order of and that you can add, remove and/or update items within it. It's written in Python using square brackets:
```
    city_list = ["Chicago", "Madison", "Minneapolis"]
```
* A **Tuple** is an *immutable* list. It's ordered, but you can't change it - so you can't add, edit or delete elements within a tuple. It's written in Python using round brackets:
```
    unchangeable_city_list = ("Chicago", "Madison", "Minneapolis")
```
* A **Set** is an *unordered* collection. It is *mutable* because you can add or remove items from it after creating it. Also, with a Set, you can't have duplicate items (no two of the elements can be identical). It's written in Python using curly braces:

```
    unique_city_list = {"Chicago", "Madison", "Minneapolis"}
```
* A **Dictionary** in a collection of key:value pairs that are *mutable* and *unordered*. They are a very common data type for structured information. It's written in Python using curly braces:
```
    person = {
        "first_name": "Jim",
        "last_name": "Collins",
        "email": "jim@gmail.com",
        "dob": "1965/02/22"
       }
```

## Picking a Collection Type
Here are some heuristics for getting started:
* If you want a unique collection (e.g. all of the cities you are investigating people in), a **Set** is probably a good fit as you don't have to worry about duplicate entries and it's usually pretty quick to do lookups against it.
* If you have a single collection of data points (list of cities, list of states, list of company names, list of business codes, etc) and you might want to support duplicates, a **List** is probably a good collection for you to use.
* If you have a list of data points that you know will never change such as a list of US states (sure, we might end up annexing Canada, but in general the list of US states is unlikely to change on a regular basis), you could use a **Tuple**. It's not really that different from a list, but it makes it very clear to others reading your code that you do not expect to make any changes to that list of items.
* Finally, if you have more complex data (think a spreadsheet, not a list), you're probably going to want to use a **Dictionary** to store that (at least until next week when we introduce you to the Pandas library and their wonderful DataFrames!)

## Summary

We've introduced a number of common collection types in Python and why you might pick one over another. In the next lesson, we'll look at how to iterate over a collection (to loop through all of the items) so we can start to perform data clean up on collections of data - not just individual items.

