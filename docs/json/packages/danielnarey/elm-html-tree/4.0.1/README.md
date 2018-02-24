# Deprecated

This package was my initial attempt to make Elm view code more pipeline-friendly
by representing HTML elements as updatable Elm records, which would then be
rendered to unmodifiable VirtualDom nodes. Major features of the API have been
incorporated into the
[Element module](http://package.elm-lang.org/packages/danielnarey/elm-semantic-dom/3.0.0/Dom-Element)
of my Semantic Dom package. The improved version in Semantic Dom is implemented
more efficiently; instead of having to traverse a tree of records to render to
VirtualDom, the rendering function is called on child nodes whenever they
are placed in a container. 
