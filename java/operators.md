# Java : Operators

## Operators

```text
+ - * / %
++ --
== != < <= > >=
&& || !
& | ^ ~ << >> >>>
= += -= *= /=
?:
instanceof
```

```java
boolean sameReference = first == second;
boolean sameValue = first.equals(second);
int result = condition ? success : fallback;
```

Use `==` for primitive equality and reference identity. Use `equals` for value semantics. Parenthesize mixed expressions when precedence is not immediately clear and avoid side effects inside complex conditions.
