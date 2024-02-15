# BasranS-programming-article

# Refactoring Practices

## Introduction

Refactoring code involves systematically improving a software's internal structure, readability, and maintainability, all without any impact on its external structure. The primary goal is to improve the code quality and enhance its efficiency by rearranging or simplifying the codebase. This process results in a more comprehensible code which is more understandable for developers. Refactoring is most effective when approached as a sequence of incremental adjustments, with each modification enhancing the existing code.

Its heart is a series of small behavior-preserving transformations. Each transformation (called a "refactoring") does little, but a sequence of these transformations can produce a significant restructuring. 
(Martin Fowler, 1997-1999). Refactoring.com. https://refactoring.com/

## Best Time to Refactor

### Rule of Three
* When you’re doing something for the first time, just get it done.

* When you’re doing something similar for the second time, cringe at having to repeat but do the same thing anyway.

* When you’re doing something for the third time, start refactoring.


### When adding a feature
Refactoring helps you understand other people’s code. If you have to deal with someone else’s dirty code, try to refactor it first. Clean code is much easier to grasp. You will improve it not only for yourself but also for those who use it after you.
Refactoring makes it easier to add new features. It’s much easier to make changes in clean code.


### When fixing a bug
Bugs in code behave just like those in real life: they live in the darkest, dirtiest places in the code. Clean your code and the errors will practically discover themselves.
Managers appreciate proactive refactoring as it eliminates the need for special refactoring tasks later. Happy bosses make happy programmers!


### During a code review
The code review may be the last chance to tidy up the code before it becomes available to the public.

It’s best to perform such reviews in a pair with an author. This way you could fix simple problems quickly and gauge the time for fixing the more difficult ones. (https://refactoring.guru/refactoring/when)

## Why should you refactor the code?

Code refactoring is essential to keep code clean, readable, and maintainable over time. As developers work on a codebase, natural changes can introduce inefficiencies, redundancies, and complexity if not appropriately addressed.

Some common reasons code becomes messy and requires refactoring include:

* Improved code quality
* Increased maintainability
* Better performance
* Lower risk of bugs
* Higher developer productivity

## Refactoring Best Practices 

These proven strategies help ensure refactoring success and mitigate any potential risks involved in the process.

1. Refactor first before adding any new features
This practice ensures the codebase is in the best possible state to accommodate new additions. Instagram’s development team followed this approach before introducing their IGTV feature, helping to prevent feature creep and maintain a clean, manageable codebase.

2. Planning your refactoring project and timeline carefully
This involves deciding what to refactor, when, and how to mitigate associated risks. Twitter, for example, carefully planned its shift from Ruby on Rails to a JVM-based stack over several years, allowing for a smooth transition without significant user-facing issues.

3. Testing often throughout the refactoring process
Testing is a crucial part of refactoring. Netflix has automated tests that run continuously throughout their refactoring process, enabling them to catch and address any regressions or issues immediately.

4. Involving your QA team in the process
The QA team plays a vital role in ensuring the refactored code meets the quality standards. Companies like Shopify involve their QA teams early to ensure thorough testing and high-quality code.

5. Focusing on progress, not perfection
Remember, refactoring is about improving the codebase incrementally, not perfecting it. Microsoft follows this principle, regularly making minor improvements to its vast codebase.

6. Trying refactoring automation
There are tools available that can automate parts of the refactoring process. Google, for instance, developed an internal tool called Rosie, which has automated millions of refactorings, improving developer productivity and code quality.

## Best Practices (Bonus tips)

1. Take incremental steps
Rather than attempting to refactor a large portion of your codebase simultaneously, taking small, incremental steps is often best. This approach makes the process more manageable and reduces the risk of introducing bugs. Amazon applies this principle by frequently deploying small but substantive changes to its codebase, leading to continuous improvement and allowing them to maintain one of the world’s most complex e-commerce platforms.

2. Keep your Code DRY (Don’t Repeat Yourself)
Duplication is the root of all evil in programming. DRY is a principle of software development aimed at reducing repetition. Applying DRY principles means that developers should aim to reduce the repetition of information of all kinds. Twitter’s development team follows this principle, which has helped to keep its codebase clean and maintainable despite its large size.

3. Use refactoring tools
Many integrated development environments (IDEs) include tools that automate refactoring tasks. This can speed up the refactoring process and help ensure you don’t introduce bugs in your code. Airbnb, for example, uses the RuboCop tool for their Ruby codebase to enforce style conventions and find common errors before they become problems.
("Code Refactoring: 6 Best Practices to Follow for Developers,"https://www.rapidops.com/blog/code-refactoring-best-practices/)

## Code refactoring techniques
There are many different approaches and techniques for code refactoring. Some of the most popular include:

### Red-Green-Refactor
One of the most widely used techniques for code refactoring is the red/green process used in Agile test-driven development. Applying the
Red-Green-Refactor method, developers break  refactoring down into three distinct steps:

* Stop and consider what needs to be developed. [RED]
* Get the development to pass basic testing. [GREEN]
* Implement improvements. [REFACTOR]
code refactoring - red green refactor


![red](https://github.com/nic-dgl104-winter-2024/BasranS-programming-article/assets/144393592/317a255f-992e-40ba-ab57-1b23b4460983)


### Refactoring by Abstraction
Branching by abstraction is a method used primarily when there is a large amount of refactoring to be done. Abstraction involves class inheritances, hierarchy, and extraction. The goal of abstraction is to reduce unnecessary duplications in software code.

One example of abstraction is the Pull-Up/Push-Down method. These are two opposite forms of refactoring involving classes. The Pull-Up method pulls code parts into a superclass in order to eliminate code duplication. Push-Down takes it from a superclass and moves it down into subclasses.

![abs](https://github.com/nic-dgl104-winter-2024/BasranS-programming-article/assets/144393592/8c162520-7a46-47b9-bd1c-e699b8e28735)

### Composing Method
Composing involves streamlining the code in order to reduce duplications. This is done through various processes, including extraction and inline methods.

* Extraction involves breaking down the code into smaller chunks in order to find and “extract” fragmentation. The fragmented code is then moved to a separate method and replaced with a call to this new method. In addition to the method, extraction can involve class, interface, and local variables as well.

* Inline refactoring is a way to reduce the number of unnecessary methods while simplifying the code. By finding all calls to the method and replacing them with the content of the method, the method can then be deleted.

### Simplifying Methods
The older code gets, the more garbled and complicated it tends to be. Consequently, it makes sense to go in and simplify a lot of the logic. This can be done in a variety of ways, including consolidation of conditional fragments and expressions and replacing conditional with polymorphism. Simplifying method calls involves tweaking the interaction between classes. Adding, removing, and introducing new parameters along with replacing parameters with explicit methods and method calls are all aspects of simplification.
Moving Features Between Objects. (https://www.altexsoft.com/blog/code-refactoring-best-practices-when-and-when-not-to-do-it/)

### 

### References

