# concat
Pretty Apex string builder for Salesforce/Force.com

## Features
* Null and empty string safe
* Clear chaining syntax
* Smart ending
* Default separator is space
* Default ending is no ending :)

## Example
```java
String f1 = 'Vasya';
String f2 = 'Petro';
String f3 = null;
String f4 = 'Andrew';
// Hello Vasya, Petro, Andrew!
String result = 'Hello ' + concat.strings(f1,f2,f3).add(f4).add(null).with(', ').end('!');
```

## Usage
### Constructor
Use Concat.strings() method to create new instance of StringBuilder.
```java
StringBuilder sb = concat.strings();
// or
StringBuilder sb = concat.strings(new List<String>{'a','b','c'});
// or
StringBuilder sb = concat.strings('a');
// or even
StringBuilder sb = concat.strings('a', 'b');
// ..up to 8 strings
StringBuilder sb = concat.strings('a','b','c','d','e','f','g','h');
```

### Add more strings
```java
StringBuilder sb = concat.strings('thing').add('one more');
sb.add('and one more');
// or use chaining
StringBuilder sb = concat.strings().add('one').add('two');
```

### Set separator
```java
sb.with(', ');
// with chaining
StringBuilder sb = concat.strings('zero').add('one').add('two').with('; ');
```

### Set ending and take your result string without removed nulls, empty strings with properly set separators and ending
```java
// no ending
String s = concat.strings('zero').add('one').add('two').with('; ').end();
// some ending
String s = concat.strings('zero').add('one').add('two').with('; ').end('.'); 
```