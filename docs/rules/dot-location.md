# Enforce newline before and after dot (dot-location)

JavaScript allows you to place newlines before or after a dot in a member expression.

Consistency in placing a newline before or after the dot can greatly increase readability.

```js
var a = universe.
        galaxy;

var b = universe
       .galaxy;
```

## Rule Details

This rule aims to enforce newline consistency in member expressions. This rule prevents the use of mixed newlines around the dot in a member expression.

### Options

The rule takes one option, a string, which can be either `object` or `property`.
If it is `object`, the dot in a member expression should be on the same line as the object portion.
If it is `property`, the dot in a member expression should be on the same line as the property portion.

If unset, the default behavior is `"object"`.

```json
    "dot-location": [2, "object"]
```

#### "object"

This is the default option. It requires the dot to be on the same line as the object.

The following patterns are considered warnings:

```js
var foo = object
.property;
```

The following patterns are not warnings:

```js
var foo = object.
property;
var bar = object.property;
```

#### "property"

This option requires the dot to be on the same line as the property.

The following patterns are considered warnings:

```js
var foo = object.
property;
```

The following patterns are not warnings:

```js
var foo = object
.property;
var bar = object.property;
```

## When Not To Use It

You can turn this rule off if you are not concerned with the consistency of newlines before or after dots in member expressions.

## Related Rules

* [newline-after-var](newline-after-var.md)
* [dot-notation](dot-notation.md)
