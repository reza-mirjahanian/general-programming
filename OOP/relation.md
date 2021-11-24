
# Association vs Aggregation vs Composition

-   owners feed pets, pets please owners (**association**)
-   a tail is a part of both dogs and cats (**aggregation**  /  **composition**)
-   a cat is a kind of pet (**inheritance**  /  **generalization**)

**Aggregation**  and  **Composition**  are subsets of association meaning they are  **specific cases of association**. In both aggregation and composition object of one class "owns" object of another class. But there is a subtle difference:

-   **Aggregation**  implies a relationship where the child can exist independently of the parent. Example: Class (parent) and Student (child). Delete the Class and the Students still exist.
-   **Composition**  implies a relationship where the child cannot exist independent of the parent. Example: House (parent) and Room (child). Rooms don't exist separate to a House.


## Generalization vs Specialization

**Generalization**  is a mechanism for combining similar classes of objects into a single, more general class. Generalization identifies commonalities among a set of entities. The commonality may be of attributes, behavior, or both. In other words, a superclass has the most general attributes, operations, and relationships that may be shared with subclasses. A subclass may have more specialized attributes and operations.

**Specialization**  is the reverse process of Generalization means creating new sub-classes from an existing class.

##
Generalization vs Inheritance

**Generalization**  is the term that we use to denote abstraction of common properties into a base class in UML. The  **UML**  diagram's  **Generalization**  association is also known as  **Inheritance**. When we implement Generalization in a programming language, it is often called Inheritance instead. Generalization and inheritance are the same. The terminology just differs depending on the context where it is being used.
