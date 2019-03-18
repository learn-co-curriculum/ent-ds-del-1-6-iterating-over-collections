
# Iterating Over Collections


## Introduction
In the last lesson we introduced some of the common collection types within Python. Remember? 

***What are the characteristics of Lists, Tuples, Sets and Dictionaries?***

**When would you choose to use each one?**

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

## Iterating Over a Set

A Set isn't an **ordered** sequence *(remember? in a set duplicates are not allowed and you can't control the order of the elements)*, but the code to iterate over it is the same as for a List or a Tuple:


```python
unique_cities = {"Chicago", "Madison", "Minneapolis"}
for city in unique_cities:
    print(city)
```

## Transforming a List

Let's iterate over a list and clean up the results, storing them in a new list. Lets take the capitalization example we used before just to make this easy . . .


```python
original_company_list = ["aMAzOn", "FAcebooK", "GooGLe"]
new_company_list = []
for company in original_company_list:
    new_company_list.append(company.capitalize())
print(new_company_list)                  
```

## List Comprehensions

The code above works, but there is a more idiomatic way to write that code in Python, using something called "list comprehensions". It allows you to easily iterate over a list and create a new list based on the transformation you describe. 


```python
original_company_list = ["aMAzOn", "FAcebooK", "GooGLe"]
new_company_list = [company.capitalize() for company in original_company_list]
print(new_company_list)
```

You can even apply a filter to a list comprehension, so, for example, if you only want companies where the first letter of theirt name starts with an "a", you could write:


```python
original_company_list = ["aMAzOn", "FAcebooK", "GooGLe"]
new_company_list = [company.capitalize() for company in original_company_list if company[:1] == "a"]
print(new_company_list)
```

You don't necessarily need to write your code using list comprehensions, but it's important to be familiar with the format so you don't get confused when they come up when you Google for answers!

## Turning a List into a Set

Lets say you have a list of companies and each one is incorporated in a different state. It might be nice to create a de-duplicated list of states so you just have a list of all of the states that one or more of the companies is incorporated in.
```
company_incorporation_states = ["Alabama", "California", "New York", "California", "Delaware", "New York", "Delaware", "Delaware"] 
```

There are lots of ways to do this, but one of the simplest is:


```python
company_incorporation_states = ["Alabama", "California", "New York", "California", "Delaware", "New York", "Delaware", "Delaware"]
unique_states = set(company_incorporation_states)
print(unique_states)
```

## Iterating over a List of Dictionaries

While you will occasionally have a List you want to clean up, it's way more common for you to have a List of Dictionaries. For example, the problem above probably looks a little more like this most of the time:


```python
company_1 = {
    "company_name": "Acme",
    "state_incorporated": "Alabama"    
}
company_2 = {
    "company_name": "Deville",
    "state_incorporated": "California"    
}
company_3 = {
    "company_name": "Goldwater",
    "state_incorporated": "New York"    
}
company_list = [company_1, company_2, company_3]

print(company_list)
```

And the code for working with this is pretty straightforward. Let's say we want to get a list of company names:


```python
company_name_list = []
for company in company_list:
    company_name_list.append(company["company_name"])
print(company_name_list)     
```

Or using a list comprehension:


```python
company_name_list = [company["company_name"] for company in company_list]
print(company_name_list)
```

## Summary

There are lots of ways of iterating over and operating on collections in Python, but now you should have enough of the building blocks required to start to perform data clean up operations on collections of data.

