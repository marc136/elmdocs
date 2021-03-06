elm-memo
========

Most basic memoization functionality.

If you have a function `fun : Int -> Int -> Bool` that is expensive to
compute, and you know you are going to repeatedly need values of that
function with first argument `100` and second argument either between
`1` and `10` or between `30` and `40`, you can do:

```elm
memoized : Int -> Maybe Bool
memoized =
    memo (fun 100) ([1..10] ++ [30..40])
```

and later use `memoized 5`, `memoized 35`, `memoized 35`, `memoized 5`,
`memoized 35`, etc.

No recomputation will take place, i.e., each of `fun 100 5` and `fun
100 35` will be computed only once. Also, only results that are
actually needed will be computed, so in the example only `fun 100 5`
and `fun 100 35` will be computed at all, no `fun 100 1` or any others
in the range.

The return value is `Nothing` if the argument provided is not in the
range declared when `memo` was called. One way for a client of the
library to handle this case is as follows:
```elm
memoFallback : (comparable -> b) -> List comparable -> comparable -> b
memoFallback fun args =
    let
        memoized =
            memo fun args
    in
        \arg ->
            case memoized arg of
                Just val ->
                    val

                Nothing ->
                    fun arg
```
But other ways are reasonable as well (depending on scenario), e.g.,
replacing `fun arg` in the last line by a conscious call to
[`Debug.crash`](http://package.elm-lang.org/packages/elm-lang/core/latest/Debug#crash).

Here is a fun use of memoization to avoid recursion explosion:
```elm
fibonacci : Int -> Int
fibonacci n =
    let
        mfib =
            memoFallback fib [2..n - 2]

        fib n =
            if n < 2 then
                1
            else
                mfib (n - 1) + mfib (n - 2)
    in
        fib n
```
