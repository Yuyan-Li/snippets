# Wrapping settings
Change from "Wrap where necessary" to either "Wrap all elements, every element on a new line" or
"Wrap all elements, except first element, if not necessary".
## Constructor Declarations
### Parameters
Before
```
class Example {
  Example(int arg1, int arg2, int arg3,
      int arg4, int arg5, int arg6) {
    this();
  }

  Example() {}
}
```
after
```
class Example {
  Example(int arg1,
      int arg2,
      int arg3,
      int arg4,
      int arg5,
      int arg6) {
    this();
  }

  Example() {}
}
```

## Method Declarations
### Parameters
Before
```
class Example {
  void foo(int arg1, int arg2, int arg3,
      int arg4, int arg5, int arg6) {}
}
```
after
```
class Example {
  void foo(int arg1,
      int arg2,
      int arg3,
      int arg4,
      int arg5,
      int arg6) {}
}
```

## Record declarations
### Record components
Before
```
record Example(int firstNumber, int secondNumbere,
    String string) {
}
```
after
```
record Example(int firstNumber,
    int secondNumbere,
    String string) {
}
```

## Function Calls
### Arguments
Before
```
class Example {
  void foo() {
    Other.bar(100, nested(200, 300, 400,
        500, 600, 700, 800, 900));
  }
}
```
after
```
class Example {
  void foo() {
    Other.bar(100,
        nested(200,
            300,
            400,
            500,
            600,
            700,
            800,
            900));
  }
}
```

### Qualified invocations
Before
```
class Example {
  int foo(Some a) {
    var foobar =
        a.getFirst().doSomething()
            .doMore().finish();
    return a.getFirst().doSomething();
  }
}
```
after
```
class Example {
  int foo(Some a) {
    var foobar = a.getFirst()
        .doSomething()
        .doMore()
        .finish();
    return a.getFirst().doSomething();
  }
}
```

### Explicit constructor invocations
Before
```
class Example extends AnotherClass {
  Example() {
    super(100, 200, 300, 400, 500, 600,
        700);
  }
}
```
after
```
class Example extends AnotherClass {
  Example() {
    super(100,
        200,
        300,
        400,
        500,
        600,
        700);
  }
}
```

### Object allocation arguments
Before
```
class Example {
  SomeClass foo() {
    return new SomeClass(100, 200, 300,
        400, 500, 600, 700, 800, 900);
  }
}
```
after
```
class Example {
  SomeClass foo() {
    return new SomeClass(100,
        200,
        300,
        400,
        500,
        600,
        700,
        800,
        900);
  }
}
```

### Qualified object allocation arguments
Before
```
class Example {
  SomeClass foo() {
    return SomeOtherClass.new SomeClass(
        100, 200, 300, 400, 500);
  }
}
```
after
```
class Example {
  SomeClass foo() {
    return SomeOtherClass.new SomeClass(100,
        200,
        300,
        400,
        500);
  }
}
```

## Other expressions
### Array initializers
Before
```
class Example {
  int[] fArray = {1, 2, 3, 4, 5, 6, 7,
      8, 9, 10, 11, 12};
}
```
after
```
class Example {
  int[] fArray = {1,
      2,
      3,
      4,
      5,
      6,
      7,
      8,
      9,
      10,
      11,
      12};
}
```

## Statements
### 'multi-catch'
Before
```
class Example {
  void foo() {
    try {
    } catch (IllegalArgumentException | NullPointerException
        | ClassCastException e) {
      e.printStackTrace();
    }
  }
}
```
after
```
class Example {
  void foo() {
    try {
    } catch (IllegalArgumentException
        | NullPointerException
        | ClassCastException e) {
      e.printStackTrace();
    }
  }
}
```

## Annotations
### Element-value pairs
Before
```
@MyAnnotation(v1 = "an", v2 = "exp",
    value3 = "with several arguments",
    value4 = "which may need to be wrapped")
class Example {
}
```
after
```
@MyAnnotation(v1 = "an",
    v2 = "exp",
    value3 = "with several arguments",
    value4 = "which may need to be wrapped")
class Example {
}
```

