# Implementation

What is it? _[here](../Programming%20Concepts/FluentInterface.md)._

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

# Client Code

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