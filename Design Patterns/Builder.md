# Builder Pattern

## Intent

Separate the construction of a **complex object** from its representation so that the same construction process can create different representations.

## Applicability

Use the Builder pattern when

* the algorithm for creating a complex object should be independent of the
parts that make up the object and how they're assembled.

* the construction process must allow different representations for the object
that's constructed.

## Participants

1. `Builder` 

   * specifies an abstract interface for creating parts of a Product object.

2. `ConcreteBuilder`

   * constructs and assembles parts of the product by implementing the Builder
   interface.

   * defines and keeps track ofthe representation it creates.

   * provides an interface for retrieving the product.

3. `Director`

    * constructs an object using the Builder interface.

4. `Product`

    * represents the complex object under construction. ConcreteBuilder builds the product's internal representation and definesthe process by which it's assembled.

    * includes classes that define the constituent parts, including interfaces for assembling the parts into the final result.

## Collaboration

* The client creates the Director object and configure sit with the desired Builder
object.

* Director notifies the builder whenever a part of the product should be built.

* Builder handles requests from the director and adds parts to the product.

* The client retrieves the product from the builder.

---

_[refference](https://en.wikipedia.org/wiki/Design_Patterns)_

_Thanks._
