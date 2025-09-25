# Abstract Factory Pattern

## Intent

In computer programming, the **strategy pattern** (also known as the **policy pattern**) is a behavioral software design pattern that enables `selecting an algorithm at runtime`. Instead of implementing a single algorithm directly, code receives runtime instructions as to which in a family of algorithms to use.

_[refference](https://en.wikipedia.org/wiki/Strategy_pattern)_

## Applicability

Use the Strategy pattern when

* many related classes differ only in their behavior. Strategies provide a way to configure a class with one of many behaviors.

* you need different variants of an algorithm. For example, you might define algorithms reflecting different space/time trade-offs. Strategies can be used when these variants are implemented as a class hierarchy of algorithms [HO87].

* an algorithm uses data that clients shouldn't know about. Use the Strategy pattern to avoid exposing complex, algorithm-specific data structures.

* a class defines many behaviors, and these appear as multiple conditional statements in its operations. Instead of many conditionals, move related conditional branches into their own Strategy class.

_[refference](https://en.wikipedia.org/wiki/Design_Patterns)_

## Participants

1. `Strategy`

    * declares an interface common to all supported algorithms. Context uses this interface to call the algorithm defined by a ConcreteStrategy.

2. `ConcreteStrategy`

    * implements the algorithm using the Strategy interface.

3. `Context`

    * is configured with a ConcreteStrategy object.

    * maintains a reference to a Strategy object.

    * may define an interface that lets Strategy access its data.

_[refference](https://en.wikipedia.org/wiki/Design_Patterns)_

## Collaboration

* Strategy and Context interact to implement the chosen algorithm. A context may pass all data required by the algorithm to the strategy when the algorithm is called Alternatively, the context can pass itself as an argument to Strategy operations. That lets the strategy call back on the context as required.

* A context forwards requests from its clients to its strategy. Clients usually create and pass a ConcreteStrategy object to the context; thereafter, clients
interact with the contextexclusively.There is often a family ofConcreteStrategy classes for a client to choose from.

_[refference](https://en.wikipedia.org/wiki/Design_Patterns)_

---

_Thanks._
