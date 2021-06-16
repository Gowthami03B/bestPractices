# Python Coding Practices
## Start with your functions

When learning how to level up your code, start with how you write functions. Most code is just a series of functions (or potentially classes) and if you can learn to write pretty good functions, that will go a long way to improving your code quality.
### Your functions at a minimum should:
- Do only one thing
- Have documentation
- Use good variable names
- While there are entire books written on how to write clean functions, these 3 items are a great place to start.

You should never have a function that feels like it is trying to do more than a single thing. Some signs that your function might be doing too much:

- It is longer than a single screen length or roughly 30 lines of code (in my experience).
- It is hard to name your function clearly because of how many things it does
- It contains a lot of code within if/else blocks that should actually be broken into separate functions
- Functions that only do one thing are important because it makes your code easier to understand, manage, and test (more on testing later).

> Any function being released to production should have a document string and that string should describe what the function does, give information on the input parameters, and potentially provide some simple examples of how to use the function. You will thank yourself in the future when you have well-documented functions and others will have a significantly easier time understanding your code. 

- Remove Print Statements and using Logging instead
- Logging should be how you communicate information and errors from your code. A good Python library to take a look at to make logging even simpler is Loguru. It automatically takes care of most of the annoying parts about logging and it feels much more like just using print statements.

### Use a Style Guide
 - Style guides in programming are used to make it easier for many people to work on the same code, but for that code to mostly look as if it were coded by a single person.

    ##### Why does this matter?

    - When you have a consistent style it makes it much easier to navigate and understand the code. Conforming to a standard way of writing code will make it easier for you to navigate that code as well as others. 

    - PEP 8 is probably the most widely used style guide for Python. Another popular source of style guides is Google as they have made public their internal style guides.

    - What matters is you pick one and try to stick to it. One way to make that easier is to enable your IDE to check for style errors and set up style checks that stop code from being pushed if the style guide isn't followed. 
    
    - You could also commit even further by using an auto-formatter that will automatically format your code for you. These allow you to write code however you want and then when run will auto-format your code to conform to the standard. A popular one for Python is Black.

### Write Unit Tests

- To get started using Python, I would go with pytest. Using pytest you can easily create tests and run them all at once to make sure they pass. 
- A simple way to get started is to have a directory called “tests” and within that directory have Python files that start with “test.” For example, you could have “test_addition.py”

```sh
# content of test_addition.py
def add(x, y):
    return x + y
def test_add():
    assert add(3, 2) == 5
```
- Typically, you would have your actual function in another Python file and would import it to your test module. You also would never need to test Python addition, but this is just a very simple example.

Within these test modules, you can save all the “sanity checks” of your functions. It is generally good practice to not only test common cases, but also edge cases and potential error cases.

### Do Code Reviews
 - The person who reviews your code should preferably be at least as good as you at writing code, but even having someone more junior review your code can still be incredibly beneficial.

- Having a more experienced colleague review your code and give you tips for ways to improve is priceless.

To make it easier for those reviewing your code, try to keep the amount of new code small. Small, frequent code reviews work well. Infrequent, huge code reviews are terrible. No one wants to be sent 1,000s of lines of code to have to review. These reviews tend to provide worse feedback because the person can’t take the time necessary to really understand that much code at once.

Original article - https://towardsdatascience.com/data-scientists-you-need-to-know-how-to-code-9142b2dc74e8
