# Convert a number from one base to another base

We can pass base as another parameter in `Integer.parseInt` method in java

```java
String number = "111001";
int base = 2;
int convertToBase = 10;

Integer.parseInt(Integer.toString(Integer.parseInt(number, base), convertToBase));

```

#Caveats
Max radix = 36: "If the radix is smaller than Character.MIN_RADIX 
or larger than Character.MAX_RADIX, then the radix 10 is used instead.
