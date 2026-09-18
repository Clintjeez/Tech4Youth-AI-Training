# Python syntax

How to write Python code properly

## What is syntax

Every programming language has its own rules - its syntax. It’s like grammar in human languages. You can’t just write words in any order and expect people to understand. The same goes for programming.
Python’s syntax is known for being clean and readable. But it still has rules you must follow, or your code won’t run.

## The importance of syntax

Think about these two sentences:

- “The cat sat on the mat” ✓ (correct English)
- "Cat the on mat sat the” ✗ (same words, wrong order)

Programming is the same:

```python
# Correct Python
    if age > 18:
    print("Adult")

# Wrong - Python won't understand
    age > 18 print("Adult")
```

## Python's unique feature: Indentation

Most languages use {} brackets. Python uses indentation (spaces):

```
# Python - clean and readable
if temperature > 30:
    print("It's hot!")
    print("Turn on AC")

# Other languages (like JavaScript)
if (temperature > 30) {
    console.log("It's hot!");
    console.log("Turn on AC");
}
```

Indentation rules

```python
# CORRECT - consistent 4 spaces
if score > 90:
    print("A grade")
    if score == 100:
        print("Perfect!")

# WRONG - mixing spaces
if score > 90:
  print("A grade")    # 2 spaces
    if score == 100:  # 4 spaces
      print("Perfect!")  # 6 spaces
```