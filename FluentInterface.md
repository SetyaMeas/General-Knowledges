# Fluent Interface

This concept, created in 2005 by [Eric Evans](https://x.com/ericevans) and [Martin Fowler](https://x.com/martinfowler), aims to increase code readability by creating a domain-specific language (DSL). [_refference_](https://dzone.com/articles/java-fluent-api)

## Definition

The `Fluent Interface` is an object-oriented API design that allows us to chain method calls together in a readable and intuitive manner. [_refference_](https://www.baeldung.com/java-fluent-interface-vs-builder-pattern)

## Implementation

### Concept

To implement it, we need to declare methods that return objects from the same class. As a result, we’ll be able to chain together multiple method calls. The pattern is often used in building **DSLs** (Domain-Specific Languages). [_refference_](https://www.baeldung.com/java-fluent-interface-vs-builder-pattern)

### Code

This is my personal example code based on `Java` programming language:

```java
public final class SQL {

    private SQL() {}

    interface Select {
        From select();
    }

    interface From {
        Where from();
    }

    interface Where {
        String where();
    }

    public static class Query implements Select, From, Where {

        private String result;

        // create new query instance
        public static Select getInstance() {
            return new Query();
        }

        @Override
        public From select() {
            // modify result
            return this;
        }

        @Override
        public Where from() {
            // modify result
            return this;
        }

        @Override
        public String where() {
            // modify result
            return result;
        }
    }
}
```

#### Client Code

```java
public class Main {
    public static void main(String[] args) {
        String sqlResult = SQL.Query
                .getInstance()
                .select()
                .from()
                .where();

        System.out.println(sqlResult);
    }
}
```
---

_Thanks._