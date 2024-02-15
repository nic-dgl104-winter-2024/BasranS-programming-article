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
Bugs in code behave just like those in real life: they live in the darkest, dirtiest places in the code. Clean your code and the errors will practically discover themselves. Managers appreciate proactive refactoring as it eliminates the need for special refactoring tasks later. Happy bosses make happy programmers!

### During a code review
The code review may be the last chance to tidy up the code before it becomes available to the public. It’s best to perform such reviews in a pair with an author. This way you could fix simple problems quickly and gauge the time for fixing the more difficult ones. ("Refactoring,"https://refactoring.guru/refactoring/when/)

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

![red1](https://github.com/nic-dgl104-winter-2024/BasranS-programming-article/assets/144393592/2a99f494-7576-4e79-b6c0-072e46c8771b)
### Refactoring by Abstraction
Branching by abstraction is a method used primarily when there is a large amount of refactoring to be done. Abstraction involves class inheritances, hierarchy, and extraction. The goal of abstraction is to reduce unnecessary duplications in software code. One example of abstraction is the Pull-Up/Push-Down method. These are two opposite forms of refactoring involving classes. The Pull-Up method pulls code 
parts into a superclass in order to eliminate code duplication. Push-Down takes it from a superclass and moves it down into subclasses.

![abs1](https://github.com/nic-dgl104-winter-2024/BasranS-programming-article/assets/144393592/440fd978-8910-4236-8c71-2fbc45e1dc05)
## Composing Method
Composing involves streamlining the code in order to reduce duplications. This is done through various processes, including extraction and inline methods.
* Extraction involves breaking down the code into smaller chunks in order to find and “extract” fragmentation. The fragmented code is then moved to a separate method and replaced with a call to this new method. In addition to the method, extraction can involve class, interface, and local variables as well.
* Inline refactoring is a way to reduce the number of unnecessary methods while simplifying the code. By finding all calls to the method and replacing them with the content of the method, the method can then be deleted.
## Simplifying Methods
The older code gets, the more garbled and complicated it tends to be. Consequently, it makes sense to go in and simplify a lot of the logic. This can be done in a variety of ways, including consolidation of conditional fragments and expressions and replacing conditional with polymorphism. Simplifying method calls involves tweaking the interaction between classes. Adding, removing, and introducing new parameters along with replacing parameters with explicit methods and method calls are all aspects of simplification. ("Code Refactoring Best Practices: When (and When Not) to Do It,"https://www.altexsoft.com/blog/code-refactoring-best-practices-when-and-when-not-to-do-it/)

## Code Snippets(Java)
### Red and Green Method (Before Refactoring)

public class OrderProcessor {
    
    public void processOrder(Order order) {
        // Processing logic
        
        // Logging
        Logger logger = new Logger();
        logger.log("Order processed: " + order.getId());
    }
}

### After Refactoring 

public class OrderProcessor {

    public void processOrder(Order order) {
        // Processing logic
        
        // Logging
        OrderLogger orderLogger = new OrderLogger();
        orderLogger.logOrderProcessed(order);
    }
}

public class OrderLogger {

    public void logOrderProcessed(Order order) {
        Logger logger = new Logger();
        logger.log("Order processed: " + order.getId());
    }
}

### Extraction Mtehod (Before Extraction)

public class OrderProcessor {
   
    private List<Item> items;
    private double taxRate;

    public double processOrder() {
        double subtotal = 0;
        for (Item item : items) {
            subtotal += item.getPrice();
        }
        
        double totalTax = subtotal * taxRate;
        double totalCost = subtotal + totalTax;
        
        return totalCost;
    }
}

### After Extraction

public class OrderProcessor {
   
    private List<Item> items;
    private double taxRate;

    public double processOrder() {
        double subtotal = calculateSubtotal();
        double totalTax = calculateTax(subtotal);
        return calculateTotalCost(subtotal, totalTax);
    }
    
    private double calculateSubtotal() {
        double subtotal = 0;
        for (Item item : items) {
            subtotal += item.getPrice();
        }
        return subtotal;
    }
    
    private double calculateTax(double subtotal) {
        return subtotal * taxRate;
    }
    
    private double calculateTotalCost(double subtotal, double totalTax) {
        return subtotal + totalTax;
    }
}

###Simplifying Method (Before Simplification)

public class ShoppingCart {
    
    private List<Item> items;

    public double calculateTotalCost() {
        double total = 0;
        for (Item item : items) {
            if (item.isDiscounted()) {
                total += item.getPrice() * 0.8;
            } else {
                total += item.getPrice();
            }
        }
        if (total > 100) {
            total -= 10;
        }
        return total;
    }
}

### After Simplification

public class ShoppingCart {
    
    private List<Item> items;

    public double calculateTotalCost() {
        double total = 0;
        for (Item item : items) {
            total += calculateItemPrice(item);
        }
        total -= applyDiscount(total);
        return total;
    }

    private double calculateItemPrice(Item item) {
        return item.isDiscounted() ? item.getPrice() * 0.8 : item.getPrice();
    }

    private double applyDiscount(double total) {
        return total > 100 ? 10 : 0;
    }
}

(https://medium.com/javarevisited/code-refactoring-in-java-tips-best-practices-techniques-c240fb334925)


### Bibliography

