

# Use `markdown-toc` to generate ToC

# Table of Contents

1. [Creating and Destroying Objects](#creating-and-destroying-objects)
  - [Item 1](#item-1-consider-static-factories-instead-of-constructors)
  - [Item 2](#item-2-use-builder-when-faced-with-many-constructors)
  - [Item 3](#item-3)
  - [Item 4](#item-4)
  - [Item 5](#item-5)
  - [Item 6](#item-6)
  - [Item 7](#item-7)
  - [Item 8](#item-8)
  - [Item 9](#item-9)
  - [Item 10](#item-10)
  - [Item 11](#item-11)
  - [Item 12](#item-12)
  - [Item 13](#item-13)
  - [Item 14](#item-14)
  - [Item 15](#item-15)
  - [Item 16](#item-16)
  - [Item 17](#item-17)
  - [Item 18](#item-18)
  - [Item 19](#item-19)
  - [Item 20](#item-20)
  - [Item 21](#item-21)
  - [Item 22](#item-22)
  - [Item 23](#item-23)
  - [Item 24](#item-24)
  - [Item 25](#item-25)
2. [Generics](#generics)  
  - [Item 26](#item-26)
  - [Item 27](#item-27)
  - [Item 28](#item-28)
  - [Item 29](#item-29)
  - [Item 30](#item-30)
  - [Item 31](#item-31)
  - [Item 32](#item-32)
  - [Item 33](#item-33)
  - [Item 34](#item-34)
  - [Item 35](#item-35)
  - [Item 36](#item-36)
  - [Item 37](#item-37)
  - [Item 38](#item-38)
  - [Item 39](#item-39)
  - [Item 40](#item-40)
  - [Item 41](#item-41)
  - [Item 42](#item-42)
  - [Item 43](#item-43)
  - [Item 44](#item-44)
  - [Item 45](#item-45)
  - [Item 46](#item-46)
  - [Item 47](#item-47)
  - [Item 48](#item-48)
  - [Item 49](#item-49)
  - [Item 50](#item-50)
  - [Item 51](#item-51)
  - [Item 52](#item-52)
  - [Item 53](#item-53)
  - [Item 54](#item-54)
  - [Item 55](#item-55)
  - [Item 56](#item-56)
  - [Item 57](#item-57)
  - [Item 58](#item-58)
  - [Item 59](#item-59)
  - [Item 60](#item-60)
  - [Item 61](#item-61)
  - [Item 62](#item-62)
  - [Item 63](#item-63)
  - [Item 64](#item-64)
  - [Item 65](#item-65)
  - [Item 66](#item-66)
  - [Item 67](#item-67)
  - [Item 68](#item-68)

10. [Exceptions](#exceptions)
  - [Item 69](#item-69-use-exceptions-only-for-exceptional-conditions)
  - [Item 70](#item-70-use-checked-exceptions-for-recoverable-conditions-&-runtime-exceptions-for-programming-errors)
  - [Item 71](#item-71-avoid-unnecessary-use-of-checked-exceptions)
  - [Item 72](#item-72-favour-use-of-standard-exceptions)
  - [Item 73](#item-73-throw-exception-appropriate-to-abstraction)
  - [Item 74](#item-74-document-all-exceptions-thrown-by-each-method)
  - [Item 75](#item-75-include-failure-capture-information-in-detail-messages)
  - [Item 76](#item-76-strive-for-failure-atomicity)
  - [Item 77](#item-77-don't-ignore-exceptions)

11. [Concurrency](#concurrency)    
  - [Item 78](#item-78)
  - [Item 79](#item-79)
  - [Item 80](#item-80)
  - [Item 81](#item-81)
  - [Item 82](#item-82)
  - [Item 83](#item-83)
  - [Item 84](#item-84)


12. [Serialization](#serialization)  
  - [Item 85](#item-85)
  - [Item 86](#item-86)
  - [Item 87](#item-87)
  - [Item 88](#item-88)
  - [Item 89](#item-89)
  - [Item 90](#item-90)
  - [Item 91](#item-91)
  - [Item 92](#item-92)
  - [Item 93](#item-93)
  - [Item 94](#item-94)
  - [Item 95](#item-95)
  - [Item 96](#item-96)
  - [Item 97](#item-97)
  - [Item 98](#item-98)
  - [Item 99](#item-99)

# Creating and Destroying Objects

## Item 1 Consider Static Factories Instead of Constructors

**Rule of Thumb**: 
- If class has 3 or less paramenters, use *static factory*.
- If not, use [builder](#item-2-use-builder-when-faced-with-many-constructors) *(See Item 2)*

## Item 2 Use Builder when faced with many constructors
## Item 3
## Item 4
## Item 5
## Item 6
## Item 7
## Item 8
## Item 9 

## Item 10
## Item 11
## Item 12
## Item 13
## Item 14


## Item 15
## Item 16
## Item 17
## Item 18
## Item 19
## Item 20
## Item 21
## Item 22
## Item 23
## Item 24
## Item 25

# Generics
## Item 26
## Item 27
## Item 28
## Item 29
## Item 30
## Item 31
## Item 32
## Item 33


## Item 34
## Item 35
## Item 36
## Item 37
## Item 38
## Item 39
## Item 40
## Item 41

## Item 42
## Item 43
## Item 44
## Item 45
## Item 46
## Item 47
## Item 48

## Item 49
## Item 50
## Item 51
## Item 52
## Item 53
## Item 54
## Item 55
## Item 56

## Item 57
## Item 58
## Item 59
## Item 60
## Item 61
## Item 62
## Item 63
## Item 64
## Item 65
## Item 66
## Item 67
## Item 68


# Exceptions

|Checked Exceptions|Runtime Exceptions|
|--|--|
|**Catch early & Propogate Exceptions**|**Programmable Error: Fix code**|
|Javadoc `@throws` tag to document checked exception. See *Item 74*|Since Unchecked exception are programming errors, **DO NOT DOCUMENT USING `@throws`**.[Controversy](https://docs.oracle.com/javase/tutorial/essential/exceptions/runtime.html)|
|Use this for conditions from which the caller can reasonably be expected to recover|All of the unchecked throwables you implement should subclass `RuntimeException`|
|ClassNotFoundException|NullPointerException|
|InterruptException|ArrayIndexOutOfBoundsException|
|IOException|ArithmeticException|
|SQLException|ClasscastException|
|InstantiationException|ArrayStoreException|
|FileNotFoundException|IllegalThreadStateException|



## Item 69 Use Exceptions Only For Exceptional Conditions

**TL; DR :**  Don’t use them for ordinary control flow (loops), and don’t write APIs that force others to do so.

**History Lesson:** This "exceptions only for exceptional circumstances" business stems from a time when exception handling was deemed an unacceptable performance hit. (Opinion I found on Internet)


### Problem Code

```java 
// Horrible Code
public String processString(String[] strings){
    String resultString="";
    int i = 0;
    try {
        while(true) {
            resultString = resultString.concat(strings[i]);
        }
    }
    catch (ArrayIndexOutOfBoundsException ex){

    }
    return resultString;
}
```

### Solution code

```java 
// Better Code
public String processString(String[] strings){
    String resultString="";
    for(i=0; i< strings.length; ++i){
        result = result.concat(strings[i]);
    }
    return resultString;
}
```

Use state-testing (If statement)
    - Item 55 for handling `null` values using `Optional`

## Item 70 Use Checked Exceptions For Recoverable Conditions & Runtime Exceptions For Programming Errors
Java has three type of throwables:
1. Checked Exceptions
2. Unchecked/runtime exceptions
3. Errors

When in doubt, throw unchecked exceptions.

## Item 71 Avoid Unnecessary Use Of Checked Exceptions


### Problem Code

```java
// Catch example
catch (TheCheckedException e) {
throw new AssertionError(); // Can't happen!
}
// another example
} catch (TheCheckedException e) {
e.printStackTrace(); // Oh well, we lose.
System.exit(1);
}
```

### Solution
**Checked Exception**: If Exception condition cannot be prevented by proper use of API and Programmer using the API can take appropriate decision using the exception
If both of the above 2 conditions are not met, used **Unchecked Exceptions**
Easiest way to remove remove checked exception is to use `Optional`. [Item 55](#item-55)
// TODO

## Item 72 Favour Use Of Standard Exceptions
## Item 73 Throw Exception Appropriate To Abstraction
## Item 74 Document All Exceptions Thrown By Each Method


## Item 75 Include Failure Capture Information In Detail Messages
Use the Javadoc `@throws` tag to document each exception that a method can throw, but do not use the throws keyword on unchecked exceptions. It is
important that programmers using your API are aware of which exceptions are checked and which are unchecked because the programmers’ responsibilities
differ in these two cases. 
The documentation generated by the Javadoc `@throws` tag without a corresponding throws clause in the method declaration provides a strong visual cue to the programmer that an exception is unchecked.

## Item 76 Strive For Failure Atomicity

## Item 77 Don't Ignore Exceptions
When you use an dependency and the method throws Exception, don't just surround the exception with a `catch{}` block.

```java
try {
...
} catch (DependencyException e) { // Don't do this
}
```

### Ignoring exceptions
There are very few cases when you can ignore the exception(very few). In such cases, you should at least log for investigation reasons.
If you ignore, you need to log and comment as to why you are not throwing the exception.

### Why propogate exceptions?

1. Fail program swiftly at the lowest/earliest level.
2. Propogate exceptions outward so that the information is preserved, which makes debugging a lot more informative.

# Concurrency
## Item 78
## Item 79
## Item 80
## Item 81
## Item 82
## Item 83
## Item 84

# Serialization
## Item 85
## Item 86
## Item 87
## Item 88
## Item 89
## Item 90
