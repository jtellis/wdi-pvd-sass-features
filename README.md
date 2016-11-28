# Mixins

## What Are Mixins?
One of the most powerful features of the CSS preprocessor Sass is the mixin, an abstraction of a common pattern into a semantic and reusable chunk. Think of taking the styles for a button and, instead of needing to remember what all of the properties are, having a selector include the styles for the button instead.

## Defining a Mixin
Mixins are defined with the @mixin directive. It’s followed by the name of the mixin and optionally the arguments, and a block containing the contents of the mixin. The arguments are written as variable names ($variable-name) separated by commas, all in parentheses after the name.
```scss
@mixin example-mixin($arg1, $arg2) {
  background-color: $arg1;
  color: $arg2;
}
```

## Using a Mixins
Mixins are included in the document with the @include directive. This takes the name of a mixin and optionally arguments to pass to it, and includes the styles defined by that mixin into the current rule.
```scss
body {
  @include example-mixin(white, black);
}
```

## Mixin Example
### Sass SCSS
```scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { @include border-radius(10px); }
```

### Resulting CSS
```css
.box {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```

## References
- [Sass Reference: Mixins](http://www.sass-lang.com/documentation/file.SASS_REFERENCE.html#mixins)
- [Sass Guide: Mixins](http://www.sass-lang.com/guide#topic-6)
