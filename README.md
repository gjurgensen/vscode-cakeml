Basic syntax highlighting for CakeML.

## Issues and limitations

### Multi-line declarations
Multi-line declarations may fail to parse. For instance:

```sml
fun 
  foo x = 
  x
```

Here, `foo` and `x` are not recognized as a function name and parameter, as they would in a single-line declaration. This is a fundamental limitation of the TextMate regex engine, which only matches against one line at a time.


### Tuple binders in val / datatype declarations
The following statement:

```sml
val (a, b, c) = foo
```

fails to parse correctly, because the grammar cannot handle variable-length tuples. While the corresponding regex matches fine, only the last of the repeated capture group 
within the tuple is correctly assigned a token name.
