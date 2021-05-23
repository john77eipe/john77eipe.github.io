## Dynamic selection of implementations

Let's say you have different implementations of an interface. Initialized as singleton beans using spring or any other framework.
And you want to select them based on some string value 

```java
interface Inf {}
class A implements Inf{
}
class B implements Inf{
}

//in your code
Inf obj = null;
@Autowire
A a;
@Autowire
B b;
public Inf getImpl(String input) {
    if(input.equals("aaa"))
        return a;
    else if (input.equals("bbb"))
        return b;
    else
        return null;
}
```

There has to be a better way especially when your implementations are more than 2 or 3.

Using a lookup

```java
Map<String, Inf> lookup = new HashMap<String, Inf>();

@Bean
public Map<String, Inf> getLookup() {
    lookup.put("aaa", a);
    lookup.put("bbb", b);
}

//in code
public Inf getImpl(String input) {
    return lookup.get(input);
}
```

If you need a more conditional/regular expression check instead of a direct comparison.

```java
Optional data = lookup.keySet()
        .stream()
        .filter(s -> s.startsWith(input)).findFirst().map(s -> lookup.get(s));
```
