# Assoc
Lookup a key in an assoc list

## Examples

```elm
namesByAges = [("Mary", 30), ("John", 20), ("Ivan", 18), ("John", 100)]
lookup "John" namesByAges == Just 20
lookupAll "John" namesByAges == [20, 100]
lookup "Pete" namesByAges == Nothing
lookupAll "Pete" namesByAges == []
```

## Running tests
To run tests use [elm-test](https://github.com/elm-community/elm-test)
