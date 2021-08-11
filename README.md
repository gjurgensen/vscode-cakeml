Basic syntax highlighting for CakeML.

## Issues
Multi-line declarations may fail to parse. For instance:

```sml
fun 
  foo x = 
  x
```

Here, `foo` and `x` are not recognized as a function name and parameter, as they would in a single-line declaration. This is a fundamental limitation of the TextMate regex engine, which only matches against one line at a time.