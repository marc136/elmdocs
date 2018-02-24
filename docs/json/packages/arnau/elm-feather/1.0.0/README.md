# Feather in Elm

## What is Feather?

Quoting [the original project](https://github.com/colebemis/feather)

> Feather is a collection of simply beautiful open source icons. Each icon is
> designed on a 24x24 grid with an emphasis on simplicity, consistency and
> readability.

This translation is based on Feather 3.2.2

## Example

```elm
import Feather

view : Html Msg
view =
  div [] [ Feather.alertTriangle "#7EA" 24  ]
```

## Credits

Thanks to Cole Bemis for releasing [Feather icons](https://feathericons.com/)
under MIT.

## License

See [LICENSE](./LICENSE)
