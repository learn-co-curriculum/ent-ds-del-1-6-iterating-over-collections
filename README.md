
# Iterating Over Collections


## Introduction
In the last lesson we introduced some of the common collection types within Python. Remember? 

**What are the characteristics of Lists, Tuples, Sets and Dictionaries? When would you choose to use each one?**

In this lesson, we're going to focus on iterating over collections so we can start to perform data clean up on collections of data. We'll also introduce nested collections where (for example), you have a List of Dictionaries for storing and operating on a collection of complex data.

## Objectives
You will be able to:
* Iterate over common Python collection types
* Use list comprehensions to clean up lists
* Create and iterate over collections of collections

## Iterating Over a Sequence

In Python, a Sequence is an ordered set. As such, both Lists *(mutable - you can change them)* and Tuples *(immutable, you can't change them)* are sets. 

Let's look at how to iterate over a sequence:


```python
state_list = ["Alabama", "California", "Montana"]
for state in state_list:
    print(state)

```

    Alabama
    California
    Montana


## Iterating Over a Set

A Set isn't an **ordered** sequence *(remember? in a set duplicates are not allowed and you can't control the order of the elements)*, but the code to iterate over it is the same as for a List or a Tuple:


```python
unique_cities = {"Chicago", "Madison", "Minneapolis"}
for city in unique_cities:
    print(city)
```

    Minneapolis
    Chicago
    Madison


## Transforming a List

Let's iterate over a list and clean up the results, storing them in a new list.

original_company_list 

## List Comprehensions

Often you want to take the elements 


## Turning a List into a Set



## Summary


