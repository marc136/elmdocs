![](graphdemo.png)

GraphDisplay
============

This package creates SVG images of graphs.  It makes use of the
package `jxxcarlson/geometry`.

Example
-------

First, make define a graph:
```
import DisplayGraph

vertices =
    [ Vertex 1 "A", Vertex 2 "B", Vertex 3 "C", Vertex 4 "D", Vertex 5 "E" ]

edges =
    [ ( 1, 2 ), ( 1, 3 ), ( 2, 3 ), ( 2, 4 ), ( 2, 5 ), ( 3, 4 ), ( 4, 5 ) ]

    testGraph =
        Graph vertices edges
```

Second, create an SVG representation of it:

```
svgImage = graphDisplay 100 testGraph
```

The `100` is a scale factor.  For a demo that
displays the above graph, run

```
$ elm make GraphDemo.elm
```

in the examples folder.  
