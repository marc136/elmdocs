# elm-tuple-extra
This package contains functions to make working with tuples easier.<br>
I recommend importing the needed modules like this:

    import Tuple2.Extra as Tuple2
    import Tuple2.Infix expsoing (..)
    
You can then use different convenient functions to work with your tuples.

    five = 
        (1 , 2)               -- Creates the tuple             (1,2)
        |> Tuple2.map ((+)1)  -- Adds 1 to each element        (2,3)
        |> Tuple2.reduce (+)  -- Adds the elements together    5


The arrow notation is usefull if you create many tuples at once

    tuples =
        [ "a" => 1
        , "b" => 2
        , "c" => 3
        ]
        
To work with tuples of numbers there are some special functions:

    twenty =
        (1 , 2)                -- Creates the tuple    (1, 2)
        |> Tuple.add (3, 4)    -- Adds 3 and 4         (4, 6)
        |> Tuple.scale 2       -- Multiplies by 2      (8, 12)
        |> Tuple.sum           -- Sums it up           20
        
        
For a full documentation read the module docs.

## Folder Structure

    .
    ├── src          # Source files of the project
    │   ├── Tuple2   # Functions for tuples of two elements are in Tuple2, 
    │   ├── Tuple3   # those for three elements in Tuple3, etc.
    │   └── Tuple4 
    ├── tests        # Tests. Has the same structure as the src folder.
    │   ├── Tuple2
    │   ├── Tuple3
    │   └── Tuple4
    └── README.md
    
Functions belong in their `TupleN.Extra` modules. If the functions are infix then they are placed in the `TupleN.Infix` module. The test for each function belongs in `TupleN.ExtraTest` or `TupleN.InfixTest`
