
##  Keep It Simple, Stupid (KISS)
clear variable names
-   Increase readability, understand-ability and changeability
-   Less error prone
-   Easier to maintain
##  DRY
## Open/Closed
## Composition Over Inheritance
## Single Responsibility
A class should have only one reason to change.
## Separation of Concerns
MVC
The separation of concerns concept is an abstract version of the single responsibility principle.
## You Aren't Going to Need It (YAGNI)
shouldn't try to solve a problem that doesn't exist.
## Document Your Code

## Avoid Premature Optimization

## Boy-Scout Rule
Leave the campground cleaner than you found it

## Low coupling

## Law of Demeter
The _Law of Demeter (LoD)_ or _principle of least knowledge_ is a design guideline for developing software, particularly object-oriented programs.
Demeter’s law is known as “don’t talk to strangers” because:

1.  Each unit should have only limited knowledge about other units — only units “closely” related to the current unit.
2.  Each unit should only talk to its friends —  _don’t talk to strangers_.
3.  Only talk to your immediate friends.


## Composition Over Inheritance
A rule of thumb is to use HAS-A and IS-A phrases for composition and inheritance, respectively.

## Robustness Principle
> “Be conservative in what you do, be liberal in what you accept from others”

It reflects the idea that computer interfaces should be able to accept many different forms of information but always give you information in the same way.

## Inversion of Control

Inversion of Control is also known as the Hollywood Principle, “Don’t call us, we’ll call you”. It is a design principle in which custom-written portions of a computer program receive the flow of control from a generic framework.


**WHY**?
Inversion of control is used to increase modularity of the program and make it extensible.
To decouple the execution of a task from implementation.
To focus a module on the task it is designed for.
To free modules from assumptions about how other systems do what they do and instead rely on contracts.
To prevent side effects when replacing a module.
**HOW**?
Using Factory pattern
Using Service Locator pattern
Using Dependency Injection
Using contextualized lookup
Using Template Method pattern
Using Strategy pattern

## Maximize Cohesion

Cohesion of a single module/component is the degree to which its responsibilities form a meaningful unit; higher cohesion is better.


## Open/Closed Principle

the open/closed principle states “software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification”; that is, such an entity can allow its behavior to be extended without modifying its source code.

WHY?

-   Improve maintainability and stability by minimizing changes to existing code

HOW?

-   Write classes that can be extended (as opposed to classes that can be modified)
-   Expose only the moving parts that need to change, hide everything else
## Single Responsibility Principle

## Interface Segregation Principle

The interface-segregation principle (ISP) states that no client should be forced to depend on methods it does not use. ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them.
Avoid fat interfaces.

# Command Query Separation

It states that every method should either be a command that performs an action, or a query that returns data to the caller, but not both. In other words, Asking a question should not change the answer.

Consider the following pseudo-code service definition.

**CustomerService**void MakeCustomerPreferred(CustomerId)Customer GetCustomer(CustomerId)CustomerSet GetCustomersWithName(Name)CustomerSet GetPreferredCustomers()void ChangeCustomerLocale(CustomerId, NewLocale)void CreateCustomer(Customer)void EditCustomerDetails(CustomerDetails)

Applying CQRS on this would result in two services,

**CustomerWriteService**void MakeCustomerPreferred(CustomerId)void ChangeCustomerLocale(CustomerId, NewLocale)void CreateCustomer(Customer)void EditCustomerDetails(CustomerDetails)**CustomerReadService**Customer GetCustomer(CustomerId)CustomerSet GetCustomersWithName(Name)CustomerSet GetPreferredCustomers()
