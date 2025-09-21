# Abstract Factory Pattern

## Intent

Provide an interface for creating **families of related** or dependent objects without specifying their concrete classes.

## Applicability

Use the Abstract Factory pattern when

* a system should be independent of how its products are created, composed, and represented.

* a system should be configured with one of multiple families of products.

* a family of related product objects is designed to be used together, and you need to enforce this constraint.

* you want to provide a class library of products, and you want to reveal just their interfaces, not their implementations.

## Participants

1. `AbstractFactory` 

   * declares an interface for operations that create abstract product object.

2. `ConcreteFactory`

   * implements the operations to create concrete product objects.

3. `AbstractProduct`

    * declares an interface for a type of product object.

4. `ConcreteProduct`

    * defines a product object to be created by the corresponding concrete factory.

    * implements the AbstractProduct interface.

5. `Client`

    * uses only interfaces declared by AbstractFactory and AbstractProduct classes.

## Collaboration

* Normally a single instance of a ConcreteFactory class is created at run-time. This concrete factory creates product objects having a particular implementation. **To create different product objects, clients should use a different concrete factory.**

* AbstractFactory defers creation of product objects to its ConcreteFactory subclass.

---

#### _**refference**_: Design Patterns Elements of Reusable Object-Oriented Software

_Thanks._
