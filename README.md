## Asterisk will help developers to create style sheets faster and simpler.

The helper receives a property name as the first argument followed by its values. In case you need to send more than one property name or
value at the same time, you can send both as a list separated by commas. All the values in the second argument will be assigned to each
property in the first argument.

Optionally, a third boolean argument can be passed to set CSS prefixes such as 'moz' and 'webkit'.
There is also a fourth and optional argument that will be used as a glue to join the values in a list.

Notice that for asterisk a list must be separated by commas (","). Lists separated by spaces will be interpreted as strings and won't work
properly. Since these lists are separated by a comma, make sure to declare them between parenthesis, otherwise the interpreter believe
that second index of the values list is the third argumented reveived by asterisk.

Reference:

asterisk(mixed $properties, mixed $values [, string $glue [, boolean $prefixed ]])

Examples in SCSS:

```scss
@import asterisk

p{
    @include sk(font-family, ("Verdana, Tahoma"));
    @include sk(font-family, "Verdana, Tahoma");
    @include sk(font-family, (Verdana, Tahoma));

    @include sk(margin, 1px 2px);
    @include sk(margin, "2px 3px");
    @include sk(margin, (3px 4px));
    @include sk((margin, padding), (5px 6px));

    @include sk(box-shadow, 1px 2px 3px black, true);
    @include sk(box-shadow, (-5px -5px 5px red, 5px 5px 5px blue), true);
}
```
